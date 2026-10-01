# Cours 07 — Le NAS (stockage partagé)

🕐 Lecture : ~6 min · Niveau : débutant

---

## 📦 L'analogie du quotidien

Un **NAS**, c'est une **grande armoire à dossiers, toujours ouverte, dans le
couloir du bureau**.

- Elle est **toujours allumée** (contrairement à un PC qu'on éteint le soir).
- **Tout le monde** peut y ranger et y prendre des documents (selon ses droits).
- Elle est **solide** : conçue pour garder les fichiers en sécurité.

**NAS** veut dire *Network Attached Storage* : littéralement « **stockage branché
au réseau** ». C'est un petit boîtier avec des disques durs, relié à la box.

---

## 🆚 NAS vs partage depuis un PC

Au cours 06, on partageait un dossier depuis un PC. Problème : si le PC s'éteint,
plus d'accès. Le NAS règle ça :

| | **Partage depuis un PC** | **NAS** |
|---|---|---|
| Allumé en permanence | ❌ non (on éteint le PC) | ✅ oui |
| Fait pour ça | ❌ non | ✅ oui |
| Sécurité des données | moyenne | 💪 bonne (voir RAID) |
| Gestion des accès | basique | fine (comptes, droits) |

👉 En TPE, le NAS est **la bonne solution** pour centraliser les fichiers.

---

## 🖼️ Où se place le NAS

```
                 🌐 Internet
                     |
                 [ BOX ]
                 │ │ │
        💻 PC ───┘ │ └─── 💾 NAS  ← l'armoire commune, toujours allumée
        💻 PC ─────┘
```

Le NAS est un **appareil du réseau comme un autre** : il a sa propre adresse IP.
Les PC y accèdent comme à un dossier partagé (`\\NAS\Documents` par exemple).

---

## 🛟 Le RAID — ne pas tout perdre si un disque lâche

Un NAS contient souvent **plusieurs disques durs**. Le **RAID** est une technique
pour les faire travailler ensemble.

Le plus utile à connaître : le **miroir** (RAID 1). Tout est écrit **en double**,
sur deux disques. Si l'un meurt, l'autre a **la copie** : tu ne perds rien.

> 💡 Image : tu écris chaque document **en deux exemplaires** rangés dans deux
> tiroirs. Un tiroir brûle ? Tu as toujours l'autre. 🔥➡️📄

> ⚠️ **ATTENTION, piège classique** : le RAID protège d'une **panne de disque**,
> PAS d'une erreur humaine, d'un virus ou d'un vol. Le RAID **n'est pas une
> sauvegarde**. La vraie sauvegarde, c'est le cours 08.

---

## 🏷️ Les NAS courants

- **Marques toutes prêtes** : **Synology**, **QNAP** (faciles, interface claire).
  Idéal en TPE : tu branches, tu suis l'assistant.
- **Solution "maison"** (vieux PC recyclé) : **TrueNAS** ou **OpenMediaVault**
  (gratuits). Moins cher, un peu plus technique. Parfait pour s'entraîner !

---

## ✅ Ce qu'il faut retenir

1. Un **NAS** = une **armoire à fichiers** du réseau, **toujours allumée**.
2. Le **RAID miroir** protège si **un disque** tombe en panne (écriture en double).
3. ⚠️ Le RAID **n'est PAS une sauvegarde** : ça, c'est le cours suivant.

## 🔧 À essayer

Pas de NAS sous la main ? Pas grave : va voir le site de **Synology** et clique sur
leur **démo en ligne** (DSM live demo). Tu navigueras dans l'interface d'un vrai
NAS, gratuitement, depuis ton navigateur. Repère où on crée un **dossier partagé**
et où on gère les **utilisateurs**.

> ➡️ Fais ensuite l'[exercice 07](../../exercices/07-nas-stockage-partage.md).

---

⬅️ [Cours 06](../06-partage-fichiers-imprimantes/) · ➡️ [Cours 08 — Les sauvegardes](../08-sauvegardes/)
