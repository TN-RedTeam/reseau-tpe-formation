# Corrigé 02 — Les adresses IP

**1.** À une **adresse postale** : elle permet de livrer les informations au bon
appareil.

**2.** Dans `192.168.1.25` :
- **Quartier (réseau)** : `192.168.1`
- **Numéro de la maison (appareil)** : `.25`

**3.**
- `192.168.0.10` → **oui**, privée.
- `10.0.0.5` → **oui**, privée.
- `8.8.8.8` → **non**, c'est une adresse **publique** (le DNS de Google).

**4.** Le masque **indique où s'arrête le « quartier »** : quelle partie de l'IP est
le réseau, et quelle partie est l'appareil.

**5.** **Non.** Deux appareils du même réseau ne peuvent pas avoir la même IP :
ce serait comme deux maisons avec la même adresse, le facteur (le réseau) ne saurait
plus à qui livrer → **conflit d'adresses**.

**6.** (réponse personnelle) Ton IP commence très probablement par `192.168.` →
c'est une adresse privée, normale pour un réseau local.

---

⬅️ [Retour à l'exercice](../02-adresses-ip.md)
