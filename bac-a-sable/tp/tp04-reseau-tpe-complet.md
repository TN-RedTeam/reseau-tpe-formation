# TP04 — Monter un réseau TPE complet

🎯 **Objectif** : construire un réseau TPE réaliste : routeur + **5 PC** + serveur,
avec **DHCP automatique**. 🕐 Durée : ~40 min · Prérequis : TP03, cours 03.

> C'est le TP « grand format ». Prends ton temps, fais une pause si besoin. 💪

---

## 🧱 Ce que tu vas construire

```
                 [ Routeur ] 192.168.1.1  (la box)
                       │
                  [ Switch ]
     ┌──────┬──────┬──────┬──────┬──────────┐
   💻PC0  💻PC1  💻PC2  💻PC3  💻PC4     💾 Serveur (192.168.1.100)
   (adresses données AUTOMATIQUEMENT par le DHCP)
```

Les 5 PC ne recevront **pas** d'adresse à la main : c'est le **serveur DHCP** qui
les distribue (rappel cours 03). Comme dans une vraie TPE.

---

## 🪜 Étapes

### 1. Poser le matériel

- 1 **routeur** (`Router0`), 1 **switch** (`Switch0`), **5 PC** (`PC0`→`PC4`),
  1 **serveur** (`Server0`).
- Relie tout au switch avec des câbles **« Copper Straight-Through »** (routeur,
  serveur et les 5 PC sur des ports différents du switch).

### 2. Configurer le routeur (la box)

- `Router0` → Config → interface reliée au switch :
  - IP `192.168.1.1`, masque `255.255.255.0`, Port Status **On**.

### 3. Configurer le serveur

- `Server0` → Desktop → IP Configuration → Static :
  - IP `192.168.1.100`, masque `255.255.255.0`, gateway `192.168.1.1`.

### 4. Activer le DHCP sur le serveur ⭐

- `Server0` → onglet **« Services »** → menu **« DHCP »**.
- Mets **Service : On**.
- Renseigne le « pool » (la plage d'adresses à distribuer) :
  - **Default Gateway** : `192.168.1.1`
  - **DNS Server** : `192.168.1.100` (notre serveur)
  - **Start IP Address** : `192.168.1.20`
  - **Subnet Mask** : `255.255.255.0`
  - **Maximum Users** : `50`
- Clique sur **« Save »**.

> 💡 Tu viens de créer le « gardien de parking » : il distribuera les adresses à
> partir de `.20`.

### 5. Mettre les 5 PC en automatique (DHCP)

Pour **chaque** PC (`PC0` à `PC4`) :
- Desktop → IP Configuration → coche **« DHCP »** (au lieu de Static).
- Attends le message **« DHCP request successful »**.
- L'adresse s'affiche toute seule (ex : `192.168.1.20`, `.21`, …). 🎉

### 6. Tester tout le réseau

> ⚠️ **Mode `Realtime`** (bas à droite) pour que les `ping` répondent tout de suite.

Depuis `PC0` → Command Prompt :
- `ipconfig` → tu as reçu une IP automatiquement ? ✅
- `ping 192.168.1.1` → la box répond ? ✅
- `ping 192.168.1.100` → le serveur répond ? ✅
- `ping` l'adresse d'un autre PC (vue dans son `ipconfig`) → il répond ? ✅

---

## ✅ Réussite

Les 5 PC ont reçu une adresse **automatiquement** et tout le monde communique. Tu
viens de monter l'ossature d'un **vrai réseau de TPE**. Bravo, c'est une grande
étape ! 🏆

## 🧠 Pour aller plus loin (optionnel)

- Sur `Server0` → Services → **HTTP** : laisse-le activé. Depuis un PC → Desktop →
  **Web Browser**, tape `192.168.1.100` : tu vois la page web servie par ton serveur !
- Renomme tes PC de façon réaliste (`PC-ACCUEIL`, `PC-COMPTA`…) via l'onglet Config.

> 💾 Enregistre sous `tp04.pkt` — tu réutiliseras ce réseau dans les TP suivants.

---

⬅️ [TP03](tp03-ajouter-routeur-serveur.md) · ➡️ [TP05 — Accès distant](tp05-acces-distant.md)
