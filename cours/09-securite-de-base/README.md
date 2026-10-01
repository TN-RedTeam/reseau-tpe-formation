# Cours 09 — La sécurité de base

🕐 Lecture : ~7 min · Niveau : débutant · ⭐ Cours essentiel

---

## 🔐 L'analogie du quotidien

Sécuriser un réseau, c'est comme **protéger un local commercial** :

- Une **bonne serrure** sur la porte (mots de passe solides).
- Un **vigile** qui filtre les entrées (le pare-feu).
- Ne pas **laisser traîner les clés** (droits d'accès bien gérés).
- Se **méfier des colis piégés** (phishing, pièces jointes douteuses).

Pas besoin d'être expert : **quelques réflexes simples** bloquent déjà l'immense
majorité des problèmes.

---

## 🧱 Les 6 réflexes essentiels en TPE

### 1. Changer tous les mots de passe par défaut

La box, le NAS, l'imprimante arrivent avec un mot de passe « admin/admin ». Les
pirates les connaissent par cœur. **Change-les immédiatement.**

### 2. Des mots de passe forts (et uniques)

Long vaut mieux que compliqué. Une **phrase** est idéale :
`Mon-Chat-Dort-Sur-Le-Clavier-2024!`

> 💡 Utilise un **gestionnaire de mots de passe** (Bitwarden, KeePass, gratuits) :
> tu ne retiens qu'un seul mot de passe « maître », il garde tous les autres.

### 3. Mettre à jour (box, PC, NAS, imprimantes)

Les mises à jour bouchent les **trous de sécurité**. Active les mises à jour
automatiques partout où c'est possible. Un appareil pas à jour = une **porte
laissée ouverte**.

### 4. Un antivirus actif et à jour

Sur Windows, **Microsoft Defender** (intégré, gratuit) suffit dans la plupart des
TPE, à condition qu'il soit **activé et à jour**.

### 5. Le pare-feu : le vigile

Le **pare-feu** (*firewall*) décide ce qui a le droit d'entrer et de sortir du
réseau. Ta box en a un, activé par défaut. **Ne le désactive jamais.**

> Image : le pare-feu, c'est le **vigile à l'entrée** qui ne laisse passer que ce
> qui est attendu.

### 6. Le principe du moindre privilège

Donne à chacun **uniquement les accès dont il a besoin**. Le comptable n'a pas
besoin d'accéder au dossier RH, et inversement. Moins de clés qui circulent = moins
de risques.

---

## 🎣 Le phishing (hameçonnage) — l'ennemi n°1

La plupart des attaques en TPE ne cassent pas une serrure : elles **demandent
gentiment la clé** par email.

- Un email « urgent » de la banque, un « colis bloqué », une « facture en pièce
  jointe »… qui te demande de **cliquer** ou **donner un mot de passe**.
- **Réflexe** : on ne clique pas dans la panique. On vérifie l'**adresse de
  l'expéditeur**, et en cas de doute, on contacte l'organisme **par un autre
  moyen** (téléphone officiel).

> 💡 La meilleure sécurité technique ne sert à rien si quelqu'un **donne son mot de
> passe**. La sensibilisation des utilisateurs fait partie de ton métier.

---

## 📶 Rappel Wi-Fi (du cours 05)

- Chiffrement **WPA2/WPA3**, jamais WEP.
- Mot de passe Wi-Fi fort.
- Un **réseau invité** séparé pour les visiteurs.

---

## ✅ Ce qu'il faut retenir

1. **Change les mots de passe par défaut** et utilise des mots de passe **forts et uniques**.
2. **Mets à jour** tout (box, PC, NAS) et garde **antivirus + pare-feu** actifs.
3. L'attaque la plus courante est le **phishing** : méfiance, on vérifie avant de cliquer.

## 🔧 À essayer

Fais le tour de **tes propres comptes importants** (email, banque). Ont-ils un
mot de passe **unique** et **fort** ? La **double authentification** (code reçu par
SMS/appli) est-elle activée ? Active-la là où c'est possible : c'est le réflexe de
sécurité le plus efficace qui existe. 🔒

> ➡️ Fais ensuite l'[exercice 09](../../exercices/09-securite-de-base.md).

---

⬅️ [Cours 08](../08-sauvegardes/) · ➡️ [Cours 10 — VPN et accès distant](../10-vpn-acces-distant/)
