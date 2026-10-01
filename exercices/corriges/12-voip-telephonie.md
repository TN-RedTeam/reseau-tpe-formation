# Corrigé 12 (bonus) — La téléphonie VoIP

**1.** VoIP = *Voice over IP* = « la voix sur IP ». Idée : faire passer la **voix sur
le réseau internet**, découpée en **paquets de données**, comme le reste du trafic.

**2.** Le téléphone classique (RTC) utilisait une **ligne téléphonique dédiée** (un
fil séparé pour la voix). La VoIP utilise **le même réseau que les PC** : un seul
tuyau pour tout. (Et le RTC ferme progressivement en France.)

**3.**
- Téléphone IP → un **téléphone branché au réseau** (RJ45), pas à une prise tél.
- Softphone → une **appli** qui transforme un PC/smartphone en téléphone.
- IPBX → le **standard téléphonique** qui gère appels, transferts, messagerie.
- Trunk SIP → la **ligne** VoIP de l'opérateur (appels vers/depuis l'extérieur).

**4.** La **QoS** (*Quality of Service*) donne la **priorité à la voix** sur le reste
du trafic réseau. C'est important car la voix est **fragile** : sans priorité, elle
peut se **hacher** quand le réseau est chargé (« voie réservée » pour la voix).

**5.** Par exemple : **moins cher** (un seul abonnement, souvent illimité) ;
**souple** (ajouter une ligne = brancher un téléphone) ; **nomade** (softphone depuis
chez soi) ; **fonctions avancées** (standard auto, renvois, messagerie par email).
Deux suffisent.

**6.** Gros risque : **si internet tombe, le téléphone tombe aussi.** Parade : une
connexion **fiable** (fibre), et éventuellement une **solution de secours 4G** pour
basculer en cas de coupure.

**7.** (réponse personnelle) Si ton fixe est branché sur la prise « Tel » de la box,
tu fais déjà de la VoIP. La section « Téléphonie »/« QoS » de la box permet de régler
ça.

---

⬅️ [Retour à l'exercice](../12-voip-telephonie.md)
