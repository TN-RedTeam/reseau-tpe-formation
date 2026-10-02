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

#### 🏆 La config recommandée pour CE labo (2 cartes par VM)

On veut **deux choses** : qu'elles **se parlent entre elles** (le lab) **et** qu'elles aient
**internet** (mises à jour). Donc **2 cartes réseau** sur chaque VM :

| Carte | Mode | Pour quoi | Nom Linux probable |
|---|---|---|---|
| **Carte 1** | **NAT** | Internet (apt, Windows Update) — IP auto | `enp0s3` |
| **Carte 2** | **Réseau interne**, nom = **`LAB`** | Le réseau du labo (IP statiques) | `enp0s8` |

> Fais exactement la même chose sur **Windows Server**, **Ubuntu** et **Kali**, avec le
> **même nom de réseau interne** (`LAB`, à taper à l'identique). C'est ce qui les relie.

```
                 ┌── Carte 1 (NAT) ──► 🌐 Internet
   Chaque VM ────┤
                 └── Carte 2 (Réseau interne "LAB") ──► 🔗 les autres VM du labo
```

#### 🔢 Le plan d'adressage du labo (réseau `LAB`)

On choisit une plage, par exemple **`10.10.10.0/24`** :

| Machine | IP sur le réseau LAB |
|---|---|
| Windows Server | `10.10.10.10` |
| Ubuntu | `10.10.10.20` |
| Kali | `10.10.10.30` |

> 💡 Pas besoin de passerelle sur la carte LAB : internet passe par la carte **NAT**.

#### 🐧 Donner l'IP statique à Ubuntu **Server** (Netplan)

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

- [ ] La **carte est activée** ? (*Configuration → Réseau* → « Activer la carte réseau » coché)
- [ ] Le **câble est branché** ? (*Avancé → Câble branché* coché)
- [ ] Sur une carte **Réseau interne**, tu as bien mis une **IP statique** (pas de DHCP !) ?
- [ ] Le **nom du réseau interne** est **identique** sur toutes les VM (`LAB`) ?
- [ ] Les VM sont dans la **même plage** (`10.10.10.x`, masque `/24`) ?
- [ ] Après config Ubuntu : `sudo netplan apply` lancé ? `ip a` montre la bonne IP ?
- [ ] Test : depuis Ubuntu, `ping 10.10.10.10` (Windows Server) répond ? *(pense au
  pare-feu Windows qui bloque parfois le ping — voir TP02.)*
- [ ] Pas d'internet ? Vérifie la **carte NAT** (Carte 1) et, sous Ubuntu, `dhcp4: true`
  dessus.

#### 🪄 Option plus simple (si tu ne veux pas gérer les IP tout de suite)

Pour juste « que tout marche » avec internet **et** communication entre VM, sans config :
utilise un **Réseau NAT** unique. Dans VirtualBox : *Fichier → Outils → Gestionnaire de
réseau → Réseaux NAT → Créer* (ex. `LAB-NAT`, réseau `10.10.10.0/24`). Puis sur chaque VM :
Carte 1 → **Réseau NAT** → `LAB-NAT`. Il fournit **DHCP + internet + inter-VM**.
> ⚠️ À éviter **quand tu feras l'Active Directory** (TP02+) : tu voudras que **Windows
> Server** soit ton serveur DHCP/DNS, et le DHCP du Réseau NAT entrerait en conflit. Pour
> l'AD, reviens à **Réseau interne + IP statiques** (la config recommandée ci-dessus).

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
