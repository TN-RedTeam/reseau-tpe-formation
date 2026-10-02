# 🔁 Fiche-mémo — Partage de dossiers Linux ↔ Windows ↔ Mac

Le protocole commun = **SMB** (le partage de fichiers de Windows). Sous Linux, c'est
**Samba** qui le parle. Résultat : les 3 mondes peuvent échanger des dossiers.

```
   🐧 Linux (Samba) ⇄ 🪟 Windows (SMB) ⇄ 🍎 Mac (SMB)
                    tous parlent SMB
```

---

## 🪟 Windows → accéder depuis Linux / Mac
1. **Windows** : clic droit sur le dossier → *Propriétés → Partage* → **Partager**
   (choisir qui + lecture/écriture).
2. **Linux (Mint/Nemo)** : barre d'adresse → `smb://IP-windows/NomPartage`
   (ex : `smb://192.168.1.30/Devis`).
3. **Mac (Finder)** : *Aller → Se connecter au serveur* → `smb://IP-windows/NomPartage`.

## 🐧 Linux → accéder depuis Windows / Mac
1. Installer Samba : `sudo apt install samba`
2. Créer un utilisateur Samba : `sudo smbpasswd -a tonuser`
3. Partager le dossier :
   - **Simple** : installer `nemo-share`, puis clic droit sur le dossier → *Options de
     partage* → cocher « Partager ce dossier ».
   - **Manuel** : éditer `/etc/samba/smb.conf`, ajouter :
     ```ini
     [Partage]
       path = /home/tonuser/Partage
       valid users = tonuser
       read only = no
     ```
     puis `sudo systemctl restart smbd`.
4. **Windows** : explorateur → `\\IP-linux\Partage`
   **Mac** : Finder → `smb://IP-linux/Partage`

## 🔗 Monter un partage en permanence (Linux)
```bash
sudo apt install cifs-utils
sudo mount -t cifs //192.168.1.30/Devis /mnt/devis -o username=tonuser
```
*(Pour un montage au démarrage : ajouter une ligne dans `/etc/fstab`.)*

---

## 🧩 Dans ton labo VirtualBox (host ↔ VM)
Pour juste échanger des fichiers entre ton **host Mint** et une **VM** (pratique, hors
cours 06) : VirtualBox → *Configuration → Dossiers partagés* (nécessite les **Additions
invité**). C'est propre à VirtualBox, différent du partage **réseau** SMB du cours 06.

## ⚠️ Les droits priment toujours
- Qui accède ? Lecture seule ou écriture ? (rappel [cours 06](../cours/06-partage-fichiers-imprimantes/))
- Côté Linux : droits `rwx` + Samba ([admin 07](../administration/07-linux-serveur-bases.md)).
- Côté Windows : droits **NTFS** + partage ([admin 06](../administration/06-droits-ntfs-partages.md)).
- Règle d'or : **le plus restrictif gagne** quand partage et droits se combinent.

## 🩺 Ça ne marche pas ?
- `ping` l'autre machine (même réseau ? cf. [cours 11](../cours/11-diagnostic-depannage/)).
- Pare-feu : autoriser le partage de fichiers (Windows) / ouvrir Samba (`sudo ufw allow samba`).
- Vérifier le **nom d'utilisateur/mot de passe** Samba (différent du mot de passe Linux).

⬅️ [Fiches-mémo](README.md)
