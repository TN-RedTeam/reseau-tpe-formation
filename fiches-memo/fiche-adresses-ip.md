# 📮 Fiche-mémo — Adresses IP

**IP = adresse postale d'un appareil sur le réseau.**

```
   192 . 168 . 1 . 25
   └──────────┘   └──┘
    le QUARTIER    le NUMÉRO
    (le réseau)    (l'appareil)
```

- Même réseau = **même quartier** (`192.168.1`), **numéros différents** (`.10`, `.11`…).
- **Masque** `255.255.255.0` = dit où s'arrête le quartier.
- **Passerelle** = l'adresse de la box (souvent `192.168.1.1`) = la porte vers internet.

## Adresses privées (chez toi)
- `192.168.x.x` ← le plus courant
- `10.x.x.x`

## Pièges
- Deux appareils avec la **même IP** → conflit, ça casse.
- IP en **`169.254.x.x`** → le DHCP n'a pas répondu (pas de vraie adresse).
- IP dans le **mauvais quartier** → l'appareil est isolé.

🔍 Voir mon IP : `ipconfig` (Windows) · `ip a` (Mac/Linux)

⬅️ [Fiches-mémo](README.md)
