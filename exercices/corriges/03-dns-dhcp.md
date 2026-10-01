# Corrigé 03 — DNS et DHCP

**1.** « Le DNS traduit un **nom de site** (ex : google.com) en **adresse IP** (ex :
142.250.179.100). »

**2.** Le **DHCP** attribue **automatiquement une adresse IP libre** à chaque
appareil qui se connecte au réseau.

**3.**
- L'annuaire téléphonique → **DNS**.
- Le gardien de parking → **DHCP**.

**4.** Le **DNS**. Si internet répond (ping 8.8.8.8 OK) mais que les noms de sites
ne s'ouvrent pas, c'est l'**annuaire (DNS)** qui ne fait pas son travail.

**5.** La **box**. En TPE sans serveur dédié, c'est elle qui fait DHCP et relais DNS.

**6.** (réponse personnelle) Le serveur DHCP et le DNS pointeront souvent vers
l'adresse de ta box (ex : `192.168.1.1`). Le `nslookup` doit te renvoyer une ou
plusieurs adresses IP pour google.com → le DNS fonctionne.

---

⬅️ [Retour à l'exercice](../03-dns-dhcp.md)
