# Cours 10 — VPN et accès distant

🕐 Lecture : ~6 min · Niveau : débutant

---

## 🚇 L'analogie du quotidien

Tu es en télétravail, chez toi, et tu veux accéder aux fichiers du **bureau**
comme si tu y étais. Mais entre chez toi et le bureau, il y a tout internet : une
**ville pleine de monde** où tes données pourraient être lues.

Le **VPN** (*Virtual Private Network* = « réseau privé virtuel »), c'est un
**tunnel privé et fermé** qui relie directement ta maison au bureau. Personne, dans
la ville, ne peut voir ce qui circule dedans.

```
   🏠 Chez toi ====[ tunnel VPN sécurisé ]==== 🏢 Bureau
                  (chiffré, personne ne lit)
```

Une fois dans le tunnel, c'est **comme si ton PC était branché au réseau du
bureau** : tu accèdes au NAS, aux partages, etc.

---

## 🎯 À quoi sert un VPN en TPE

- **Télétravail** : accéder aux fichiers et à l'imprimante du bureau depuis chez soi.
- **Déplacement** : le commercial consulte les documents de l'entreprise en clientèle.
- **Sécurité sur Wi-Fi public** : dans un café/hôtel, le VPN chiffre ta connexion
  pour que personne autour ne t'espionne.

> ⚠️ Attention à ne pas confondre deux usages du mot « VPN » :
> - Le **VPN d'entreprise** (celui qu'on voit ici) : relie à **ton** réseau pro.
> - Le **VPN grand public** (NordVPN, etc.) : sert surtout à masquer sa position/IP.
>   Ce n'est **pas** la même chose. Ici, on parle du premier.

---

## 🔑 Le chiffrement, cœur du VPN

« Chiffrer », c'est **transformer les données en charabia illisible** pour tous,
sauf pour celui qui a la **clé** (les deux bouts du tunnel).

Même si quelqu'un intercepte le trafic dans « la ville », il ne voit que du charabia.
C'est ce qui rend le tunnel **privé**.

---

## 🛠️ Comment on le met en place (vue d'ensemble)

En TPE, deux approches simples :

1. **Le VPN de la box / du NAS** : beaucoup de box et de NAS (Synology, QNAP) ont
   un **serveur VPN intégré**. On l'active, on crée un compte par utilisateur, et
   chacun se connecte depuis chez lui avec une appli. Simple et économique. ✅
2. **Une solution moderne type WireGuard / Tailscale** : rapide à installer, très
   sécurisée, de plus en plus populaire. Tailscale est particulièrement facile pour
   débuter (peu de configuration).

Le principe est toujours le même :
- Un **serveur VPN** côté bureau (sur la box ou le NAS).
- Un **client VPN** sur chaque appareil distant (appli sur le PC/téléphone).
- Des **comptes/clés** pour authentifier chaque personne.

---

## 🧭 Accès distant SANS VPN (à connaître, mais prudence)

On peut aussi exposer un service (ex : le NAS) directement sur internet via une
**redirection de port** sur la box. ⚠️ **C'est risqué** : ça ouvre une porte vers
l'extérieur. En TPE, **préfère le VPN**, bien plus sûr. Si tu dois le faire,
mets des mots de passe béton et des mises à jour à jour (cours 09).

---

## ✅ Ce qu'il faut retenir

1. Un **VPN** = un **tunnel privé et chiffré** entre un appareil distant et ton réseau.
2. Il sert surtout au **télétravail** et à sécuriser les connexions hors du bureau.
3. En TPE, active le **VPN de la box ou du NAS** (ou Tailscale) ; évite les
   redirections de port ouvertes.

## 🔧 À essayer

Va voir la page produit de **Tailscale** (tailscale.com) ou la doc VPN de
**Synology**. Lis juste la page « comment ça marche » / « getting started ». Tu
verras que monter un VPN moderne tient en quelques étapes. Pas besoin d'installer
quoi que ce soit aujourd'hui : repère juste à quoi ça ressemble.

> ➡️ Fais ensuite l'[exercice 10](../../exercices/10-vpn-acces-distant.md).

---

⬅️ [Cours 09](../09-securite-de-base/) · ➡️ [Cours 11 — Diagnostic et dépannage](../11-diagnostic-depannage/)
