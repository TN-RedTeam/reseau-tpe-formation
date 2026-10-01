# Corrigé 11 — Diagnostic et dépannage

**1.** De bas en haut : **câble/Wi-Fi** → **adresse IP** → **box (passerelle)** →
**internet** → **DNS**. Le premier « non » indique où est le problème.

**2.**
- `ipconfig` → **« ai-je une adresse IP ? »** (voir IP, passerelle, DNS).
- `ping` → **« est-ce que tu me réponds ? »** (tester une liaison).
- `nslookup` → **« traduis-moi ce nom »** (tester le DNS).
- `tracert` → **« par où passe mon paquet ? »** (voir le chemin, où ça bloque).

**3.** Un **problème de DNS**. Internet répond (8.8.8.8 OK), mais la **traduction des
noms** échoue → l'annuaire (DNS) est en cause.

**4.** Une adresse en `169.254.x.x` signifie que le **DHCP n'a pas répondu** : l'appareil
n'a pas reçu d'IP (souvent un souci de câble, de box, ou de service DHCP).

**5.** **« Un seul PC, ou tout le monde ? »**
- Un seul → le problème est **sur ce PC**.
- Tout le monde → le problème est **côté box/réseau**.

**6.** **Redémarrer** l'appareil, **redémarrer la box** (30 s éteinte), **vérifier les
câbles**.

**7.** (réponse personnelle) Si tout répond, ton réseau est sain — et tu viens de
réussir un diagnostic méthodique complet. 🩺

---

⬅️ [Retour à l'exercice](../11-diagnostic-depannage.md)
