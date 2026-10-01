# 🧾 Cas pratique — Fiche d'intervention (remplie)

> Exemple rempli du [modèle vierge](../infogerance/modeles/modele-fiche-intervention.md).
> Un incident réel traité **à distance**, dans le cadre du forfait.

---

**Client :** Cabinet comptable Durand   **Fiche N° :** 2025-091
**Date :** 06/05/2025   **Technicien :** [Toi]
**Type :** ☑ À distance
**Cadre :** ☑ Inclus au forfait

---

## Demande / symptôme signalé
Mme Durand signale (ticket #091, priorité 🟠 majeur) : « Depuis ce matin, personne
n'arrive à accéder au dossier partagé "Clients" sur le serveur. Le logiciel de compta
affiche une erreur de connexion. »

## Diagnostic
- Supervision RMM : le serveur SRV-DURAND est **en ligne** mais l'espace disque du
  volume D: est à **99 %** (alerte reçue à 7h58, avant l'appel client).
- Le service de base de données du logiciel de compta s'est **arrêté** faute d'espace.
- Cause racine : accumulation d'anciens **fichiers temporaires** et de journaux non purgés.

## Actions réalisées
- Prise en main à distance du serveur (via RMM).
- Suppression des fichiers temporaires et rotation des journaux → **38 Go libérés**.
- Redémarrage propre du service de base de données ; accès au dossier "Clients" rétabli.
- Mise en place d'une **tâche de nettoyage automatique hebdomadaire** + **alerte à 85 %**
  d'occupation disque (pour prévenir avant blocage).

## Matériel fourni / remplacé
Aucun.

## Résultat
☑ Résolu — accès et logiciel de compta de nouveau fonctionnels. Prévention ajoutée.

## Temps passé
Début : 08h10   Fin : 08h55   **Durée : 0,75 h**

## Recommandations au client
Le volume du serveur se remplit : prévoir, d'ici la fin d'année, une **extension de
stockage** (hors forfait, devis à venir). Sans urgence immédiate grâce à la surveillance
mise en place.

---

**Signature technicien :** [Toi]    **Signature client :** (accusé par email, ticket #091)

> 💡 Ce que ça illustre : grâce à la **supervision** (cours exploitation 01), le problème
> a été **vu avant le client**, résolu **à distance** en 45 min, **tracé** par un ticket,
> et une **prévention** a été ajoutée pour éviter la récidive. C'est exactement la valeur
> que paie le forfait.

---

⬅️ [Dossier client](05-dossier-client-rempli.md) · ➡️ [Checklist maintenance remplie](07-checklist-maintenance-remplie.md)
