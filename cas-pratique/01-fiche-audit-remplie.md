# 📋 Cas pratique — Fiche d'audit (remplie)

> Exemple rempli du [modèle vierge](../infogerance/modeles/modele-fiche-audit.md).
> 🔴 critique · 🟠 à améliorer · 🟢 correct.

---

**Client :** Cabinet comptable Durand   **Date :** 12/03/2025   **Réalisé par :** [Toi]
**Nb de postes :** 12 (10 fixes + 2 portables)   **Nb d'utilisateurs :** 10   **Nb de sites :** 1

---

## 1. Matériel

| Appareil | Modèle / Âge | Système | N° de série | État |
|---|---|---|---|---|
| PC Accueil | Dell OptiPlex, 3 ans | Windows 11 | FR8K2L1 | 🟢 |
| PC Compta 1-6 | HP, 2 à 4 ans | Windows 11 | (voir annexe) | 🟢 |
| PC Compta 7 | Tour assemblée, **8 ans** | **Windows 10** (fin de support proche) | — | 🔴 |
| Portables (×2) | Lenovo, 2 ans | Windows 11 | — | 🟢 |
| Serveur | Tour, 6 ans, **pas de RAID vérifié** | Windows Server 2016 | SRV-DUR | 🟠 |
| NAS | Synology 2 baies | DSM | NAS-DUR | 🟢 |
| Imprimantes | 1 multifonction + 1 laser | réseau | — | 🟢 |
| Box / Routeur | Box fibre opérateur | — | — | 🟠 |
| Switch | Switch **non managé** 8 ports | — | — | 🟠 |
| Onduleur (UPS) | **Aucun** sur le serveur | — | — | 🔴 |

## 2. Logiciels & licences

- OS + versions : Windows 11 (majorité), **1 poste Windows 10 ancien** 🔴, Windows Server 2016 🟠
- Logiciels métier : logiciel de comptabilité (serveur) + bureautique
- Licences en règle ? ☑ À vérifier (bureautique : clés OEM dispersées) 🟠
- Suite bureautique / messagerie : **Office acheté une fois + messagerie chez l'opérateur** 🟠

## 3. Réseau

- Plage IP / plan d'adressage : `192.168.1.0/24` (DHCP box)
- Wi-Fi : SSID « DURAND » · Chiffrement ☑ WPA2 🟢 — **mais une seule clé partagée, pas de réseau invité** 🟠
- Débit internet : Fibre 🟢
- Réseau invité séparé ? ☑ Non 🟠
- Câblage / switch : switch non managé, **pas de VLAN** (compta + visiteurs mélangés) 🟠

## 4. Sécurité

- Antivirus actif & à jour ? ☑ Partiel (Defender OK sur récents, **absent sur le vieux poste**) 🟠
- Pare-feu actif ? ☑ Oui (box) 🟢
- Mots de passe par défaut présents ? ☑ **Oui — admin box inchangé, NAS « admin »** 🔴
- Mises à jour à jour ? ☑ Non (serveur et poste ancien en retard) 🔴
- Double authentification (2FA) ? ☑ Non (ni messagerie, ni NAS) 🔴

## 5. Sauvegardes ⭐

- Sauvegarde en place ? ☑ Partielle (copie manuelle occasionnelle sur le NAS) 🔴
- Où ? Sur le NAS, **au même endroit que les données de travail**
- Fréquence : « quand on y pense » · Automatique ? ☑ Non 🔴
- Copie hors site (3-2-1) ? ☑ **Non** 🔴
- **Déjà testée (restauration) ?** ☑ **Jamais** 🔴

## 6. Organisation

- Qui gère l'info ? Le neveu du dirigeant, bénévolement, irrégulièrement
- Documentation existante ? ☑ Non 🔴
- Référent interne : Mme Durand (dirigeante)
- Fournisseurs : opérateur fibre, éditeur logiciel compta, registrar du nom de domaine (inconnu du client) 🟠

---

## 🔴 Synthèse des points critiques

1. **Aucune sauvegarde fiable, automatique, hors site, ni testée** → risque de perte
   totale des dossiers clients (données comptables = vitales et légalement à conserver).
2. **Aucun onduleur sur le serveur** → une coupure de courant peut corrompre la base de
   comptabilité.
3. **Mots de passe par défaut + pas de 2FA + mises à jour en retard** → cabinet très
   exposé au piratage et au rançongiciel (données sensibles = cible de choix).

*(Secondaires 🟠 : poste Windows 10 obsolète, pas de réseau invité ni de VLAN, licences à
régulariser, aucune documentation.)*

---

➡️ Suite : [Rapport d'audit rempli](02-rapport-audit-rempli.md)
