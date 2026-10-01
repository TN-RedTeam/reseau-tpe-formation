# Cours 08 — Les sauvegardes

🕐 Lecture : ~6 min · Niveau : débutant · ⭐ Cours essentiel

---

## 🧯 L'analogie du quotidien

Une **sauvegarde**, c'est comme **faire des photocopies de tes papiers les plus
importants et les ranger ailleurs**.

Si l'original brûle, est volé, ou si tu renverses ton café dessus… tu as une
**copie en lieu sûr**. Tu ne perds rien.

> C'est **le** sujet le plus important de toute l'informatique de TPE. Un réseau
> peut tomber en panne une journée, c'est embêtant. Perdre **toutes les données**
> d'une entreprise, ça peut la **couler**. 🚨

---

## ❌ Ce qu'une sauvegarde N'EST PAS

- Le **RAID** (cours 07) n'est **pas** une sauvegarde. Il protège d'une panne de
  disque, pas d'un virus, d'une erreur, d'un vol ou d'un incendie.
- Avoir ses fichiers **sur le NAS** n'est **pas** une sauvegarde : si le NAS brûle
  ou est volé, tout part avec lui.

Une vraie sauvegarde, c'est une **copie séparée**, rangée **ailleurs**.

---

## 🥇 La règle d'or : le 3-2-1

La méthode que tout bon technicien applique :

```
   3  copies de tes données
   2  supports différents (ex : NAS + disque externe)
   1  copie hors du bâtiment (cloud, ou disque emporté ailleurs)
```

Exemple concret pour une TPE :

1. Les fichiers **de travail** sur le NAS (copie n°1).
2. Une **sauvegarde automatique** sur un **disque dur externe** (copie n°2).
3. Une **sauvegarde dans le cloud** ou un disque **rapporté à la maison** (copie n°3,
   hors site).

> 💡 Le « 1 hors du bâtiment » protège contre **l'incendie, le dégât des eaux et le
> vol** : la catastrophe qui emporte tout le local d'un coup.

---

## 🔁 Automatique, sinon ça ne marche pas

Une sauvegarde qu'on doit **penser à faire à la main** ne se fait jamais. La clé :
**l'automatiser**.

- Les NAS (Synology/QNAP) ont des outils intégrés (ex : *Hyper Backup*) pour copier
  automatiquement vers un disque externe ou le cloud, chaque nuit.
- Windows a l'**Historique des fichiers** ; Mac a **Time Machine**.
- Règle : **planifie** (tous les jours/nuits) et **oublie**. La machine s'en charge.

---

## 🧪 La sauvegarde qu'on ne teste pas n'existe pas

Le piège le plus cruel : croire qu'on est sauvegardé… et découvrir le jour du
problème que la sauvegarde était **vide ou corrompue**.

> ✅ **Réflexe de pro** : au moins **une fois par mois**, teste en **restaurant un
> fichier** depuis la sauvegarde. Si tu arrives à le récupérer, ta sauvegarde
> fonctionne vraiment.

---

## ✅ Ce qu'il faut retenir

1. Une sauvegarde = une **copie séparée, rangée ailleurs**. Le RAID n'en est pas une.
2. Applique le **3-2-1** : 3 copies, 2 supports, 1 hors du bâtiment.
3. **Automatise** la sauvegarde, et **teste la restauration** régulièrement.

## 🔧 À essayer

Pense à **tes propres fichiers importants** (photos, documents). Réponds
honnêtement : as-tu **3 copies** ? Sur **2 supports** ? Dont **1 ailleurs** ?
Si la réponse est « non »… tu viens de comprendre pourquoi ce cours est le plus
important. Branche un disque externe et lance une première copie dès aujourd'hui. 💾

> ➡️ Fais ensuite l'[exercice 08](../../exercices/08-sauvegardes.md).

---

⬅️ [Cours 07](../07-nas-stockage-partage/) · ➡️ [Cours 09 — La sécurité de base](../09-securite-de-base/)
