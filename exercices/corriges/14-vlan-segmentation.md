# Corrigé 14 — VLAN & segmentation

**1.** À des **cloisons** qui créent des **bureaux séparés** dans un grand open space, sans
refaire les murs (sans retirer de câbles).

**2.** **VLAN** = *Virtual LAN* = réseau local **virtuel**. Il permet de **découper un même
réseau physique en plusieurs réseaux logiques isolés**.

**3.** **Sécurité** (cloisonnement : une zone compromise n'atteint pas les autres),
**performance** (moins de bruit, priorité possible à la voix), **organisation** (règles
claires par usage).

**4.** « Le **Wi-Fi des visiteurs** ne doit jamais accéder à vos fichiers internes » : on
isole le VLAN invité du VLAN bureautique.

**5.** Un **switch managé** (indispensable), souvent un **routeur/pare-feu** gérant les VLAN
(pour le routage inter-VLAN), et des bornes Wi-Fi multi-SSID.

**6.** Un port **access** appartient à **un seul** VLAN (ex : prise d'un PC). Un port
**trunk** transporte **plusieurs** VLAN (ex : lien entre switchs ou vers le routeur).

**7.** (exemple) VLAN 10 Bureautique `192.168.10.0`, VLAN 20 Voix `192.168.20.0`, VLAN 30
Invités `192.168.30.0`, VLAN 40 Caméras `192.168.40.0`. Chaque usage isolé.

---

⬅️ [Retour à l'exercice](../14-vlan-segmentation.md)
