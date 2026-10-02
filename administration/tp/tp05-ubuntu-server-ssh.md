# TP05 — Un serveur Linux (Ubuntu) : SSH, utilisateurs, services

🎯 **Objectif** : installer Ubuntu Server dans une VM, s'y connecter en **SSH**, gérer des
**utilisateurs** et un **service**. 🕐 Durée : ~45 min · Prérequis : TP01, admin 07.

> Pas d'interface graphique ici : on travaille **en ligne de commande**, comme sur un vrai
> serveur Linux. C'est l'objectif du TP : s'y habituer.

---

## 1. Créer la VM Ubuntu Server

1. Télécharge l'**ISO de Ubuntu Server LTS** (gratuit, ubuntu.com) — la version « LTS » =
   support long, celle qu'on met en production.
2. VirtualBox → **Nouvelle** → `SRV-LINUX` · Linux / Ubuntu 64-bit · RAM **2048 Mo** ·
   disque **20 Go**. Réseau : rattache-la au labo (voir [TP01, section 5](tp01-labo-virtuel.md#5-le-réseau-du-labo--à-lire-attentivement-)) —
   **option simple** : une carte en **« Réseau NAT » (`LAB-NAT`)** → **IP automatique**.
3. Branche l'ISO, démarre, suis l'installateur : clavier FR, **installe OpenSSH server**
   quand c'est proposé (coche la case !), crée ton utilisateur (ex : `admin-labo`).
4. *(Option avancée seulement)* fixe une IP statique `10.10.10.20` via Netplan
   ([TP01 §5](tp01-labo-virtuel.md#-donner-lip-statique-à-ubuntu-server-netplan-option-avancée)).
   En option simple, **note juste l'IP** donnée automatiquement (étape suivante).

## 2. Premiers repères (dans la console de la VM)

Connecte-toi avec ton utilisateur, puis :

```bash
pwd            # où suis-je
ls -l          # contenu du dossier
whoami         # mon compte
id             # mes groupes
ip a           # mon adresse IP → NOTE-LA (ex. 10.10.10.x sur le réseau du labo)
```

## 3. Se connecter en SSH (depuis une autre VM du labo)

> ⚠️ **Important** : le réseau du labo **n'est PAS accessible depuis ton PC hôte** (c'est
> fait pour isoler le labo). Donc on se connecte en SSH **depuis une autre VM du labo** —
> par exemple depuis **Windows Server** (PowerShell) ou **Kali** :

```bash
ssh admin-labo@10.10.10.20     # remplace par l'IP de ton Ubuntu (vue avec « ip a »)
```

> 🎉 Tu administres le serveur **à distance d'une machine à l'autre**, exactement comme en
> vrai. Tu n'as plus besoin de la fenêtre de la VM Ubuntu.

> 💡 **Tu veux vraiment SSH depuis ton PC hôte ?** Deux options : ajouter une **3ᵉ carte
> « Réseau privé hôte » (host-only)** à l'Ubuntu, ou mettre une **redirection de port** sur
> la carte NAT (*Configuration → Réseau → Carte 1 → Avancé → Redirection de ports* :
> hôte `2222` → invité `22`), puis `ssh -p 2222 admin-labo@127.0.0.1` depuis l'hôte.

## 4. Gérer des utilisateurs

```bash
sudo adduser bob                 # créer l'utilisateur bob
sudo usermod -aG sudo bob        # donner à bob le droit d'admin (sudo)
id bob                           # vérifier ses groupes
```

> 💡 `sudo` = exécuter en administrateur (admin 07). Tu dois taper ton mot de passe.

## 5. Jouer avec les droits de fichiers

```bash
touch rapport.txt                # créer un fichier
ls -l rapport.txt                # voir ses droits (rwx)
chmod 640 rapport.txt            # proprio: rw / groupe: r / autres: rien
sudo chown bob:bob rapport.txt   # changer propriétaire et groupe
ls -l rapport.txt                # vérifier
```

## 6. Gérer un service

Le service SSH tourne déjà. Observe et pilote-le :

```bash
sudo systemctl status ssh        # état (actif ?)
sudo systemctl restart ssh       # redémarrer
sudo systemctl enable ssh        # démarrage auto au boot
```

## 7. Mettre à jour le serveur

```bash
sudo apt update && sudo apt upgrade
```

```mermaid
flowchart LR
    PC[💻 Ton PC] -->|SSH| SRV[🐧 SRV-LINUX]
    SRV --> A[adduser / usermod]
    SRV --> B[chmod / chown]
    SRV --> C[systemctl: services]
    SRV --> D[apt: mises à jour]
```

---

## ✅ Réussite

Tu as installé un serveur Linux, tu t'y connectes en **SSH**, tu gères **utilisateurs,
droits, services et mises à jour**. Avec ça, tu peux administrer un NAS, un Raspberry Pi,
un serveur web… la plupart des équipements Linux d'un réseau.

## 🧠 Astuce sécurité (admin 10)

Plus tard, configure une **clé SSH** (connexion sans mot de passe, plus sûre) et **désactive
la connexion root directe**. Ce sont les premiers gestes de durcissement d'un serveur Linux.

---

⬅️ [TP04](tp04-serveur-fichiers-ntfs.md) · ➡️ [TP06 — Scénario d'administration complet](tp06-scenario-admin.md)
