# TP03 — Ajouter un routeur et un serveur

🎯 **Objectif** : ajouter une « box » (routeur) et un serveur de fichiers au réseau.
🕐 Durée : ~25 min · Prérequis : TP02, cours 03/04/06/07.

---

## 🧱 Ce que tu vas construire

```
        [ Routeur ]  (la "box" : 192.168.1.1)
             │
        [ Switch ]
         │  │  │
      💻PC0 💻PC1  💾 Serveur (192.168.1.100)
```

---

## 🪜 Étapes

### 1. Repartir du TP02

Ouvre `tp02.pkt` (ou reconstruis 2 PC + 1 switch comme au TP02).

### 2. Ajouter un routeur (la box)

- Catégorie **« Network Devices » → « Routers »**, glisse un routeur (ex : `1941`).
  Il s'appelle `Router0`.
- Relie `Router0` au `Switch0` avec un câble **« Copper Straight-Through »**
  (port `GigabitEthernet0/0` du routeur → un port libre du switch).

### 3. Donner une IP au routeur (la passerelle)

- Clique sur `Router0` → onglet **« Config »**.
- À gauche, clique sur l'interface reliée au switch (ex : `GigabitEthernet0/0`).
- Renseigne :
  - **IP Address** : `192.168.1.1`
  - **Subnet Mask** : `255.255.255.0`
- **Coche « On »** pour activer le port (Port Status).

> 💡 `192.168.1.1` = l'adresse de la box = la **passerelle** (rappel cours 04).

### 4. Ajouter un serveur de fichiers

- `End Devices` → glisse un **« Server »** : `Server0`.
- Relie-le au `Switch0` (câble droit).
- `Server0` → Desktop → IP Configuration → Static :
  - IP `192.168.1.100`, masque `255.255.255.0`
  - **Default Gateway** : `192.168.1.1` (la box !)

### 5. Indiquer la passerelle aux PC

Pour que les PC puissent un jour sortir du réseau, indique-leur la passerelle :

- `PC0` et `PC1` → IP Configuration → **Default Gateway** : `192.168.1.1`

### 6. Tester

Depuis `PC0` → Command Prompt :
- `ping 192.168.1.1` → la **box** répond ?
- `ping 192.168.1.100` → le **serveur** répond ?

Les deux répondent → 🎉 ton réseau a maintenant une box et un serveur.

---

## ✅ Réussite

Tous les `ping` répondent. Tu as un vrai petit réseau structuré : routeur +
switch + postes + serveur. C'est le squelette d'un réseau de TPE.

## 🧠 Pour aller plus loin

Sur `Server0`, va dans l'onglet **« Services »** et explore le menu de gauche :
**DHCP**, **DNS**, **HTTP**… Tu verras bientôt à quoi ils servent (TP04).

> 💾 Enregistre sous `tp03.pkt`.

---

⬅️ [TP02](tp02-relier-deux-pc.md) · ➡️ [TP04 — Réseau TPE complet](tp04-reseau-tpe-complet.md)
