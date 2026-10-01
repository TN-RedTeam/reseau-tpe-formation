# 🩺 Fiche-mémo — Dépannage express

## ⚡ Les 2 questions d'or
1. **Un seul PC, ou tout le monde ?**
   - Un seul → problème **sur ce PC**.
   - Tout le monde → problème **côté box/réseau**.
2. **Qu'est-ce qui a changé récemment ?** (mise à jour, déplacement, nouveau matériel)

## 🪜 La méthode (de bas en haut)
```
   1. Câble / Wi-Fi branché ?        (physique)
   2. A une IP valide ?              → ipconfig
   3. Atteint la box ?              → ping 192.168.1.1
   4. Atteint internet ?           → ping 8.8.8.8
   5. Les noms se traduisent ?     → ping google.com
```
Le premier « non » = là où est le problème.

## 🔁 Les réflexes qui résolvent la moitié des cas
- [ ] Redémarrer l'appareil
- [ ] Redémarrer la box (30 s éteinte)
- [ ] Vérifier les câbles (voyants, bien enfoncés)
- [ ] Tester avec un autre câble / une autre prise

## 🚩 Indices qui parlent
- IP en `169.254.x.x` → **DHCP muet** (câble/box/service DHCP).
- `ping 8.8.8.8` OK + `ping google.com` KO → **DNS**.
- Liaison **rouge** dans le simulateur → **câble/port** HS.

## 🗒️ Après : note la panne, la cause, la solution.
La prochaine fois, 2 min au lieu d'1 h.

⬅️ [Fiches-mémo](README.md)
