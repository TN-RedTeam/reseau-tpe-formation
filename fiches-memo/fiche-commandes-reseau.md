# ⌨️ Fiche-mémo — Commandes réseau

À taper dans **`cmd`** (Windows). Ouvre-le : touche Windows → tape `cmd` → Entrée.

| Commande | Ce qu'elle fait | Quand l'utiliser |
|---|---|---|
| `ipconfig` | Montre ton IP, passerelle, DNS | « Ai-je une adresse ? » |
| `ipconfig /all` | Tous les détails (DHCP, DNS, MAC) | Diagnostic complet |
| `ipconfig /release` | Libère l'adresse DHCP | Forcer un renouvellement |
| `ipconfig /renew` | Redemande une adresse au DHCP | Après un /release |
| `ping 192.168.1.1` | « La box répond ? » | Tester le réseau local |
| `ping 8.8.8.8` | « Internet répond ? » | Tester la sortie internet |
| `ping google.com` | « Le DNS marche ? » | Tester la traduction de noms |
| `nslookup google.com` | Traduit un nom en IP | Confirmer un souci DNS |
| `tracert google.com` | Montre le chemin jusqu'au site | Voir où ça bloque |

## 🧠 Le combo diagnostic (dans l'ordre)
```
   ipconfig
   ping 192.168.1.1     (box)
   ping 8.8.8.8         (internet)
   ping google.com      (DNS)
```
Le premier qui échoue = l'endroit du problème.

> 💡 `8.8.8.8` OK mais `google.com` KO → **c'est le DNS**.

> 🍎 Mac/Linux : `ip a` (ou `ifconfig`), `ping`, `nslookup`/`dig`, `traceroute`.

⬅️ [Fiches-mémo](README.md)
