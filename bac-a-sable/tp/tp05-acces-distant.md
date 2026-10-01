# TP05 — Simuler un accès distant

🎯 **Objectif** : comprendre comment un PC **de l'extérieur** rejoint le réseau de la
TPE, et visualiser le rôle de la box comme frontière.
🕐 Durée : ~30 min · Prérequis : TP04, cours 10 (VPN/accès distant).

> ⚠️ Un vrai VPN ne se configure pas « clic-clic » dans Packet Tracer de base. Ici,
> on **simule le principe** : un site « maison » séparé, relié au bureau par un
> routeur, pour bien **voir la frontière intérieur/extérieur**. L'important est la
> compréhension, pas la techno exacte.

---

## 🧱 Ce que tu vas construire

```
   🏢 BUREAU (TPE)                         🏠 MAISON (télétravail)
   [ Routeur bureau ]───[ lien "internet" ]───[ Routeur maison ]
        │                                             │
     [ Switch ]                                    💻 PC-Teletravail
   💻x5  💾 Serveur
```

Deux « lieux », reliés entre eux. On vérifie que le PC de la maison peut atteindre
le serveur du bureau — comme le ferait un VPN.

---

## 🪜 Étapes (version simplifiée)

### 1. Repartir du TP04

Ouvre `tp04.pkt`. Tu as déjà le **bureau** complet (routeur + switch + 5 PC + serveur).

Pour alléger, tu peux garder seulement **2 PC** côté bureau : ça suffit pour le test.

### 2. Créer le « côté maison »

- Ajoute un **2e routeur** : `Router-Maison`.
- Ajoute **1 PC** : `PC-Teletravail`, relié (switch ou direct) à `Router-Maison`.

### 3. Relier les deux routeurs (le « lien internet »)

- Relie `Router0` (bureau) à `Router-Maison` via leurs interfaces **Gigabit** avec un
  câble **« Copper Cross-Over »** (câble croisé, routeur↔routeur).
- Configure ce lien dans un **autre quartier** (c'est « internet » entre les deux) :
  - `Router0` interface du lien : `203.0.113.1` / `255.255.255.0`, Port **On**.
  - `Router-Maison` interface du lien : `203.0.113.2` / `255.255.255.0`, Port **On**.
- Côté maison, donne au PC : IP `192.168.2.10`, masque `255.255.255.0`, gateway
  `192.168.2.1` (l'interface de `Router-Maison` côté maison, à configurer aussi).

### 4. Apprendre aux routeurs le chemin de l'autre (routes statiques)

Pour que les deux réseaux se trouvent, ajoute une **route statique** sur chaque
routeur (onglet **Config → Static Routing** ou CLI) :

- Sur `Router0` : vers le réseau `192.168.2.0 / 255.255.255.0` via `203.0.113.2`.
- Sur `Router-Maison` : vers le réseau `192.168.1.0 / 255.255.255.0` via `203.0.113.1`.

> 💡 Une **route**, c'est juste « pour aller à tel quartier, passe par là ». On
> indique au gardien le chemin vers l'autre immeuble.

### 5. Tester l'accès distant

Depuis `PC-Teletravail` → Command Prompt :
- `ping 192.168.1.100` (le serveur du bureau).
- Réponse ✅ → le PC de la maison atteint le serveur du bureau, à travers
  « internet », comme le ferait un VPN. 🎉

---

## ✅ Réussite

Le PC « maison » atteint le serveur « bureau ». Tu as visualisé la **frontière
intérieur/extérieur** et le fait qu'un accès distant **relie deux réseaux**.

## 🧠 À retenir côté réalité

Dans une vraie TPE, on ne poserait **pas** de routes manuelles sur internet : on
monterait un **VPN** (box, NAS, ou Tailscale) qui crée le tunnel sécurisé
automatiquement (cours 10). Ce TP illustre le **principe** ; le VPN, c'est la
version **sécurisée et chiffrée** de ce que tu viens de faire.

> 💾 Enregistre sous `tp05.pkt`.

---

⬅️ [TP04](tp04-reseau-tpe-complet.md) · ➡️ [TP06 — Scénario de panne](tp06-scenario-panne.md)
