# 🧪 Le bac à sable — ton terrain d'entraînement

Lire, c'est bien. **Pratiquer, c'est indispensable.** Ce dossier est là pour que tu
**manipules un vrai réseau** sans risque et sans dépenser un centime.

---

## 🤔 Trois options possibles

Il existe 3 façons de s'entraîner. Voici le comparatif honnête :

### Option A — Un simulateur (logiciel sur ton PC)

Tu construis des réseaux virtuels (routeurs, PC, câbles) sur ton écran.

- **Outils** : **Cisco Packet Tracer** (gratuit) ou **GNS3** (plus avancé).
- ✅ **Avantages** : gratuit, aucun matériel, tu peux tout casser sans risque, tu
  recommences à l'infini, tu vois les paquets circuler.
- ⚠️ **Inconvénients** : il faut créer un compte (Packet Tracer) ; ça reste une
  simulation (pas 100 % identique au réel).
- 💰 **Coût** : **0 €**.

### Option B — Des outils en ligne (dans le navigateur)

Des bacs à sable réseau accessibles depuis un site web, sans rien installer.

- **Outils** : la **démo DSM de Synology** (pour s'exercer sur un NAS), des
  simulateurs de sous-réseaux en ligne, des labos Cisco en ligne.
- ✅ **Avantages** : rien à installer, immédiat.
- ⚠️ **Inconvénients** : moins complet, on ne construit pas un vrai réseau de A à Z.
- 💰 **Coût** : **0 €**.

### Option C — Un mini-réseau réel (ton propre matériel)

Tu t'entraînes sur **ta box + tes PC**, et éventuellement un vieux PC recyclé en
NAS (**TrueNAS** / **OpenMediaVault**) ou un **Raspberry Pi**.

- ✅ **Avantages** : 100 % réel, super formateur, tu touches du vrai matériel.
- ⚠️ **Inconvénients** : tu risques de couper internet à la maison le temps des
  tests ; un vieux PC / Raspberry Pi est utile pour aller loin.
- 💰 **Coût** : **0 €** (avec ta box) à **~50-100 €** (Raspberry Pi ou disques).

---

## 🏆 Ma recommandation pour débuter

> **Commence par l'Option A : Cisco Packet Tracer.**

Pourquoi ? Parce que c'est **gratuit**, que tu peux **tout construire et tout
casser sans conséquence**, et que c'est **l'outil de référence** pour apprendre le
réseau. Tu montes un réseau TPE complet (routeur + 5 PC + serveur) sur ton écran,
tranquillement.

Puis, quand tu seras à l'aise, **complète avec l'Option C** (ton vrai réseau) pour
le contact avec le matériel réel. Les deux se complètent parfaitement.

👉 La suite de cette page t'installe **Packet Tracer** pas à pas.

---

## 🛠️ Installer Cisco Packet Tracer (pas à pas)

### Étape 1 — Créer un compte gratuit

Packet Tracer est gratuit, mais il faut un compte Cisco « Networking Academy ».

1. Va sur **https://www.netacad.com**
2. Cherche le cours gratuit **« Getting Started with Cisco Packet Tracer »**
   (ou « Introduction to Packet Tracer »).
3. Clique sur **S'inscrire / Enroll** (gratuit) et crée ton compte.

> 💡 C'est 100 % gratuit. Le cours en lui-même est un bonus sympa pour débuter.

### Étape 2 — Télécharger le logiciel

1. Une fois connecté sur netacad.com, va dans la section **Ressources →
   Télécharger Packet Tracer**.
2. Choisis la version pour ton système (**Windows**, **macOS** ou **Linux**).
3. Télécharge le fichier d'installation.

### Étape 3 — Installer

- **Windows** : double-clique sur le fichier `.exe`, accepte la licence, clique
  « Suivant » jusqu'au bout (les options par défaut conviennent).
- **macOS** : ouvre le `.dmg` et glisse Packet Tracer dans Applications.
- **Linux** : suis les instructions du `.deb` fourni.

### Étape 4 — Première ouverture

1. Lance Packet Tracer.
2. Connecte-toi avec ton compte netacad (le même qu'à l'étape 1).
3. Tu arrives sur un **espace de travail vide**. 🎉 C'est ta table de montage.

### Étape 5 — Découvrir l'interface (2 minutes)

```
 ┌───────────────────────────────────────────┐
 │   Espace de travail (ton réseau)           │
 │                                            │
 │                                            │
 ├───────────────────────────────────────────┤
 │ [Routeurs][Switchs][PC][Câbles] ← en bas   │  ← la "boîte à matériel"
 └───────────────────────────────────────────┘
```

- En **bas à gauche** : les **catégories de matériel** (routeurs, switchs,
  terminaux/PC, connexions/câbles).
- Tu **glisses** un appareil sur l'espace de travail pour l'ajouter.
- Tu utilises l'outil **câble** (l'éclair ⚡ ou la catégorie « Connections ») pour
  relier les appareils.

> ✅ Tu es prêt ! Tu peux commencer les TP ci-dessous.

---

## 📂 Les TP (travaux pratiques) progressifs

Dans l'ordre, du plus simple au plus complet. Dossier [`tp/`](tp/).

| TP | Titre | Tu apprends à… |
|---|---|---|
| [TP01](tp/tp01-premiere-ip.md) | Ta première IP | Donner une adresse IP à un PC |
| [TP02](tp/tp02-relier-deux-pc.md) | Relier deux PC | Faire communiquer 2 PC via un switch |
| [TP03](tp/tp03-ajouter-routeur-serveur.md) | Routeur + serveur | Ajouter la box et un serveur |
| [TP04](tp/tp04-reseau-tpe-complet.md) | Réseau TPE complet | Monter routeur + 5 PC + serveur + DHCP |
| [TP05](tp/tp05-acces-distant.md) | Accès distant | Simuler un accès depuis l'extérieur |
| [TP06](tp/tp06-scenario-panne.md) | Scénario de panne | Diagnostiquer et réparer une panne |

---

## 🧰 Pour l'Option C (ton vrai réseau), plus tard

Quand tu voudras t'entraîner sur du matériel réel :

- **TrueNAS** (truenas.com) ou **OpenMediaVault** (openmediavault.org) : transforment
  un vieux PC en NAS, gratuitement.
- **Raspberry Pi** : un mini-ordinateur (~50 €) parfait pour tester serveur de
  fichiers, Pi-hole (filtrage DNS), VPN, etc.
- ⚠️ Fais tes tests **en dehors des heures où tu as besoin d'internet**, et note
  toujours les réglages d'origine de ta box **avant** de les modifier.

---

## ➡️ Et maintenant ?

1. **Installe Packet Tracer** (section ci-dessus).
2. Enchaîne sur les TP **dans l'ordre**, en commençant par le premier :
   👉 **[TP01 — Ta première IP](tp/tp01-premiere-ip.md)**.

Chaque TP s'appuie sur le précédent : ne les saute pas. 🙂

---

⬅️ [Retour au sommaire](../README.md) · 🧭 [Parcours](../PARCOURS.md)
