# Cours 04 — Le routeur / la box

🕐 Lecture : ~6 min · Niveau : débutant

---

## 🚪 L'analogie du quotidien

Le **routeur** (ta **box** internet), c'est le **gardien d'immeuble**.

- Il est à l'**entrée** : tout ce qui entre ou sort passe par lui.
- Il **oriente le courrier** : « ce paquet est pour l'appart 25 → je le donne au PC 25 ».
- Il **parle à l'extérieur** (la ville = internet) au nom de tous les habitants.
- Il **distribue les adresses** (c'est lui le DHCP, vu au cours 03).

En TPE, **box = routeur = gardien**. C'est la pièce la plus importante du réseau.

---

## 🧭 Routeur vs switch (ne pas confondre)

Deux appareils se ressemblent, mais ne font pas la même chose :

| | **Routeur (la box)** | **Switch (multiprise réseau)** |
|---|---|---|
| Rôle | Relie ton réseau **à internet** | Relie des appareils **entre eux** |
| Analogie | Le **gardien** de l'immeuble | Une **rallonge multiprise** |
| Distribue les IP | Oui (DHCP) | Non |

👉 Quand tu n'as **pas assez de prises** sur la box, tu ajoutes un **switch**
(une « multiprise réseau ») pour brancher plus d'appareils. Il ne remplace pas la
box, il l'étend.

```
   Internet
      │
   [ BOX/Routeur ]  ← le gardien (4 prises par ex.)
      │
   [ SWITCH ]       ← la multiprise (8 prises de plus)
    │ │ │ │
   PC PC PC NAS
```

---

## 🔑 Deux adresses, deux "côtés"

La box a deux visages :

- Côté **intérieur** (ton réseau local) : une IP privée, souvent **`192.168.1.1`**.
  C'est **l'adresse de ton gardien**, celle que tu tapes pour le configurer.
- Côté **extérieur** (internet) : une IP **publique** donnée par ton fournisseur.
  C'est l'adresse de ton immeuble vue depuis « la ville ».

> 💡 L'adresse `192.168.1.1` (ou `192.168.0.1`) est ta **porte d'entrée** vers
> internet. On l'appelle la **passerelle** (*gateway* en anglais).

---

## ⚙️ L'interface d'administration

Pour régler ta box (Wi-Fi, mot de passe, etc.), tu ouvres son **interface
d'administration** :

1. Ouvre un navigateur (Chrome, Firefox…).
2. Tape l'adresse de la box dans la barre d'adresse : `192.168.1.1`.
3. Connecte-toi (identifiant/mot de passe souvent écrits **sous la box**).

Tu arrives sur un **panneau de contrôle** : c'est là qu'on gère le réseau. On y
reviendra souvent dans les prochains cours.

> ⚠️ **Règle de sécurité n°1** : change le **mot de passe par défaut** de la box.
> On en reparle au cours 09.

---

## ✅ Ce qu'il faut retenir

1. La **box = le routeur = le gardien** : elle relie ton réseau à internet.
2. Le **switch** n'est qu'une **multiprise réseau** pour ajouter des prises.
3. L'adresse de la box (souvent **`192.168.1.1`**) = ta **passerelle** + ton panneau de contrôle.

## 🔧 À essayer

Ouvre ton navigateur et tape l'adresse de ta box (`192.168.1.1` ou
`192.168.0.1`). Tu devrais voir une page de connexion : c'est le **panneau de
contrôle du gardien**. Ne change rien pour l'instant, regarde juste à quoi ça
ressemble. (Pour trouver l'adresse exacte : `ipconfig` → ligne « Passerelle ».)

> ➡️ Fais ensuite l'[exercice 04](../../exercices/04-le-routeur-box.md).

---

⬅️ [Cours 03](../03-dns-dhcp/) · ➡️ [Cours 05 — Wi-Fi et réseau local](../05-wifi-et-reseau-local/)
