# 🖧 Réseau TPE — Formation de A à Z

Bienvenue ! Ce dépôt est ta **formation complète au réseau d'entreprise**, pensée
pour partir de **zéro** et aller jusqu'à savoir **gérer l'informatique d'une
petite entreprise** (TPE : 5-6 postes, un routeur, un NAS).

> 🎯 **Objectif final** : être capable de faire du support informatique pour des
> petites structures (installer, configurer, dépanner un réseau).

---

## 🌱 Pour qui ?

- Tu pars de **zéro** en réseau : parfait, c'est fait pour ça.
- Tu veux des explications **simples, courtes, concrètes**.
- Tu préfères **une notion à la fois**, sans te noyer.

Pas besoin de matériel coûteux : on apprend avec un **simulateur gratuit** et ta
propre box internet.

---

## 🗺️ Comment utiliser ce dépôt

Le dépôt est organisé en dossiers, dans l'ordre où tu dois les parcourir :

| Dossier | À quoi ça sert |
|---|---|
| `00-demarrage/` | Par où commencer, outils à installer |
| `cours/` | Les leçons, numérotées dans l'ordre (01, 02, 03…) |
| `exercices/` | Des exercices + leurs corrigés |
| `bac-a-sable/` | Ton terrain d'entraînement (simulateur) |
| `fiches-memo/` | Des antisèches ultra-courtes (1 page) |
| `glossaire.md` | Tous les mots techniques en 1 phrase simple |

**La règle d'or** : une leçon = ~5 minutes de lecture + 1 petit truc à essayer.
Pas plus. On avance par **petites sessions de 20-30 min**.

---

## ✅ Par où commencer : suis le Parcours

👉 **[Ouvre le PARCOURS.md](PARCOURS.md)** — c'est **ton fil d'Ariane** : la liste
ordonnée de **tout** ce qu'il faut faire, avec des **cases à cocher**. Tu la suis de
haut en bas, une étape à la fois, sans jamais te demander « et maintenant ? ».

Le parcours est découpé en **6 phases** (du plus simple au plus complet) :

| Phase | Tu fais… |
|---|---|
| 🟢 **0. Démarrage** | Prérequis, comment utiliser le dépôt |
| 📘 **1. Comprendre** | Les 11 cours de base + leurs exercices |
| 🧪 **2. Pratiquer** | Le [bac à sable](bac-a-sable/) : installer le simulateur, puis les TP **dans l'ordre** |
| 🎁 **3. Bonus** | La téléphonie VoIP |
| 🏢 **4. PME** | Active Directory, VLAN, serveur, cloud, RGPD… |
| 💼 **5. Le métier** | [Infogérance](infogerance/), [exploitation](exploitation/), [cas pratique](cas-pratique/) |
| 🧑‍💼 **6. Administration** | [Admin serveur Windows & Linux](administration/) + TP en labo virtuel |

> 💡 **Règle anti-dispersion** : on **termine une phase avant la suivante**, et on ne
> saute pas devant. Chaque session dure **20-30 min**. Perdu ? Reviens au
> **[Parcours](PARCOURS.md)**.

---

## 📚 Les modules de cours

1. [C'est quoi un réseau ?](cours/01-c-est-quoi-un-reseau/)
2. [Les adresses IP](cours/02-adresses-ip/)
3. [DNS et DHCP](cours/03-dns-dhcp/)
4. [Le routeur / la box](cours/04-le-routeur-box/)
5. [Wi-Fi et réseau local](cours/05-wifi-et-reseau-local/)
6. [Partage de fichiers et imprimantes](cours/06-partage-fichiers-imprimantes/)
7. [Le NAS (stockage partagé)](cours/07-nas-stockage-partage/)
8. [Les sauvegardes](cours/08-sauvegardes/)
9. [La sécurité de base](cours/09-securite-de-base/)
10. [VPN et accès distant](cours/10-vpn-acces-distant/)
11. [Diagnostic et dépannage](cours/11-diagnostic-depannage/)
12. 🎁 [La téléphonie VoIP](cours/12-voip-telephonie/) *(module bonus)*

**🏢 Niveau PME (passer de la TPE à la PME) :**

13. [Active Directory & le domaine](cours/13-active-directory-domaine/)
14. [VLAN & segmentation réseau](cours/14-vlan-segmentation/)
15. [Le serveur d'entreprise](cours/15-serveur-entreprise/)
16. [Le switch managé](cours/16-switch-manage/)
17. [L'onduleur (UPS)](cours/17-onduleur-ups/)

**☁️ Cloud & conformité :**

18. [Le cloud & le SaaS](cours/18-cloud-et-saas/)
19. [Microsoft 365 (et Google Workspace)](cours/19-microsoft-365/)
20. [Le RGPD pour TPE/PME](cours/20-rgpd-tpe-pme/)

> 💡 Certains cours contiennent des **schémas Mermaid** (dessins générés
> automatiquement par GitHub) en plus des schémas ASCII. Tu les vois directement
> en ouvrant le cours sur GitHub ; dans VS Code, ils s'affichent dans l'aperçu
> Markdown (`Ctrl+Shift+V`).

---

## 💼 Devenir infogéreur (le métier)

La technique, c'est la moitié du chemin. Pour **gérer l'IT de plusieurs TPE/PME,
du premier contact au contrat mensuel**, deux sections dédiées :

- 💼 [**Métier d'infogérance**](infogerance/) — prospection, audit, devis, **contrat
  mensuel & SLA**, tarification, onboarding (+ modèles prêts à remplir : audit,
  contrat, devis, fiche d'intervention…).
- 🛠️ [**Exploitation au quotidien**](exploitation/) — supervision/RMM, prise en main à
  distance, ticketing, maintenance préventive, documentation client, gestion des
  accès (+ checklists et modèles).
- 🎯 [**Cas pratique fil rouge**](cas-pratique/) — un client fictif (cabinet comptable
  Durand) suivi **de l'audit au contrat mensuel**, avec **tous les modèles remplis** en
  exemple. Le meilleur moyen de voir la théorie en action.
- 🧑‍💼 [**Administration réseau & serveur**](administration/) — le track **pratique** :
  comptes/droits, Windows Server & Active Directory, GPO, droits NTFS, Linux serveur
  (SSH), DHCP/DNS serveur, logs, sauvegarde & sécurisation (+ **6 TP en machines
  virtuelles gratuites**).

---

## 🧰 Les raccourcis utiles

- 📖 [Glossaire](glossaire.md) — un mot que tu ne comprends pas ? Il est là.
- 🗂️ [Fiches-mémo](fiches-memo/) — les antisèches à imprimer.
- 🧪 [Bac à sable](bac-a-sable/) — pour pratiquer pour de vrai.

---

👉 **Tu commences maintenant ?** Ouvre le **[Parcours](PARCOURS.md)** et suis-le de haut
en bas. (Il démarre par [`00-demarrage/`](00-demarrage/).)

Bon courage, tu vas y arriver. 💪
