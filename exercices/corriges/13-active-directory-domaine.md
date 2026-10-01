# Corrigé 13 — Active Directory & le domaine

**1.** À la **réception centrale d'un grand hôtel** : elle crée les badges, ouvre/ferme les
accès et applique les règles à toutes les chambres. AD centralise comptes et droits.

**2.** **Groupe de travail (TPE)** : comptes **locaux**, par PC, chacun sa config.
**Domaine (PME)** : comptes **centralisés**, mêmes identifiants partout, droits et règles
gérés d'un seul endroit.

**3.** Les **GPO** (stratégies de groupe) appliquent des **règles à tout le parc d'un
coup**. Ex : imposer un verrouillage auto de session, interdire les clés USB, définir une
imprimante par défaut, forcer des mots de passe complexes.

**4.** **Vrai.** C'est l'un des grands intérêts du domaine : le compte suit l'utilisateur
sur n'importe quel poste de l'entreprise.

**5.** En général au-delà de **~10-15 postes** (ou dès qu'on veut homogénéité et sécurité
centralisées).

**6.** **Entra ID** (ex-Azure AD) = la version **cloud** d'Active Directory, liée à
Microsoft 365. Même principe (comptes centralisés), mais « réception » dans le cloud.

**7.** (pratique) Tu dois reconnaître : *Users and Computers* (créer un compte), une GPO
(une règle), et « joindre le domaine » côté PC.

---

⬅️ [Retour à l'exercice](../13-active-directory-domaine.md)
