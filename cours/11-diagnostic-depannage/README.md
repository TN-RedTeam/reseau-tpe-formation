# Cours 11 — Diagnostic et dépannage

🕐 Lecture : ~7 min · Niveau : débutant · 🎓 Le cours qui fait de toi un dépanneur

---

## 🩺 L'analogie du quotidien

Dépanner un réseau, c'est comme être **médecin** : on ne devine pas au hasard, on
**pose des questions**, on **teste étape par étape**, et on **remonte à la cause**.

La bonne nouvelle : 90 % des pannes en TPE se règlent avec **une méthode simple**
et **4 outils**. Pas de magie, juste de la logique.

---

## 🪜 La méthode : de bas en haut

Quand « ça ne marche pas », remonte la chaîne, **du plus proche au plus loin** :

```
   1. Le câble / le Wi-Fi est-il bien connecté ?   (physique)
   2. L'appareil a-t-il une adresse IP ?           (le réseau local)
   3. Atteint-il la box (la passerelle) ?          (la sortie)
   4. Atteint-il internet ?                        (l'extérieur)
   5. Les noms de sites se traduisent-ils ?        (le DNS)
```

Teste **dans cet ordre**. Le premier « non » t'indique où est le problème. 🎯

---

## 🧰 Les 4 outils du dépanneur (sous Windows, dans `cmd`)

### 1. `ipconfig` — « ai-je une adresse ? »

Affiche ton adresse IP, ta passerelle et ton DNS.
- Pas d'adresse, ou une adresse en `169.254.x.x` → le **DHCP n'a pas répondu**
  (problème box ou câble). C'est un indice en or.

### 2. `ping` — « est-ce que tu me réponds ? »

Envoie un petit « coucou, tu es là ? » à un appareil. S'il répond, la liaison
fonctionne.
- `ping 192.168.1.1` → est-ce que **la box** répond ? (réseau local OK ?)
- `ping 8.8.8.8` → est-ce qu'**internet** répond ? (sortie OK ?)
- `ping google.com` → est-ce que le **DNS** marche ? (traduction OK ?)

> 💡 **Astuce de pro** : si `ping 8.8.8.8` marche mais `ping google.com` échoue →
> c'est un **problème de DNS**, pas de connexion. Internet est là, c'est l'annuaire
> qui déraille.

### 3. `nslookup` — « traduis-moi ce nom »

`nslookup google.com` demande au DNS de traduire un nom en IP. Utile pour confirmer
un souci de DNS.

### 4. `tracert` — « par où passe mon paquet ? »

`tracert google.com` montre toutes les étapes entre toi et le site. Permet de voir
**où ça bloque** sur le chemin.

---

## 🔁 Le grand classique qui marche vraiment

Avant de chercher compliqué, les réflexes qui résolvent la moitié des cas :

1. **Redémarrer** l'appareil concerné.
2. **Redémarrer la box** (éteindre 30 secondes, rallumer).
3. **Vérifier les câbles** (débranché ? mal enfoncé ? voyant éteint ?).
4. **Est-ce que ça touche tout le monde, ou un seul PC ?**
   - Un seul PC → le problème est **sur ce PC**.
   - Tout le monde → le problème est **côté box/réseau**.

> 💡 Cette question « un seul ou tout le monde ? » est la plus rentable du métier :
> elle divise instantanément le champ de recherche en deux.

---

## 🗒️ Garder une trace

Un bon technicien **note** : quelle panne, quelle cause, quelle solution. La
prochaine fois, tu résous en 2 minutes ce qui t'a pris 1 heure. Tiens un petit
**journal de dépannage** (même un simple fichier texte).

---

## ✅ Ce qu'il faut retenir

1. Dépanne **de bas en haut** : câble → IP → box → internet → DNS.
2. Tes 4 outils : **`ipconfig`**, **`ping`**, **`nslookup`**, **`tracert`**.
3. La question magique : **« un seul PC ou tout le monde ? »** + le trio
   redémarrer / câbles / box.

## 🔧 À essayer

Ouvre `cmd` et fais le diagnostic complet de ta propre machine, dans l'ordre :
`ipconfig` → `ping 192.168.1.1` → `ping 8.8.8.8` → `ping google.com`.
Tout répond ? Félicitations, ton réseau est en pleine santé — et tu viens de faire
ton premier diagnostic méthodique de dépanneur. 🩺

> ➡️ Fais ensuite l'[exercice 11](../../exercices/11-diagnostic-depannage.md).
> Puis passe au grand scénario : [`bac-a-sable/tp/tp06`](../../bac-a-sable/tp/tp06-scenario-panne.md).

---

⬅️ [Cours 10](../10-vpn-acces-distant/) · 🏁 [Retour au sommaire](../../README.md)
