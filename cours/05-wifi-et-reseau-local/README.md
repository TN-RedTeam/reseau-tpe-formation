# Cours 05 — Wi-Fi et réseau local

🕐 Lecture : ~6 min · Niveau : débutant

---

## 🔌 L'analogie du quotidien

Pour relier tes appareils à la box, tu as **deux moyens**, comme pour entrer chez
toi :

- Le **câble réseau** (Ethernet) = la **porte** : solide, rapide, fiable.
- Le **Wi-Fi** = la **fenêtre** : pratique, sans fil, mais un peu plus capricieux.

Les deux mènent au même endroit (la box). À toi de choisir selon la situation.

---

## 🧵 Câble (Ethernet) vs Wi-Fi

| | **Câble (Ethernet)** | **Wi-Fi** |
|---|---|---|
| Vitesse | ⚡ Très rapide, stable | Bonne, mais variable |
| Fiabilité | 💪 Excellente | Dépend de la distance/murs |
| Confort | Il faut tirer un câble | 📶 Aucun fil, pratique |
| Idéal pour | PC fixes, NAS, imprimante | Portables, téléphones |

> 💡 **Conseil TPE** : les appareils qui ne bougent pas (PC de bureau, NAS,
> imprimante) → **câble**. Les appareils mobiles → **Wi-Fi**. Le meilleur des deux.

---

## 📶 Comprendre le Wi-Fi en 3 mots

- **SSID** : le **nom** de ton réseau Wi-Fi (celui que tu vois dans la liste, ex :
  « Livebox-A3F2 »). *SSID = le nom affiché, point.*
- **Clé Wi-Fi** (ou mot de passe) : le **code** pour se connecter.
- **Bandes 2,4 GHz et 5 GHz** : deux « routes » du Wi-Fi.
  - **2,4 GHz** = portée longue, traverse mieux les murs, mais plus lente.
  - **5 GHz** = plus rapide, mais portée plus courte.

> 💡 Image : **2,4 GHz = la route de campagne** (va loin, roule doucement).
> **5 GHz = l'autoroute** (va vite, mais plus courte). La plupart des box gèrent
> les deux automatiquement.

---

## 🖼️ Le réseau local, vu de haut

Câble ou Wi-Fi, tout le monde finit relié à la **box**. C'est ça, le réseau local :

```
                 🌐 Internet
                     |
                [ BOX ]•••••• 📶 (Wi-Fi)
                 │ │ │           :
   (câbles) 💻──┘ │ └──💾 NAS   📱 Téléphone
            🖨️────┘            💻 Portable
```

Les appareils en **câble** ou en **Wi-Fi** sont **sur le même réseau local** : ils
peuvent donc se parler (partager fichiers, imprimante…). On verra ça au cours 06.

---

## 🛡️ Sécuriser son Wi-Fi (l'essentiel)

Trois réflexes simples (on approfondit au cours 09) :

1. **Mot de passe fort** sur le Wi-Fi (pas « 12345678 »).
2. Choisir le chiffrement **WPA2** ou **WPA3** (jamais « WEP », trop vieux).
3. Pour les visiteurs/clients → créer un **réseau invité** séparé, qui n'accède
   pas à tes fichiers.

---

## ✅ Ce qu'il faut retenir

1. **Câble = porte** (rapide, fiable) ; **Wi-Fi = fenêtre** (pratique, sans fil).
2. **SSID = le nom** du Wi-Fi ; la **clé** = le mot de passe.
3. Câble **ou** Wi-Fi, tout le monde est sur le **même réseau local** et peut se parler.

## 🔧 À essayer

Regarde la liste des réseaux Wi-Fi disponibles sur ton téléphone ou PC. Combien en
vois-tu ? Repère le **tien** (son SSID). Puis, dans les réglages Wi-Fi, regarde si
ton réseau est en **WPA2/WPA3** (c'est écrit dans les détails/propriétés du
réseau). C'est le signe d'un Wi-Fi bien sécurisé. 🔒

> ➡️ Fais ensuite l'[exercice 05](../../exercices/05-wifi-et-reseau-local.md).

---

⬅️ [Cours 04](../04-le-routeur-box/) · ➡️ [Cours 06 — Partage de fichiers et imprimantes](../06-partage-fichiers-imprimantes/)
