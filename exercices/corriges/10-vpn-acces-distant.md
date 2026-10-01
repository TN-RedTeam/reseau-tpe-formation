# Corrigé 10 — VPN et accès distant

**1.** À un **tunnel privé et fermé** entre deux lieux. Les données y circulent à
l'abri des regards, même en traversant internet (« la ville »).

**2.** Par exemple : **télétravail** (accéder aux fichiers du bureau de chez soi) ;
**déplacement** (commercial en clientèle) ; **sécurité sur Wi-Fi public**
(café, hôtel). Deux suffisent.

**3.** **Chiffrer** = transformer les données en **charabia illisible** pour tout le
monde, sauf ceux qui ont la **clé** (les deux bouts du tunnel).

**4.** Le **VPN d'entreprise** relie à **ton réseau pro** (pour accéder au NAS, aux
partages). Le **VPN grand public** (NordVPN…) sert surtout à **masquer sa
position/IP** et à changer de pays. Ce ne sont pas les mêmes usages.

**5.** Par exemple : (a) le **serveur VPN intégré** à la box ou au NAS
(Synology/QNAP) ; (b) une solution moderne **WireGuard / Tailscale**.

**6.** Le **VPN** crée un tunnel **chiffré et authentifié** : bien plus sûr qu'une
**redirection de port**, qui ouvre une **porte directe** sur internet (cible facile
pour les attaques).

**7.** (pratique) Grandes étapes typiques (Tailscale) : créer un compte → installer
l'appli sur chaque appareil → se connecter → les appareils se voient entre eux.

---

⬅️ [Retour à l'exercice](../10-vpn-acces-distant.md)
