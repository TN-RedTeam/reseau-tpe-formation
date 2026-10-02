# TP01 — Monter ton labo virtuel

🎯 **Objectif** : installer VirtualBox et créer ta première machine virtuelle (VM).
🕐 Durée : ~30 min · Prérequis : cours 15 (virtualisation), admin 03.

---

## 💡 L'idée

Une **machine virtuelle (VM)**, c'est un **ordinateur complet qui tourne dans une fenêtre**
de ton PC (rappel cours 15). Tu peux en créer plusieurs : un « serveur », des « postes »…
et les faire communiquer, comme un vrai réseau. Parfait pour s'entraîner.

---

## 🪜 Étapes

### 1. Installer VirtualBox

1. Va sur **https://www.virtualbox.org** → **Downloads**.
2. Télécharge la version pour ton système (Windows / macOS / Linux).
3. Installe (options par défaut). Installe aussi l'**Extension Pack** si proposé.

> 💡 Alternative : **VMware Workstation Player** (gratuit aussi). La logique est identique.

### 2. Récupérer une image à installer (ISO)

Pour ce premier TP, on prend un système **léger et gratuit** pour se faire la main :
- **Ubuntu Desktop** ou **Debian** (gratuit) : télécharge le fichier **.iso** sur le site
  officiel.
- *(On installera Windows Server au TP02.)*

Une **ISO** = l'image d'un disque d'installation (comme un CD d'install, en fichier).

### 3. Créer la VM

1. Dans VirtualBox : **Nouvelle**.
2. Nom : `LAB-TEST`. Type/Version : correspondant à ton ISO.
3. Mémoire : **2048 Mo** (2 Go) pour commencer.
4. Disque dur : **Créer un disque virtuel** → VDI → dynamiquement alloué → **25 Go**.

### 4. Brancher l'ISO et démarrer

1. Sélectionne la VM → **Configuration → Stockage**.
2. Clique sur le lecteur optique « Vide » → choisis ton fichier **.iso**.
3. **Démarrer** la VM : elle boote sur l'installateur. Suis l'assistant d'installation.

### 5. Le réseau du labo

Pour que tes VM aient **internet** ET qu'elles puissent **se parler entre elles**, on règle
leur réseau. **Ne te pose pas de question : suis les 3 étapes ci-dessous.** (Les explications
et les cas avancés sont juste en dessous, repliés — à ouvrir seulement si tu es curieux.)

#### 👉 La méthode recommandée (3 étapes)

**① Crée le réseau du labo — une seule fois, pour toutes tes VM.**
VirtualBox → menu **Fichier → Outils → Gestionnaire de réseau** → onglet **« Réseaux NAT »**
→ bouton **Créer**. Règle :
- **Nom** : `LAB-NAT`
- **CIDR** (plage) : `10.10.10.0/24`
- **DHCP** : **activé** ✅

**② Branche chaque VM sur ce réseau.**
VM **éteinte** → **Configuration** (⚙️) → **Réseau** → onglet **« Adaptateur 1 »** :
- coche **« Activer la carte réseau »**
- **Mode d'accès réseau** : **« Réseau NAT »**
- **Nom** : `LAB-NAT`

👉 Fais-le pour **Ubuntu**, **Windows Server** et **Kali**. (Tu ne touches qu'à
l'**Adaptateur 1**, rien d'autre.)

**③ Vérifie que ça marche.**
Démarre Ubuntu, ouvre un terminal :
```bash
ip a                 # tu dois voir une adresse en 10.10.10.x
ping 10.10.10.1      # la passerelle du réseau répond ?
ping ubuntu.com      # internet répond ?
```

> 🎉 **C'est tout.** Tes VM ont **internet + une IP automatique + elles se voient entre
> elles**. Aucune adresse IP à taper à la main. C'est la bonne base pour **tous** les TP.

> 🔌 Hôte en **filaire** ? Parfait, **aucun impact** : ce mode fonctionne pareil en filaire
> ou en Wi-Fi.

---

<details>
<summary>📖 <b>Pour comprendre</b> — les modes réseau de VirtualBox (optionnel)</summary>

<br>

Dans *Configuration → Réseau*, le **« Mode d'accès réseau »** décide de ce que la VM peut
faire. Les 5 modes :

| Mode | Internet ? | Les VM se parlent ? | L'hôte y accède ? | IP auto (DHCP) ? |
|---|---|---|---|---|
| **Réseau NAT** ⭐ | ✅ | ✅ | ❌ | ✅ |
| NAT (défaut) | ✅ | ❌ | ❌ | ✅ |
| Réseau interne | ❌ | ✅ | ❌ | ❌ |
| Réseau privé hôte (host-only) | ❌ | ✅ | ✅ | ⚙️ |
| Accès par pont (bridge) | ✅ | ✅ | ✅ | ✅ (via la box) |

👉 On choisit **« Réseau NAT »** parce que c'est **le seul qui fait les 3 choses à la fois** :
internet, communication entre VM, et IP automatique. D'où la méthode recommandée ci-dessus.

**⚠️ Le piège classique** : le mode **« Réseau interne »** tout seul **n'a pas de DHCP** →
personne ne distribue d'IP → la VM démarre **sans réseau**. C'est l'erreur n°1 des débutants.
On l'utilise seulement en « option avancée » (voir plus bas), avec des IP fixes.

**C'est quoi « Carte 1 / Carte 2 » ?** Une VM peut avoir jusqu'à **4 cartes réseau**.
Dans VirtualBox, ce sont les **onglets « Adaptateur 1, 2, 3, 4 »** en haut de la page Réseau
(Adaptateur 1 = « Carte 1 »). Pour notre méthode, **un seul adaptateur suffit**.

> 🖥️ Sous **VirtualBox 7.1**, l'allure des réglages a changé, mais la page **Réseau** garde
> ses 4 onglets d'adaptateurs.

</details>

<details>
<summary>🏢 <b>Pour plus tard</b> — l'option « 2 cartes » (exercice DHCP / Active Directory)</summary>

<br>

Tu n'en as **pas besoin maintenant.** Tu y viendras quand tu feras l'exercice où **c'est
Windows Server qui distribue les IP** (rôle DHCP, [admin 08](../08-dhcp-dns-serveur.md)) : là,
tu ne veux plus que VirtualBox s'en charge. On passe alors à **2 cartes par VM** :

| Onglet | Mode | Rôle | Nom Linux |
|---|---|---|---|
| **Adaptateur 1** | **NAT** | Internet (mises à jour) — IP auto | `enp0s3` |
| **Adaptateur 2** | **Réseau interne** nommé `LAB` | Le réseau du labo — **IP fixes** | `enp0s8` |

Plan d'adressage (réseau interne `LAB`, en `10.10.10.0/24`) :

| Machine | IP fixe |
|---|---|
| Windows Server | `10.10.10.10` |
| Ubuntu | `10.10.10.20` |
| Kali | `10.10.10.30` |

**Donner l'IP fixe à Ubuntu Server (Netplan) :**
```bash
sudo nano /etc/netplan/01-netcfg.yaml
```
```yaml
network:
  version: 2
  ethernets:
    enp0s3:            # Adaptateur 1 = NAT = internet
      dhcp4: true
    enp0s8:            # Adaptateur 2 = Réseau interne LAB = IP fixe
      dhcp4: false
      addresses:
        - 10.10.10.20/24
```
Puis `sudo netplan apply` et vérifie avec `ip a`.
> ⚠️ YAML = indentation avec des **espaces**, jamais de tabulation.
> 🖥️ Ubuntu **Desktop** : pas de Netplan → *Paramètres → Réseau → la carte LAB → IPv4 →
> Manuel*. 🪟 Windows Server : IP fixe réglée au [TP02](tp02-installer-windows-server.md).

</details>

#### 🩺 « Le réseau ne marche pas » — la check-list

- [ ] La VM était **éteinte** quand tu as changé le réseau ? (sinon, éteins/rallume)
- [ ] **Adaptateur 1** : « Activer la carte réseau » **coché**, Mode = **« Réseau NAT »**,
  Nom = **`LAB-NAT`** ? (⚠️ « Réseau NAT » ≠ « NAT » tout court)
- [ ] *Avancé → Câble branché* est bien coché ?
- [ ] Sur Ubuntu, `ip a` montre une IP en **`10.10.10.x`** ? Sinon : redémarre la VM.
- [ ] `ping 10.10.10.1` répond (le réseau) ? `ping ubuntu.com` répond (internet + DNS) ?
- [ ] Entre VM : `ping` l'IP d'une autre VM répond ? *(le pare-feu Windows bloque parfois le
  ping — voir TP02.)*

---

## ✅ Réussite

Ta VM démarre et tu arrives sur le bureau du système installé. 🎉 Tu as un ordinateur dans
ton ordinateur : la base de tout ton labo d'entraînement.

## 🧠 Astuce pro : les snapshots

Avant toute manip risquée, fais un **instantané (snapshot)** de la VM (menu *Machine →
Prendre un instantané*). Si tu casses tout, tu **reviens en arrière en 10 secondes**.
C'est le filet de sécurité de l'apprenant.

---

➡️ [TP02 — Installer Windows Server + domaine](tp02-installer-windows-server.md)
