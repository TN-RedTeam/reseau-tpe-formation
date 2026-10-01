# Corrigé 07 — Le NAS (stockage partagé)

**1.** NAS = *Network Attached Storage* = **stockage branché au réseau** : une
« armoire à fichiers » du réseau.

**2.** Par exemple : il est **toujours allumé** ; il est **fait pour ça** (fiable) ;
il gère **finement les droits d'accès** ; il protège mieux les données (RAID).
Deux suffisent.

**3.** Le **RAID miroir (RAID 1)** protège contre la **panne d'un disque dur** : tout
est écrit **en double** sur deux disques. Si l'un lâche, l'autre a la copie.

**4. (piège)** **FAUX.** Le RAID protège d'une **panne de disque**, pas d'un virus,
d'une suppression par erreur, d'un vol ou d'un incendie. Le RAID **n'est pas une
sauvegarde** (voir cours 08).

**5.** Tout prêt : **Synology** ou **QNAP**. Maison/gratuit : **TrueNAS** ou
**OpenMediaVault**.

**6.** (pratique) Dans DSM : (a) dossier partagé via *Panneau de configuration →
Dossier partagé* ; (b) utilisateur via *Panneau de configuration → Utilisateur*.

---

⬅️ [Retour à l'exercice](../07-nas-stockage-partage.md)
