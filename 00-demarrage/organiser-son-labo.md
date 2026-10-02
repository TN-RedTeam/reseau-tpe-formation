# 🛠️ Tuto — Organiser ton atelier + partager des dossiers entre machines

Ce tuto répond à deux questions très concrètes quand on a **plusieurs machines** :
1. **Sur laquelle je bosse ?** (répartir les rôles)
2. **Comment partager un dossier entre Linux, Windows et Mac ?** (utile dès le cours 06)

> 💡 Exemple fil rouge : un setup courant de technicien — **un PC de bureau costaud
> (Linux + machines virtuelles), un laptop Windows, un Mac**. Adapte à ce que tu as.

---

# Partie 1 — Quelle machine pour quoi ?

Ne cherche pas à tout faire sur une seule machine. **Répartis par rôle**, comme dans une
vraie TPE/PME (qui est elle-même hétérogène).

| Machine | Rôle | Ce que tu y fais |
|---|---|---|
| 🏗️ **PC de bureau** (le plus puissant) | **L'atelier / le labo** | Les machines virtuelles (Windows Server, Linux, Kali), Packet Tracer, les TP d'administration |
| 💻 **Laptop Windows** | **Le poste « client »** | Jouer le rôle d'un poste d'entreprise : rejoindre un domaine, tester les partages, le Bureau à distance, les commandes Windows |
| 🍎 **Mac** | **Le testeur multi-OS** (bonus) | Vérifier qu'un partage / SSH fonctionne depuis macOS |

## Pourquoi cette répartition ?

- Le **PC de bureau** a la RAM et le CPU pour faire tourner plusieurs VM → c'est ton
  **banc d'essai**. Les TP du [track administration](../administration/) vivent ici.
- Le **laptop Windows** représente **ce que tes futurs clients utilisent** (90 % de postes
  Windows). Beaucoup de « 🔧 À essayer » des cours sont des commandes Windows → fais-les ici.
- Le **Mac** confirme qu'une solution marche **partout** (un partage de fichiers doit être
  accessible depuis les 3 mondes).

## 3 réglages malins avant de commencer

1. **Tu as déjà une VM Windows Server ?** Réutilise-la pour le [TP02](../administration/tp/tp02-installer-windows-server.md)
   au lieu de réinstaller — mais **fais un *snapshot* AVANT** de la promouvoir en contrôleur
   de domaine (tu pourras revenir en arrière si besoin).
2. **Ajoute une VM Ubuntu Server** sur le PC de bureau pour le
   [TP05](../administration/tp/tp05-ubuntu-server-ssh.md) (partie Linux).
3. **Mets toutes les machines sur le même réseau** (même box / même plage IP) pour qu'elles
   se voient — indispensable pour la Partie 2 ci-dessous.

> ✅ **Résumé** : PC de bureau = labo · laptop Windows = poste client · Mac = tests croisés.

---

# Partie 2 — Partager un dossier entre tes machines

**Oui, c'est possible** entre Linux, Windows et Mac — et c'est exactement le cas réel d'une
TPE mixte. Tout le monde parle le même langage : **SMB** (le partage de fichiers de
Windows). Sous Linux, c'est **Samba** qui le parle.

```
   🐧 Linux (Samba) ⇄ 🪟 Windows (SMB) ⇄ 🍎 Mac (SMB)
```

> 📄 Antisèche rapide : [fiche partage multi-OS](../fiches-memo/fiche-partage-multi-os.md).
> Ci-dessous, la version **pas-à-pas** avec un exercice.

---

## 🎯 Scénario d'entraînement

On va partager un dossier **« Devis »** depuis une machine, et y accéder depuis une autre.
Fais-le dans les deux sens pour bien comprendre. (C'est la pratique du
[cours 06](../cours/06-partage-fichiers-imprimantes/).)

---

## Cas A — Partager depuis **Windows**, accéder depuis Linux/Mac

### Étape 1 — Partager le dossier (sur Windows)
1. Crée un dossier `Devis`.
2. Clic droit → **Propriétés** → onglet **Partage** → **Partager…**
3. Choisis **qui** peut accéder et **le niveau** (Lecture, ou Lecture/écriture).
4. Note le **nom de la machine** ou son **IP** (`ipconfig` → *Adresse IPv4*).

### Étape 2 — Accéder au partage
- **Depuis Linux Mint** : ouvre le gestionnaire de fichiers (Nemo) → dans la barre
  d'adresse, tape :
  ```
  smb://192.168.1.30/Devis
  ```
  *(remplace par l'IP du PC Windows)*. Saisis l'identifiant/mot de passe Windows.
- **Depuis Mac** : Finder → menu **Aller → Se connecter au serveur** → `smb://192.168.1.30/Devis`.

✅ Tu dois voir (et selon les droits, modifier) les fichiers du dossier. Bravo !

---

## Cas B — Partager depuis **Linux Mint**, accéder depuis Windows/Mac

### Étape 1 — Installer Samba (une seule fois)
Ouvre un terminal :
```bash
sudo apt update
sudo apt install samba
```

### Étape 2 — Créer ton utilisateur Samba
```bash
sudo smbpasswd -a tonuser
```
*(choisis un mot de passe — il peut différer de ton mot de passe de session).*

### Étape 3 — Partager le dossier
**Méthode simple (clic droit)** :
1. `sudo apt install nemo-share` (si pas déjà là), puis **déconnexion/reconnexion**.
2. Clic droit sur le dossier `Devis` → **Options de partage** → coche **« Partager ce
   dossier »**, autorise l'écriture si besoin.

**Méthode manuelle (fichier de conf)** — si tu préfères :
```bash
sudo nano /etc/samba/smb.conf
```
Ajoute à la fin :
```ini
[Devis]
   path = /home/tonuser/Devis
   valid users = tonuser
   read only = no
```
Puis redémarre Samba :
```bash
sudo systemctl restart smbd
```

### Étape 4 — Accéder au partage
- **Depuis Windows** : explorateur de fichiers → barre d'adresse :
  ```
  \\192.168.1.50\Devis
  ```
  *(remplace par l'IP de ta machine Mint — trouve-la avec `ip a`)*.
- **Depuis Mac** : Finder → **Aller → Se connecter au serveur** → `smb://192.168.1.50/Devis`.

✅ Le dossier Linux apparaît sur Windows/Mac. Tu partages dans les deux sens !

---

## 🔗 Bonus — Monter le partage en permanence (Linux)
Pour qu'un partage distant apparaisse comme un dossier local :
```bash
sudo apt install cifs-utils
sudo mkdir /mnt/devis
sudo mount -t cifs //192.168.1.30/Devis /mnt/devis -o username=tonuser
```
*(Pour un montage automatique au démarrage, on ajoute une ligne dans `/etc/fstab`.)*

## 🧩 Juste entre ton host et tes VM (VirtualBox)
Si tu veux seulement échanger des fichiers entre **Mint (host)** et une **VM** (sans passer
par le réseau), utilise **VirtualBox → Configuration → Dossiers partagés** (nécessite les
**Additions invité**). C'est pratique pour le labo, mais c'est **différent** du partage
réseau SMB du cours 06.

---

## 🩺 Ça ne marche pas ? (dépannage, cf. cours 11)
- **`ping`** l'autre machine : répond-elle ? Sont-elles sur **le même réseau** (même plage IP) ?
- **Pare-feu** : sur Windows, autorise « Partage de fichiers et d'imprimantes » ; sur Linux,
  `sudo ufw allow samba` (si UFW est actif).
- **Identifiants** : le mot de passe **Samba** (créé à l'étape B2) n'est pas celui de ta
  session Linux.
- **Droits** : rappelle-toi que **le plus restrictif gagne** (partage ⨉ droits du dossier).

---

## ✅ Ce qu'il faut retenir

1. Répartis tes machines **par rôle** : labo (PC puissant) · poste client (Windows) · tests
   (Mac).
2. Linux, Windows et Mac partagent des dossiers via **SMB** (**Samba** côté Linux).
3. Pense toujours **réseau commun + droits + pare-feu** quand un partage ne marche pas.

---

⬅️ [Retour au démarrage](README.md) · 🧭 [Parcours](../PARCOURS.md) · 📄 [Fiche partage multi-OS](../fiches-memo/fiche-partage-multi-os.md)
