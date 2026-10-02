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

### 5. Le réseau du labo — à lire attentivement ⭐

C'est **l'étape qui bloque tout le monde au début.** Prends 5 min, ça t'évitera des heures
de galère (« le réseau ne marche pas sur Ubuntu »).

#### Les 4 modes réseau de VirtualBox

Dans **Configuration → Réseau** de chaque VM, le « Mode d'accès réseau » définit comment
elle communique :

| Mode | Internet ? | Les VM se parlent ? | Le PC hôte y accède ? | **IP automatique (DHCP) ?** |
|---|---|---|---|---|
| **NAT** (défaut) | ✅ oui | ❌ non | ❌ non | ✅ oui |
| **Réseau NAT** | ✅ oui | ✅ oui | ❌ non | ✅ oui |
| **Réseau interne** | ❌ non | ✅ oui | ❌ non | ❌ **NON** ⚠️ |
| **Réseau privé hôte** (host-only) | ❌ non | ✅ oui | ✅ oui | ⚙️ selon réglage |
| **Accès par pont** (bridge) | ✅ oui | ✅ oui | ✅ oui | ✅ (via ta box) |

#### ⚠️ LE piège qui casse ton Ubuntu

Le **Réseau interne** isole parfaitement tes VM (c'est bien pour un labo)… mais **il n'a
AUCUN serveur DHCP**. Personne ne distribue d'adresse → ta VM démarre **sans IP** → « pas de
réseau ». 

Deux solutions, et on fait **les deux** dans ce labo :
1. **Mettre des IP statiques** toi-même (au début).
2. Plus tard, **Windows Server distribuera les IP** (rôle DHCP, cf. [admin 08](../08-dhcp-dns-serveur.md)) — c'est justement un exercice !

#### 📍 Où règle-t-on ça dans VirtualBox ? (c'est quoi « Carte 1 / Carte 2 »)

Une VM peut avoir **jusqu'à 4 cartes réseau virtuelles**. Dans VirtualBox elles
s'appellent **Adaptateur 1, 2, 3, 4** (c'est ça, « Carte 1 », « Carte 2 »…).

Pour les voir :
1. **Éteins la VM** (on ne change pas le réseau quand elle tourne).
2. Sélectionne la VM → **Configuration** (l'icône engrenage) → **Réseau**.
3. En haut de la page Réseau, il y a **4 onglets : « Adaptateur 1 », « Adaptateur 2 »,
   « Adaptateur 3 », « Adaptateur 4 »**. → **Adaptateur 1 = Carte 1**, etc.
4. Sur chaque onglet : coche **« Activer la carte réseau »**, puis choisis le **« Mode
   d'accès réseau »** dans la liste déroulante.

> 💡 Si tu n'utilises **qu'une seule carte**, tu restes sur l'onglet **Adaptateur 1** et
> tu ne touches pas aux autres. « Carte 2 » = **seulement si** tu actives un 2ᵉ onglet.

> 🖥️ **VirtualBox 7.1** a un peu changé l'allure des réglages, mais la page **Réseau** garde
> ses **4 onglets d'adaptateurs**. Si la fenêtre te paraît simplifiée, cherche un bouton
> **« Expert »/« Avancé »** pour tout afficher.

> 🔌 **Ton hôte est en filaire ?** Parfait, et ça **ne change rien** pour nous : le mode
> **NAT** (et **Réseau NAT**) marche pareil en filaire ou en Wi-Fi. (Le filaire est même
> l'idéal — c'est seulement le mode « Accès par pont » qui peut être capricieux en Wi-Fi,
> et on ne l'utilise pas.)

---

#### ✅ Option SIMPLE (recommandée pour démarrer) : un « Réseau NAT »

Le plus facile pour **te débloquer tout de suite** : une **seule carte** par VM, en mode
**« Réseau NAT »**. Il donne **internet + une IP automatique (DHCP) + la communication
entre VM**. Ton Ubuntu aura donc une IP **tout seul** (fini le « pas de réseau »).

1. **Crée le réseau NAT une fois** : dans VirtualBox, menu **Fichier → Outils →
   Gestionnaire de réseau** → onglet **« Réseaux NAT »** → **Créer**.
   - Nom : `LAB-NAT` · CIDR : `10.10.10.0/24` · DHCP : **activé**.
2. **Sur chaque VM** (Ubuntu, Windows Server, Kali), éteinte :
   **Configuration → Réseau → Adaptateur 1** → *Mode d'accès réseau* : **« Réseau NAT »** →
   *Nom* : **`LAB-NAT`**.
3. Démarre les VM. Sur Ubuntu : `ip a` → tu dois voir une IP en `10.10.10.x`. 🎉
   Test : `ping 10.10.10.1` (la passerelle), puis `ping ubuntu.com` (internet).

> 👉 Avec cette option, **pas de Netplan ni d'IP statique à taper** : tout est automatique.
> C'est l'idéal pour les premiers TP (01 à 07 côté réseau, et l'install des serveurs).

---

#### 🏆 Option AVANCÉE (2 cartes) : pour l'exercice DHCP / Active Directory

Quand tu arriveras à **Active Directory** (TP02+) et au **rôle DHCP** ([admin 08](../08-dhcp-dns-serveur.md)),
tu voudras que **ce soit Windows Server qui distribue les IP** — donc **pas** le DHCP de
VirtualBox. On passe alors à **2 cartes** par VM :

| Carte (onglet) | Mode | Pour quoi | Nom Linux probable |
|---|---|---|---|
| **Adaptateur 1** | **NAT** | Internet (apt, Windows Update) — IP auto | `enp0s3` |
| **Adaptateur 2** | **Réseau interne**, nom = **`LAB`** | Le réseau du labo (**IP statiques**) | `enp0s8` |

> Le **Réseau interne** n'a **pas** de DHCP (c'est le piège du dessus) → on met des **IP
> statiques** (voir plus bas). Même nom de réseau interne `LAB` sur les 3 VM = c'est ce qui
> les relie.

```
                 ┌── Adaptateur 1 (NAT) ──► 🌐 Internet
   Chaque VM ────┤
                 └── Adaptateur 2 (Réseau interne "LAB") ──► 🔗 les autres VM du labo
```

> 💡 **Mon conseil** : commence avec l'**option simple** (Réseau NAT) pour tout faire
> tourner. Tu basculeras sur l'option 2 cartes **seulement** au moment de l'exercice DHCP/AD.

#### 🔢 Le plan d'adressage du labo *(pour l'option avancée 2 cartes)*

> ℹ️ Avec l'**option simple (Réseau NAT)**, tu peux **sauter ce bloc** : les IP sont données
> automatiquement. Ce qui suit sert quand tu fixes les IP toi-même (option avancée, ou pour
> l'IP fixe de Windows Server).

On choisit une plage, par exemple **`10.10.10.0/24`** :

| Machine | IP sur le réseau LAB |
|---|---|
| Windows Server | `10.10.10.10` |
| Ubuntu | `10.10.10.20` |
| Kali | `10.10.10.30` |

> 💡 Pas besoin de passerelle sur la carte LAB : internet passe par la carte **NAT**.

#### 🐧 Donner l'IP statique à Ubuntu **Server** (Netplan) *(option avancée)*

1. Trouve le nom de tes cartes : `ip a` (tu verras `enp0s3`, `enp0s8`…).
2. Édite la conf : `sudo nano /etc/netplan/01-netcfg.yaml` (ou le fichier présent dans
   `/etc/netplan/`). Mets :

   ```yaml
   network:
     version: 2
     ethernets:
       enp0s3:            # Carte 1 = NAT = internet
         dhcp4: true
       enp0s8:            # Carte 2 = Réseau interne LAB = IP fixe
         dhcp4: false
         addresses:
           - 10.10.10.20/24
   ```
3. Applique : `sudo netplan apply`, puis vérifie : `ip a` (tu dois voir `10.10.10.20`).

> ⚠️ **YAML = indentation avec des ESPACES, jamais de tabulation.** Une mauvaise indentation
> = erreur. Respecte bien l'alignement ci-dessus.

> 🖥️ **Ubuntu Desktop** (interface graphique) : pas de Netplan à la main → *Paramètres →
> Réseau → la carte LAB → IPv4 → Manuel*, et saisis `10.10.10.20` / `24`.
> 🪟 **Windows Server / Kali** : réglage de l'IP fixe sur la carte LAB (vu au TP02 pour
> Windows ; sur Kali, via les paramètres réseau).

#### 🩺 « Le réseau ne marche pas » — la check-list

- [ ] L'**adaptateur est activé** ? (*Configuration → Réseau → Adaptateur 1* → « Activer la
  carte réseau » coché)
- [ ] Le **câble est branché** ? (*Avancé → Câble branché* coché)
- [ ] **Option simple** : l'adaptateur est bien sur **« Réseau NAT »** avec le nom
  **`LAB-NAT`** (et pas juste « NAT ») ? Sur Ubuntu, `ip a` montre une IP en `10.10.10.x` ?
- [ ] **Option avancée** : sur une carte **Réseau interne**, tu as bien mis une **IP
  statique** (pas de DHCP !), même **nom `LAB`** et même **plage `10.10.10.x /24`** partout ?
- [ ] Après config Ubuntu en statique : `sudo netplan apply` lancé ? `ip a` montre la bonne IP ?
- [ ] Test entre VM : depuis Ubuntu, `ping 10.10.10.10` (Windows Server) répond ? *(pense au
  pare-feu Windows qui bloque parfois le ping — voir TP02.)*
- [ ] Pas d'internet ? En option avancée, vérifie que l'**Adaptateur 1 (NAT)** est activé et,
  sous Ubuntu, `dhcp4: true` dessus.

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
