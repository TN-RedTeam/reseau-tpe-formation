# ⌨️ Fiche-mémo — Commandes d'administration

Les commandes les plus utiles, **Windows (PowerShell)** et **Linux (terminal)** côte à
côte. À garder sous la main pendant les TP.

## 👤 Utilisateurs & groupes

| Objectif | Windows (PowerShell) | Linux |
|---|---|---|
| Qui suis-je | `whoami` | `whoami` / `id` |
| Lister les comptes | `Get-LocalUser` | `cat /etc/passwd` |
| Lister les groupes | `Get-LocalGroup` | `getent group` |
| Créer un utilisateur | `New-LocalUser` / `New-ADUser` (domaine) | `sudo adduser bob` |
| Ajouter à un groupe | `Add-LocalGroupMember` / `Add-ADGroupMember` | `sudo usermod -aG grp bob` |
| Désactiver un compte | `Disable-ADAccount` | `sudo usermod -L bob` |

## 📁 Droits & fichiers

| Objectif | Windows | Linux |
|---|---|---|
| Voir les droits | onglet **Sécurité** / `icacls dossier` | `ls -l` |
| Changer les droits | `icacls` / interface NTFS | `chmod 640 fichier` |
| Changer le propriétaire | `icacls /setowner` | `sudo chown bob:grp fichier` |

## ⚙️ Services

| Objectif | Windows | Linux |
|---|---|---|
| État d'un service | `Get-Service nom` | `systemctl status nom` |
| Démarrer / arrêter | `Start-Service` / `Stop-Service` | `sudo systemctl start/stop nom` |
| Redémarrer | `Restart-Service nom` | `sudo systemctl restart nom` |
| Démarrage auto | `Set-Service -StartupType Automatic` | `sudo systemctl enable nom` |

## 🔄 Mises à jour

| Windows | Linux (Debian/Ubuntu) |
|---|---|
| Windows Update / WSUS / RMM | `sudo apt update && sudo apt upgrade` |

## 🌐 Réseau & accès distant

| Objectif | Windows | Linux |
|---|---|---|
| Voir l'IP | `ipconfig` | `ip a` |
| Tester une liaison | `ping`, `Test-NetConnection` | `ping`, `ss -tuln` |
| Se connecter à distance | **RDP** (Bureau à distance) | **SSH** : `ssh user@ip` |

## 🧩 Active Directory / GPO (Windows)

| Objectif | Commande |
|---|---|
| Forcer l'application d'une GPO | `gpupdate /force` |
| Voir les GPO appliquées | `gpresult /r` |
| Console utilisateurs AD | `dsa.msc` (ADUC) |
| Console GPO | `gpmc.msc` (GPMC) |

> 💡 Règle d'or : **teste sur une machine/OU de test avant de déployer** sur tout le parc.

⬅️ [Fiches-mémo](README.md) · [Track administration](../administration/)
