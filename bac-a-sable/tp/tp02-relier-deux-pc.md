# TP02 — Relier deux PC

🎯 **Objectif** : faire communiquer **deux PC** via un switch, et tester avec `ping`.
🕐 Durée : ~20 min · Prérequis : TP01, cours 04 (switch).

---

## 🧱 Ce que tu vas construire

```
   💻 PC0 ───┐
            [ Switch ]
   💻 PC1 ───┘

   PC0 : 192.168.1.10
   PC1 : 192.168.1.11
```

---

## 🪜 Étapes

### 1. Poser le matériel

- Ajoute **2 PC** (`End Devices` → PC) : `PC0` et `PC1`.
- Ajoute **1 switch** : catégorie **« Network Devices » → « Switches »**, prends un
  modèle simple (ex : `2960`). Il s'appelle `Switch0`.

### 2. Relier avec des câbles

- Clique sur la catégorie **« Connections »** (l'éclair ⚡).
- Choisis le câble **« Copper Straight-Through »** (câble droit cuivre).
- Clique sur `PC0` → choisis `FastEthernet0`, puis clique sur `Switch0` → choisis un
  port libre (ex : `FastEthernet0/1`).
- Recommence pour relier `PC1` au `Switch0` (sur un autre port).

> 💡 Des points **verts** aux extrémités des câbles = la liaison physique est bonne.

### 3. Configurer les IP

- `PC0` → Desktop → IP Configuration → Static :
  - IP `192.168.1.10`, masque `255.255.255.0`
- `PC1` → Desktop → IP Configuration → Static :
  - IP `192.168.1.11`, masque `255.255.255.0`

> ⚠️ Même « quartier » (`192.168.1`), numéros différents (`.10` et `.11`). Sinon ils
> ne pourront pas se parler (rappel cours 02).

### 4. Tester avec ping

> ⚠️ **Mets-toi en mode `Realtime`** (bas à droite) pour que le `ping` réponde tout de
> suite. En `Simulation`, rien ne s'affiche tant que tu n'appuies pas sur Play ▶.

- `PC0` → Desktop → Command Prompt.
- Tape : `ping 192.168.1.11`
- Si tu vois **« Reply from 192.168.1.11 »** → 🎉 les deux PC communiquent !

---

## ✅ Réussite

Le `ping` reçoit des réponses (« Reply from… »). Tes deux machines sont sur le même
réseau local et se parlent, à travers le switch (la « multiprise réseau »).

## 🧠 Pour aller plus loin

- Mets volontairement `PC1` dans un **autre quartier** : `192.168.**2**.11`. Refais
  le ping depuis PC0. Ça échoue (« Request timed out »), car ils ne sont plus dans le
  même quartier. Remets `192.168.1.11` → ça remarche. Tu viens de comprendre
  pourquoi le « quartier » doit être identique !

> 💾 Enregistre sous `tp02.pkt`.

---

⬅️ [TP01](tp01-premiere-ip.md) · ➡️ [TP03 — Routeur + serveur](tp03-ajouter-routeur-serveur.md)
