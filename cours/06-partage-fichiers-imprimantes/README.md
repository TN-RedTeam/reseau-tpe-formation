# Cours 06 — Partage de fichiers et imprimantes

🕐 Lecture : ~6 min · Niveau : débutant

---

## 🗄️ L'analogie du quotidien

Imagine une **armoire à dossiers commune** dans le bureau. Au lieu que chacun
garde ses papiers sur son propre PC, on met les documents partagés dans cette
armoire : **tout le monde peut y accéder**.

Le **partage de fichiers**, c'est exactement ça : un dossier accessible depuis
plusieurs PC du réseau.

Et l'**imprimante partagée**, c'est comme **une seule photocopieuse** pour tout le
bureau, au lieu d'une par personne.

---

## 📂 Partager un dossier (le principe)

Sur un PC (ou un NAS), on **désigne un dossier comme "partagé"**. Les autres PC du
réseau peuvent alors l'ouvrir, comme s'il était chez eux.

```
   💻 PC Alice
   └── 📁 Dossier "Devis" ──(partagé)──► 💻 PC Bob peut l'ouvrir
                                      └─► 💻 PC Chloé peut l'ouvrir
```

Deux questions se posent toujours quand on partage :

1. **Qui a le droit d'y accéder ?** (tout le monde ? certaines personnes ?)
2. **Peut-on juste lire, ou aussi modifier ?** (lecture seule vs lecture/écriture)

> 💡 Bon réflexe TPE : ne partage que ce qui doit l'être, et donne **le minimum de
> droits nécessaires**. On revient là-dessus au cours 09 (sécurité).

---

## 🪟 Partager un dossier sous Windows (vue rapide)

1. Clic droit sur le dossier → **Propriétés** → onglet **Partage**.
2. Bouton **Partager…** → choisis **qui** peut y accéder et **avec quels droits**.
3. Les autres y accèdent en tapant dans l'explorateur : `\\NOM-DU-PC\NomDuPartage`

> `\\NOM-DU-PC` = « frappe à la porte de ce PC ». C'est l'adresse du partage sur
> le réseau.

**Limite importante** : si c'est le PC d'Alice qui partage, et qu'Alice **éteint
son PC**, plus personne n'a accès aux fichiers. 😬 D'où l'intérêt du **NAS**
(cours 07), une armoire **toujours allumée** et faite pour ça.

---

## 🖨️ Partager une imprimante

Deux cas courants en TPE :

- **Imprimante réseau** (branchée directement à la box par câble ou Wi-Fi) : elle a
  sa **propre adresse IP**. Chaque PC l'ajoute et imprime. Le plus simple et le
  plus fiable. ✅
- **Imprimante USB partagée** (branchée sur un PC) : le PC la « prête » au réseau…
  mais il doit rester allumé. Comme pour les fichiers, c'est moins pratique.

> 💡 En TPE, privilégie une **imprimante réseau** : indépendante, dispo pour tous.

---

## 🧭 Le "nom" des PC sur le réseau

Pour se retrouver facilement, chaque PC a un **nom** (ex : `PC-ACCUEIL`,
`PC-COMPTA`). C'est plus parlant qu'une adresse IP. C'est ce nom qu'on utilise
dans `\\PC-COMPTA` pour accéder à ses partages.

> 🔧 Sous Windows : le nom est dans *Paramètres → Système → Informations système*.

---

## ✅ Ce qu'il faut retenir

1. **Partager un dossier** = une **armoire commune** accessible depuis le réseau.
2. Toujours se demander : **qui** a accès, et **lecture seule** ou **modification** ?
3. Pour fichiers **et** imprimante, mieux vaut un équipement **toujours allumé**
   (NAS, imprimante réseau) qu'un PC qu'on éteint.

## 🔧 À essayer

Sur ton PC Windows, ouvre l'explorateur de fichiers et tape `\\` dans la barre
d'adresse, puis le nom d'un autre PC de ton réseau (si tu en as un). Tu verras ses
dossiers partagés. Sinon, crée un dossier de test, fais clic droit → Propriétés →
**Partage**, et observe les options (sans forcément valider).

> 💡 Tu mélanges **Linux, Windows et Mac** ? Partager un dossier entre eux, c'est le rôle
> de **SMB/Samba** : voir le [tuto partage multi-OS](../../00-demarrage/organiser-son-labo.md#partie-2--partager-un-dossier-entre-tes-machines)
> (ou la [fiche-mémo](../../fiches-memo/fiche-partage-multi-os.md)).

> ➡️ Fais ensuite l'[exercice 06](../../exercices/06-partage-fichiers-imprimantes.md).

---

⬅️ [Cours 05](../05-wifi-et-reseau-local/) · ➡️ [Cours 07 — Le NAS](../07-nas-stockage-partage/)
