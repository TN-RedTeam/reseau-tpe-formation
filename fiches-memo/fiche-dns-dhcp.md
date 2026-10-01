# 📇🎫 Fiche-mémo — DNS & DHCP

Deux assistants automatiques. **Ne pas confondre !**

## DNS = l'annuaire 📇
Traduit un **nom** en **adresse IP**.
```
   google.com  ──DNS──►  142.250.179.100
```
- DNS publics connus : `1.1.1.1` (Cloudflare), `8.8.8.8` (Google).
- Panne DNS = « internet marche mais aucun site ne s'ouvre ».

## DHCP = le gardien de parking 🎫
Donne **automatiquement une IP libre** à chaque appareil qui arrive.
```
   nouveau PC ──"j'ai besoin d'une IP"──► DHCP ──"prends .25"──►
```
- Pas de DHCP → il faudrait tout régler à la main.
- En TPE, c'est **la box** qui fait DHCP + relais DNS.

## Pour s'en souvenir
| | Rôle | Analogie |
|---|---|---|
| **DNS** | nom → IP | l'annuaire |
| **DHCP** | donne une IP | le gardien de parking |

🔍 Tester : `ipconfig /all` (voir DHCP + DNS) · `nslookup google.com`

⬅️ [Fiches-mémo](README.md)
