# TP01 — Ta première adresse IP

🎯 **Objectif** : donner une adresse IP à un PC dans Packet Tracer.
🕐 Durée : ~15 min · Prérequis : cours 02 (adresses IP).

---

## 🧱 Ce que tu vas construire

Juste **un seul PC**, à qui tu vas donner une adresse. On commence tout petit.

```
   💻 PC0   (adresse : 192.168.1.10)
```

---

## 🪜 Étapes

### 1. Ajouter un PC

- En bas à gauche, clique sur la catégorie **« End Devices »** (terminaux).
- **Glisse un « PC »** sur l'espace de travail. Il s'appelle `PC0`.

### 2. Ouvrir sa configuration

- Clique sur `PC0`.
- Va dans l'onglet **« Desktop »**.
- Clique sur **« IP Configuration »**.

### 3. Donner une adresse IP (en manuel)

- Coche **« Static »** (adresse fixe, posée à la main).
- Renseigne :
  - **IP Address** : `192.168.1.10`
  - **Subnet Mask** : `255.255.255.0` (il se remplit souvent tout seul)
- Laisse le reste vide pour l'instant.

> 💡 Rappel cours 02 : `192.168.1` = le quartier, `.10` = le numéro de ce PC.

### 4. Vérifier

- Toujours dans **Desktop**, ouvre **« Command Prompt »**.
- Tape `ipconfig` et Entrée.
- Tu dois voir ton adresse `192.168.1.10`. 🎉

---

## ✅ Réussite

Tu as réussi si `ipconfig` affiche bien `192.168.1.10`. Tu viens de faire ce qu'un
technicien fait tous les jours : **attribuer une IP à une machine**.

## 🧠 Pour aller plus loin

Change l'adresse en `192.168.1.50`, revérifie avec `ipconfig`. Essaie une adresse
invalide (ex : `192.168.1.300`) : que se passe-t-il ? (300 n'existe pas, le max est
255 !)

> 💾 Enregistre ton fichier (`Ctrl+S`) sous le nom `tp01.pkt`.

---

➡️ [TP02 — Relier deux PC](tp02-relier-deux-pc.md)
