# TP06 — Le grand scénario de panne

🎯 **Objectif** : jouer au **dépanneur**. On casse volontairement le réseau, tu
diagnostiques et tu répares, avec la méthode du cours 11.
🕐 Durée : ~40 min · Prérequis : TP04, cours 11 (diagnostic).

> 🎓 C'est l'épreuve finale ! Elle rassemble presque tout ce que tu as appris.

---

## 🧰 Préparation

Ouvre `tp04.pkt` (ton réseau TPE complet qui **fonctionne**). Vérifie d'abord que
tout va bien (un `ping` du serveur depuis un PC répond). On part d'un réseau sain.

> ⚠️ **Reste en mode `Realtime`** (bouton en bas à droite) pendant tout ce TP : c'est ce
> qui fait que tes `ping` répondent tout de suite. En mode **Simulation**, le ping semble
> « bloqué » tant que tu n'appuies pas sur Play ▶ — ce n'est **pas** une panne, juste le
> mode ralenti. 😉
>
> 🧠 Rappel topologie : chaque PC a **son propre câble** vers le switch (montage en
> **étoile**). Débrancher **un** PC n'isole **que celui-là** — les autres continuent de se
> parler via le switch. C'est tout l'intérêt de la question « un seul PC, ou tout le monde ? ».

---

## 🎭 Les 3 pannes à provoquer puis réparer

Fais-les **une par une**. Pour chacune : **casse**, **diagnostique** avec tes
outils, **trouve** la cause, **répare**, puis **vérifie**.

> 💡 Méthode (cours 11) : câble → IP → box → internet → DNS, et « un seul ou tout
> le monde ? ».

---

### 🔧 Panne 1 — Le câble débranché

**Casser** : clique sur le câble entre `PC0` et le switch → supprime-le (outil
*Delete*, l'icône croix 🗙), ou débranche-le.

**À toi de jouer** :
1. Depuis `PC0`, tente `ping 192.168.1.1`. Que se passe-t-il ?
2. Est-ce que **les autres PC** ont le problème aussi ? (teste depuis `PC1`)
3. Que t'indique la réponse à la question 2 ?

<details>
<summary>👉 Voir la solution</summary>

- `PC0` ne ping plus rien ; les autres PC fonctionnent.
- « Un seul PC touché » → le problème est **sur PC0** (ou son câble).
- Indice visuel : le point de liaison est **rouge/absent** côté PC0.
- **Réparation** : rebranche un câble droit entre `PC0` et le switch. Le point
  redevient vert, le ping remarche. ✅

</details>

---

### 🔧 Panne 2 — La mauvaise adresse IP

**Casser** : sur `PC1`, passe en **Static** et mets une IP d'un **autre quartier** :
`192.168.**5**.11` (gateway `192.168.1.1`).

**À toi de jouer** :
1. Depuis `PC1`, `ping 192.168.1.1` : ça répond ?
2. Fais `ipconfig` sur `PC1` : quelque chose te choque dans l'adresse ?
3. Compare avec un PC qui marche.

<details>
<summary>👉 Voir la solution</summary>

- Le ping échoue : `PC1` est dans le quartier `192.168.5`, pas `192.168.1`.
- Il ne peut pas joindre la box (`192.168.1.1`), qui est dans un autre quartier.
- **Réparation** : remets `PC1` en **DHCP** (ou IP statique correcte
  `192.168.1.x`). Le ping remarche. ✅
- 🧠 Leçon : une IP dans le **mauvais quartier** isole la machine (rappel cours 02).

</details>

---

### 🔧 Panne 3 — Le DHCP éteint

**Casser** : sur `Server0` → Services → **DHCP** → mets **Service : Off**. Puis sur
`PC2`, repasse l'IP Configuration en **DHCP** (il va redemander une adresse).

**À toi de jouer** :
1. Sur `PC2`, l'obtention d'adresse réussit-elle ?
2. Fais `ipconfig` : quelle adresse a-t-il ? (indice : `169.254.x.x` ?)
3. Qui est en cause : le PC, ou un service du réseau ?

<details>
<summary>👉 Voir la solution</summary>

- `PC2` affiche « DHCP request failed » et récupère une adresse en `169.254.x.x`.
- `169.254.x.x` = **le DHCP n'a pas répondu** (rappel cours 11).
- Ce n'est pas le PC le fautif : c'est le **service DHCP du serveur** qui est éteint.
- **Réparation** : sur `Server0`, rallume le **DHCP (Service : On)**, puis sur `PC2`
  re-coche DHCP → il reçoit enfin une bonne adresse. ✅

</details>

---

## 🏁 Bilan

Tu as diagnostiqué et réparé **3 pannes classiques** avec une méthode. C'est
exactement le quotidien du support IT en TPE.

- Panne 1 → **couche physique** (câble).
- Panne 2 → **adressage IP** (mauvais quartier).
- Panne 3 → **service réseau** (DHCP).

## 🧠 Défi bonus

Demande à quelqu'un de **casser une chose au hasard** dans ta maquette pendant que
tu as le dos tourné, puis **retrouve et répare** la panne en appliquant la méthode.
Chronomètre-toi. 😎

---

🎉 **Félicitations, tu as terminé la Phase 2 (pratique) !** Tu sais monter, configurer et
dépanner un réseau de TPE.

**La suite dans le [Parcours](../../PARCOURS.md)** → Phase 3 : le module bonus
[**VoIP (cours 12)**](../../cours/12-voip-telephonie/).

⬅️ [TP05](tp05-acces-distant.md) · 🧭 [Parcours](../../PARCOURS.md)
