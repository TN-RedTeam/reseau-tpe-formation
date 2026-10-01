# 📑 Cas pratique — Rapport d'audit (rempli)

> Exemple rempli du [modèle vierge](../infogerance/modeles/modele-rapport-audit.md).
> Remarque le **langage de patron** : zéro jargon, que des conséquences concrètes.

---

# Rapport d'audit informatique

**Client :** Cabinet comptable Durand
**Date :** 12/03/2025   **Réalisé par :** [Toi / ton entreprise]

---

## 1. Synthèse (1 page)

Votre informatique **fonctionne au quotidien**, mais elle repose sur des bases
**fragiles** qui font courir un **risque sérieux à votre activité**. Trois points
demandent une action rapide.

**Les points qui nous préoccupent le plus :**

1. 🔴 **Vos données ne sont pas réellement sauvegardées.**
   *Conséquence si on ne fait rien :* en cas de panne, de vol, d'incendie ou de virus,
   vous **perdez définitivement** les dossiers de vos clients — avec l'obligation légale
   de les conserver, c'est un risque majeur pour le cabinet.

2. 🔴 **Votre serveur n'a pas d'onduleur (batterie de secours).**
   *Conséquence si on ne fait rien :* une simple coupure de courant peut **corrompre
   votre logiciel de comptabilité** et vous bloquer plusieurs jours.

3. 🔴 **La sécurité est insuffisante** (mots de passe d'origine, pas de double
   vérification, mises à jour en retard).
   *Conséquence si on ne fait rien :* vos données sensibles sont **exposées au piratage
   et au rançongiciel**, de plus en plus fréquents dans les cabinets comptables.

**En un mot :** votre installation « tient », mais **sans filet**. Un incident banal
pourrait avoir des conséquences graves. La bonne nouvelle : tout cela se corrige.

---

## 2. État des lieux par domaine

| Domaine | État | Commentaire |
|---|---|---|
| Matériel | 🟠 | Correct, sauf 1 poste trop ancien et l'absence d'onduleur |
| Logiciels & licences | 🟠 | Licences à régulariser, 1 poste sur un Windows en fin de vie |
| Réseau | 🟠 | Fibre OK, mais visiteurs et postes de travail non séparés |
| Sécurité | 🔴 | Mots de passe d'origine, pas de double authentification, MAJ en retard |
| Sauvegardes | 🔴 | Pas de sauvegarde fiable, automatique, hors site, ni testée |
| Organisation | 🔴 | Aucune documentation, gestion informelle |

---

## 3. Nos recommandations (par priorité)

### 🔴 À faire rapidement
- Mettre en place une **sauvegarde automatique 3-2-1** (locale + hors site), **testée**.
- Installer un **onduleur** sur le serveur et le NAS.
- **Sécuriser** : changer les mots de passe d'origine, activer la **double
  authentification**, remettre les **mises à jour** à jour, antivirus partout.

### 🟠 À planifier
- Remplacer le **poste de travail obsolète** (Windows en fin de support).
- Créer un **réseau Wi-Fi invité séparé** (visiteurs isolés de vos dossiers).
- **Régulariser les licences** logicielles.

### 🟢 Pour aller plus loin
- Envisager **Microsoft 365** (messagerie professionnelle fiable + collaboration).
- Mettre en place une **documentation** et un **suivi mensuel** de votre informatique.

---

## 4. Et maintenant ?

Nous vous proposons :
- une **remise à niveau** (devis ci-joint) pour corriger en priorité les 3 points rouges ;
- un **contrat d'infogérance** (proposition ci-jointe) pour gérer votre informatique au
  quotidien, surveiller vos sauvegardes **chaque jour** et éviter que ces risques ne
  réapparaissent.

Nous restons à votre disposition pour en discuter de vive voix.

[Toi / ton entreprise] — [téléphone / email]

---

➡️ Suite : [Devis rempli](03-devis-rempli.md)
