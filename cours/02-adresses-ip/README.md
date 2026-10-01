# Cours 02 — Les adresses IP

🕐 Lecture : ~5 min · Niveau : débutant

---

## 📮 L'analogie du quotidien

Une **adresse IP**, c'est comme une **adresse postale**.

Pour recevoir du courrier, ta maison a une adresse unique : *12 rue des Lilas*.
De la même façon, pour recevoir des informations sur le réseau, chaque appareil a
une adresse unique : son **adresse IP** (par exemple `192.168.1.25`).

Sans adresse, le facteur ne saurait pas où livrer. Sans adresse IP, le réseau ne
saurait pas à quel appareil envoyer les données.

---

## 🔢 À quoi ça ressemble

Une adresse IP (version courante, dite **IPv4**), c'est **4 nombres séparés par
des points**, chacun entre 0 et 255 :

```
192 . 168 . 1 . 25
 │     │    │   │
 └─────┴────┘   └──► le numéro de l'appareil (sa "maison")
   le quartier       (ici : appareil n°25)
 (le réseau local)
```

- La **première partie** (`192.168.1`) = le **quartier** (ton réseau local).
- La **dernière partie** (`.25`) = le **numéro de la maison** (l'appareil précis).

Tous les appareils d'un même réseau partagent le **même quartier** et ont un
**numéro différent**. Comme les maisons d'une même rue.

---

## 🏠 Les adresses "privées" (chez toi)

Dans presque toutes les box et TPE, les adresses du réseau local commencent par :

- `192.168.___.___` (le plus courant)
- parfois `10.___.___.___`

Ce sont des adresses **privées** : elles n'existent que **chez toi**, dans ton
immeuble. Le voisin peut avoir un appareil en `192.168.1.25` lui aussi, sans
conflit, car c'est **son** immeuble à lui.

> 💡 C'est comme « appartement n°3 » : il y en a un dans chaque immeuble, mais ça
> ne pose pas de problème tant qu'on reste dans le bon immeuble.

---

## 🎭 Le masque de sous-réseau (en douceur)

Tu verras souvent un deuxième nombre à côté de l'IP : le **masque**, souvent
`255.255.255.0`.

Son seul rôle : **dire où s'arrête le "quartier"**. Avec `255.255.255.0`, il dit
« les 3 premiers nombres = le quartier, le dernier = la maison ». C'est tout.

Pour l'instant, retiens juste : **masque = la limite du quartier**. On y revient
plus tard, pas besoin de calculer quoi que ce soit aujourd'hui.

---

## ✅ Ce qu'il faut retenir

1. Une **adresse IP** = l'**adresse postale** d'un appareil sur le réseau.
2. Elle a 2 parties : le **quartier** (réseau) + le **numéro** (l'appareil).
3. Chez toi, les IP commencent souvent par **`192.168.`** (adresses privées).

## 🔧 À essayer

Trouve l'adresse IP de ton ordinateur :

- **Windows** : ouvre l'*Invite de commandes* (tape `cmd` dans le menu Démarrer),
  puis tape `ipconfig` et appuie sur Entrée. Cherche la ligne **« Adresse IPv4 »**.
- **Mac/Linux** : ouvre le *Terminal* et tape `ip a` (ou `ifconfig`).

Note ton adresse. Elle commence par `192.168.` ? Bravo, tu viens de lire
l'adresse postale de ton PC. 🎉

> ➡️ Fais ensuite l'[exercice 02](../../exercices/02-adresses-ip.md).

---

⬅️ [Cours 01](../01-c-est-quoi-un-reseau/) · ➡️ [Cours 03 — DNS et DHCP](../03-dns-dhcp/)
