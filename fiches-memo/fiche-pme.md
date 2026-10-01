# 🏢 Fiche-mémo — Repères PME

Ce qui change quand une TPE devient PME (~10-15 postes et +).

## Active Directory (le domaine)
- La **réception centrale** : comptes + droits **centralisés**.
- Même compte sur **tous** les postes.
- **GPO** = règles appliquées à tout le parc d'un coup.
- Version cloud : **Entra ID** (ex-Azure AD), lié à M365.

## VLAN (segmentation)
- Des **cloisons virtuelles** : 1 réseau physique → plusieurs réseaux isolés.
- Usages : bureautique / voix / **invités** / caméras.
- Bénéfices : **sécurité** (cloisonner) · perf · organisation.
- Nécessite un **switch managé**.

## Serveur
- **Rend des services** (fichiers, AD, impression, appli…).
- **Virtualisation** = plusieurs VM sur une machine physique.
- Incontournables : **RAID + onduleur + sauvegarde + supervision**.

## Switch managé
- vs non managé = **carrefour réglable** vs multiprise bête.
- Apporte **VLAN, QoS, PoE, supervision**.
- **PoE** = courant par le câble réseau (tél IP, caméras, bornes).

## Onduleur (UPS)
- **Batterie de secours** → **arrêt propre** (évite la corruption).
- Dessus : serveur, NAS, box, switch. **Pas** d'imprimante laser.
- Batteries à **tester/remplacer** (3-5 ans).

## Cloud / M365
- SaaS surtout · **OneDrive = perso**, **SharePoint = équipe**.
- **MFA pour tous** (non négociable).
- ⚠️ **Le cloud n'est pas une sauvegarde** → sauvegarde tierce.
- **RGPD** : hébergement UE, sécurité, accès, traçabilité.

⬅️ [Fiches-mémo](README.md)
