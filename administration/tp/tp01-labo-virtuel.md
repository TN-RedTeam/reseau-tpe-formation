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

### 5. Le réglage réseau à connaître

Dans **Configuration → Réseau** de la VM, le mode définit comment elle communique :

| Mode | Effet |
|---|---|
| **NAT** (défaut) | La VM accède à internet, mais isolée | 
| **Accès par pont (Bridge)** | La VM est **sur ton vrai réseau** (comme une machine physique) |
| **Réseau interne / hôte-only** | Les VM se parlent **entre elles** (pour un labo privé) |

> 💡 Pour un labo multi-VM (TP suivants), le **réseau interne** (ou hôte-only) est idéal :
> tes VM forment leur propre petit réseau, isolé et sûr.

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
