# Administration 07 — Linux serveur, les bases

🕐 Lecture : ~8 min · Niveau : intermédiaire

> Beaucoup d'équipements d'un réseau tournent sous Linux **sans que tu le saches** : NAS,
> box, pare-feu, Raspberry Pi, hyperviseurs, serveurs web. Savoir en piloter un est
> indispensable.

---

## 🐧 L'analogie du quotidien

Linux en serveur, c'est souvent **sans tableau de bord graphique** : tu conduis « aux
instruments », avec le **terminal** (la ligne de commande). Ça fait peur au début, mais
c'est comme apprendre quelques **phrases types** dans une langue : avec 15 commandes, tu
fais 90 % du travail quotidien.

> 💡 Pas d'écran, pas de souris : on s'y connecte **à distance en SSH** (console
> sécurisée). C'est la norme pour les serveurs Linux.

---

## 🔑 Se connecter : SSH

**SSH** = *Secure Shell* : une **télécommande sécurisée** pour piloter un serveur à
distance en ligne de commande.

```bash
ssh alice@192.168.1.50      # se connecter au serveur en tant qu'alice
```

> 🔒 Bonne pratique : se connecter avec une **clé SSH** (plus sûr qu'un mot de passe) et
> **désactiver la connexion directe de root**. On en reparle au module 10.

---

## 🗺️ Se repérer et naviguer

| Commande | Ce qu'elle fait |
|---|---|
| `pwd` | Où suis-je ? (dossier courant) |
| `ls -l` | Lister le contenu (avec détails/droits) |
| `cd /chemin` | Changer de dossier |
| `cat fichier` | Afficher un fichier |
| `nano fichier` | Éditer un fichier (éditeur simple) |

> 💡 Tout est **fichier** sous Linux, y compris la configuration : administrer, c'est
> souvent **éditer des fichiers de config** dans `/etc`.

---

## 👤 Utilisateurs & droits (le cœur)

```bash
whoami                     # qui suis-je
id alice                   # groupes de l'utilisateur alice
sudo adduser bob           # créer l'utilisateur bob
sudo usermod -aG sudo bob  # donner à bob le droit d'administrer (groupe sudo)
```

**`sudo`** = « faire cette commande **en administrateur** » (l'équivalent du « Exécuter en
tant qu'administrateur » de Windows). On travaille en utilisateur normal, et on préfixe par
`sudo` **seulement** les actions d'admin (moindre privilège, rappel module 01).

### Les droits de fichiers (le fameux `rwx`)

```bash
ls -l rapport.txt
# -rw-r--r-- 1 alice compta ... rapport.txt
```

Ça se lit : **propriétaire** (`alice`) a `rw` (lecture+écriture), le **groupe** (`compta`)
a `r` (lecture), **les autres** ont `r`. On modifie avec :

```bash
chmod 640 rapport.txt        # régler les droits (proprio rw, groupe r, autres rien)
chown alice:compta rapport.txt  # changer propriétaire et groupe
```

> 💡 C'est l'équivalent Linux des droits NTFS (module 06) : **qui** possède, **quel
> groupe**, et **quoi** (lire/écrire/exécuter).

---

## ⚙️ Les services (démarrer, arrêter, surveiller)

Un **service** (ou *daemon*) est un programme qui tourne en fond (serveur web, SSH, base de
données…). On les pilote avec **`systemctl`** :

```bash
sudo systemctl status ssh     # état du service SSH
sudo systemctl restart ssh    # redémarrer
sudo systemctl enable ssh     # démarrage automatique au boot
```

---

## 🔄 Mises à jour (Debian/Ubuntu)

```bash
sudo apt update && sudo apt upgrade   # mettre à jour la liste puis les paquets
```

> 💡 `apt` est le « magasin d'applications » en ligne de commande. (Sur d'autres familles
> Linux : `dnf` ou `yum`.)

---

## ✅ Ce qu'il faut retenir

1. Un serveur Linux se pilote **en ligne de commande, à distance via SSH** ; ~15 commandes
   suffisent au quotidien.
2. **`sudo`** = agir en admin ; les droits de fichiers se lisent **`rwx`** (proprio /
   groupe / autres) et se règlent avec `chmod` / `chown`.
3. Les **services** se gèrent avec **`systemctl`** ; les mises à jour avec **`apt`** (ou
   `dnf`).

## 🔧 À essayer

Pas besoin d'installer Linux tout de suite : au [TP05](tp/tp05-ubuntu-server-ssh.md) tu
montes un serveur Ubuntu en VM. **Mais dès maintenant**, si tu as Windows 10/11, tu peux
installer **WSL** (`wsl --install` dans PowerShell admin) : ça te donne un vrai terminal
Linux en 5 min. Essaie-y `pwd`, `ls -l`, `whoami`, `id`.

---

⬅️ [Administration 06](06-droits-ntfs-partages.md) · ➡️ [Administration 08 — DHCP & DNS côté serveur](08-dhcp-dns-serveur.md)
