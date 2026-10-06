# 🧰 La boîte à outils de l'infogéreur (benchmark)

> 📌 **Rubrique « pour plus tard ».** Pas besoin de tout installer maintenant ! C'est ta
> **bibliothèque de référence** : quand tu auras un vrai besoin (superviser, sauvegarder,
> ticketer…), reviens ici choisir le bon outil.

Pour chaque catégorie : un **tableau comparatif** (💶 modèle économique · 🔓 open source ·
avantages · inconvénients) et **ma reco pour démarrer**.

> ⚠️ **Les tarifs et licences bougent vite** (surtout chez les éditeurs : rachats,
> changements de « free tier »…). Vérifie toujours le prix **à jour** avant de t'engager.
> Ici je donne le **modèle** (gratuit / freemium / payant) et le statut **open source**,
> plus stables qu'un prix exact. Repères : **Gratuit** = utilisable sans payer ·
> **Freemium** = gratuit limité, payant au-delà · **Payant** = commercial.

---

## 🧭 Sommaire des catégories

1. [Supervision & RMM](#1-supervision--rmm)
2. [Prise en main à distance](#2-prise-en-main-à-distance)
3. [Supervision d'infrastructure (monitoring)](#3-supervision-dinfrastructure-monitoring)
4. [Ticketing / helpdesk / inventaire](#4-ticketing--helpdesk--inventaire)
5. [Sauvegarde](#5-sauvegarde)
6. [Antivirus / EDR](#6-antivirus--edr)
7. [Gestionnaire de mots de passe](#7-gestionnaire-de-mots-de-passe)
8. [Documentation & inventaire IT](#8-documentation--inventaire-it)
9. [Virtualisation](#9-virtualisation)
10. [VPN / accès distant sécurisé](#10-vpn--accès-distant-sécurisé)
11. [Outils réseau & diagnostic](#11-outils-réseau--diagnostic)
12. [Microsoft 365 / cloud (gestion MSP)](#12-microsoft-365--cloud-gestion-msp)
13. [Déploiement & automatisation](#13-déploiement--automatisation)
14. [Gestion de l'activité (devis, factures)](#14-gestion-de-lactivité-devis-factures)
15. [Audit & inventaire client (découverte du parc)](#15-audit--inventaire-client-découverte-du-parc)
16. [🎒 La stack recommandée pour démarrer](#-la-stack-recommandée-pour-démarrer)

> 🔓 **Tu veux du 100 % open source & auto-hébergé ?** → va directement à la
> [**stack souveraine**](#-priorité-open-source--auto-hébergé-la-stack-souveraine).

---

## 🔓 Priorité open source & auto-hébergé : la stack souveraine

Ce sont **TES outils de travail** d'infogéreur (ton **back-office** : gérer ton activité et
tes clients), à mettre **au nom de ta société**. C'est **ici** que ta priorité « open source
+ auto-hébergé » prend tout son sens : **tes** données restent chez toi, rien chez un éditeur
SaaS qui pourrait se faire pirater.

> 👉 À **ne pas confondre** avec les **logiciels déployés chez le client** (antivirus/EDR,
> Microsoft 365, sauvegarde des données du client…). Ceux-là, tu choisis **le meilleur pour
> lui** (souvent commercial) et tu les mets **au nom du client** →
> [au nom de qui ?](../exploitation/06-gestion-acces-mots-de-passe.md#au-nom-de-qui--propriété-des-licences).

> 💡 **Chaque outil ci-dessous est cliquable** : un clic = son **site officiel**.

| Besoin (ton back-office) | 🔓 Outil open source auto-hébergeable | Remplace (SaaS/proprio) | Note |
|---|---|---|---|
| RMM | [**Tactical RMM**](https://tacticalrmm.com) | Atera, NinjaOne | Complet ; hébergement un peu technique |
| Prise à distance | [**MeshCentral**](https://meshcentral.com), [**RustDesk**](https://rustdesk.com), [**Guacamole**](https://guacamole.apache.org) | AnyDesk, TeamViewer | Guacamole = RDP/SSH/VNC par navigateur |
| Monitoring | [**Zabbix**](https://www.zabbix.com) · [**Checkmk**](https://checkmk.com) · [**Uptime Kuma**](https://github.com/louislam/uptime-kuma) · [**Grafana**](https://grafana.com) | PRTG | Matures |
| Ticketing + inventaire | [**GLPI**](https://glpi-project.org) (+ agent) | Freshdesk, Autotask | Référence FR, très complet |
| Sauvegarde (tes outils) | [**UrBackup**](https://www.urbackup.org) · [**Bareos**](https://www.bareos.org) · [**Kopia**](https://kopia.io) · [**PBS**](https://www.proxmox.com/en/proxmox-backup-server) | Veeam | Solide (⚠️ sauvegarde M365 = côté client) |
| Mots de passe | [**Vaultwarden**](https://github.com/dani-garcia/vaultwarden) · [**KeePassXC**](https://keepassxc.org) · [**Passbolt**](https://www.passbolt.com) | Bitwarden cloud, Keeper | ✅ Excellent, aucun compromis |
| Documentation | [**BookStack**](https://www.bookstackapp.com) · [**Wiki.js**](https://js.wiki) · [**Docmost**](https://docmost.com) · [**NetBox**](https://netbox.dev) | Hudu, IT Glue | Très bon |
| Virtualisation | [**Proxmox VE**](https://www.proxmox.com) | VMware | ✅ Référence |
| VPN | [**WireGuard**](https://www.wireguard.com) · [**OpenVPN**](https://openvpn.net) · [**Headscale**](https://github.com/juanfont/headscale) · [**Netbird**](https://netbird.io) · [**Firezone**](https://www.firezone.dev) | Tailscale cloud | ✅ Excellent |
| Diagnostic | [**nmap**](https://nmap.org) · [**Wireshark**](https://www.wireshark.org) · [**Angry IP**](https://angryip.org) · [**PuTTY**](https://www.chiark.greenend.org.uk/~sgtatham/putty/) · [**WinSCP**](https://winscp.net) · [**Remmina**](https://remmina.org) | Advanced IP Scanner, MobaXterm | ✅ Déjà tout OSS |
| Gestion M365 (ton portail) | [**CIPP**](https://cipp.app) | — | Pour administrer les tenants clients |
| Déploiement / auto | [**Ansible**](https://www.ansible.com) · [**OPSI**](https://www.opsi.org) · [**FOG**](https://fogproject.org) | PDQ | Puissant |
| Facturation / gestion | [**Dolibarr**](https://www.dolibarr.org) (tu l'as déjà !) · [**Odoo Community**](https://www.odoo.com/page/community) · [**Invoice Ninja**](https://www.invoiceninja.com) | — | Voir note facture électronique |

### 🧑‍💼 Et les logiciels déployés CHEZ le client ?

Ce ne sont **pas** « tes outils » : tu choisis **le plus efficace pour le client** (souvent
commercial, l'open source n'est pas le critère), et tu les mets **au nom du client** (toi, tu
as l'accès admin — voir [au nom de qui ?](../exploitation/06-gestion-acces-mots-de-passe.md#au-nom-de-qui--propriété-des-licences)).

- **Antivirus / EDR** : pas d'équivalent OSS aussi bon qu'un EDR commercial sur Windows →
  **Microsoft Defender** (intégré, piloté par GPO/Intune) ± **Wazuh** (OSS, détection), ou une
  solution commerciale (Bitdefender/ESET).
- **Sauvegarde Microsoft 365** : offre OSS immature → solution dédiée (au nom du client).

### 🧾 Note — facture électronique (réforme FR 2026-2027)

- Réception obligatoire pour **toutes** les entreprises : **1ᵉʳ sept. 2026** ; émission
  **TPE/PME** : **1ᵉʳ sept. 2027**. Format **structuré** (Factur-X / UBL / CII) + passage par
  une **Plateforme Agréée (PA)** (ex-« PDP »).
- **Dolibarr reste conforme** : Factur-X natif, **module eInvoicing gratuit** (DoliStore),
  **v17 minimum (v19 recommandée)**, à **connecter à une Plateforme Agréée**. → Pas besoin de
  changer d'outil, juste de le mettre à jour et de le brancher à une PA.
- ⚠️ Réglementation **mouvante** : vérifie dates et terminologie sur **impots.gouv.fr**.

### ⚖️ Le vrai compromis de l'auto-hébergement

Tout héberger toi-même = **souveraineté** totale… mais **tu deviens responsable** de
l'hébergement, des **mises à jour**, de la **sécurité** et de la **sauvegarde** de ces outils.
C'est une charge réelle. Bon équilibre pragmatique : auto-héberge en priorité ce qui contient
les **données sensibles** (mots de passe → Vaultwarden, doc, sauvegardes), et accepte un outil
clé-en-main là où l'OSS est faible (EDR).

---

## 1. Supervision & RMM

*(Surveiller et gérer à distance tout le parc — l'outil central de l'infogéreur. Voir
[exploitation 01](../exploitation/01-supervision-rmm.md).)*

| Outil | 💶 | 🔓 | Avantages | Inconvénients |
|---|---|---|---|---|
| **TacticalRMM** | Gratuit (self-host) | ✅ Oui | Complet, gratuit, prise à distance intégrée | Auto-hébergement technique, support communautaire |
| **Action1** | Freemium | ❌ Non | Très bon patch management, gratuit jusqu'à un quota de postes, cloud | Moins « tout-en-un » qu'un vrai RMM |
| **Atera** | Payant | ❌ Non | Facturé **par technicien** (endpoints illimités) → économique en grossissant, RMM+PSA intégrés | Abonnement, pas open source |
| **NinjaOne** | Payant | ❌ Non | Très abouti, ergonomique, fiable | Facturé **par endpoint**, coût qui grimpe avec le parc |
| **Pulseway** | Payant | ❌ Non | Excellente app mobile, léger | Moins complet sur le PSA |
| **MeshCentral** | Gratuit (self-host) | ✅ Oui | Gestion + prise à distance web, gratuit | Surtout remote/monitoring léger, pas un RMM complet |

> 🎯 **Pour démarrer** : **TacticalRMM** si tu es à l'aise avec l'auto-hébergement (0 €),
> ou **Action1** (cloud, free tier) pour commencer sans serveur. En montant en charge,
> **Atera** (par technicien) est souvent le meilleur rapport qualité/prix pour un MSP solo.

---

## 2. Prise en main à distance

*(Dépanner sans se déplacer. Voir [exploitation 02](../exploitation/02-prise-en-main-distance.md).)*

| Outil | 💶 | 🔓 | Avantages | Inconvénients |
|---|---|---|---|---|
| **RustDesk** | Gratuit | ✅ Oui | Gratuit, relais auto-hébergeable, léger | Interface moins polie, à sécuriser soi-même |
| **MeshCentral** | Gratuit | ✅ Oui | Web, multi-postes, gratuit | Mise en place technique |
| **AnyDesk** | Freemium | ❌ Non | Rapide, fiable, répandu | Payant en usage pro |
| **TeamViewer** | Freemium | ❌ Non | Très complet, universel | Cher en pro, détection d'« usage commercial » agressive |
| **Apache Guacamole** | Gratuit | ✅ Oui | RDP/SSH/VNC **dans le navigateur**, sans client | Installation technique |

> 🎯 **Pour démarrer** : **RustDesk** (gratuit, open source) ou la prise à distance
> **intégrée à ton RMM** (le plus pro : un clic depuis la fiche machine).

---

## 3. Supervision d'infrastructure (monitoring)

*(Surveiller serveurs/réseau en profondeur : dispo, charge, capteurs. Complément du RMM.)*

| Outil | 💶 | 🔓 | Avantages | Inconvénients |
|---|---|---|---|---|
| **Uptime Kuma** | Gratuit | ✅ Oui | Ultra simple, joli, alertes, parfait TPE | Monitoring « est-ce en ligne ? », basique |
| **Zabbix** | Gratuit | ✅ Oui | Très puissant, complet, mature | Courbe d'apprentissage raide |
| **Checkmk** | Freemium | ⚠️ Édition Raw open source | Puissant, édition gratuite complète | Fonctions avancées payantes |
| **Grafana + Prometheus** | Gratuit | ✅ Oui | Tableaux de bord superbes, standard du marché | Deux outils à assembler |
| **PRTG** | Freemium | ❌ Non | Simple, gratuit jusqu'à 100 capteurs | Payant au-delà, Windows |
| **LibreNMS / Nagios** | Gratuit | ✅ Oui | Référence réseau/SNMP | Configuration technique |

> 🎯 **Pour démarrer** : **Uptime Kuma** (5 min à installer, suffit à 90 % des TPE). Pour
> une PME avec serveurs/switchs managés : **Zabbix** ou **Checkmk**.

---

## 4. Ticketing / helpdesk / inventaire

*(Tracer et prioriser les demandes. Voir [exploitation 03](../exploitation/03-ticketing-helpdesk.md).)*

| Outil | 💶 | 🔓 | Avantages | Inconvénients |
|---|---|---|---|---|
| **GLPI** | Gratuit | ✅ Oui | **Tickets + inventaire du parc**, très répandu en France | Interface un peu datée |
| **Zammad** | Freemium | ✅ Oui (self-host) | Moderne, multi-canal | SaaS payant, self-host technique |
| **osTicket** | Gratuit | ✅ Oui | Simple, éprouvé | Vieillissant |
| **Freshdesk** | Freemium | ❌ Non | SaaS clé en main, bon free tier | Fonctions pro payantes |
| **Autotask / ConnectWise** | Payant | ❌ Non | PSA complets pour MSP (facturation, contrats) | Chers, pour structures établies |

> 🎯 **Pour démarrer** : **GLPI** — gratuit, et il cumule **helpdesk + inventaire
> automatique du parc**, deux besoins d'un coup.

---

## 5. Sauvegarde

*(Le sujet le plus critique. Voir [cours 08](../cours/08-sauvegardes/).)*

| Outil | 💶 | 🔓 | Avantages | Inconvénients |
|---|---|---|---|---|
| **Veeam** | Freemium | ❌ Non | **Référence** VM/serveurs, Community Edition gratuite (quota de charges) | Payant au-delà, orienté infra |
| **Synology Active Backup** | Gratuit* | ❌ Non | Sauvegarde **PC/serveurs/M365** gratuite *si tu as un NAS Synology* | Nécessite le matériel Synology (*payant) |
| **UrBackup** | Gratuit | ✅ Oui | Images + fichiers, postes & serveurs, central | Interface rustique |
| **Restic / BorgBackup** | Gratuit | ✅ Oui | Léger, chiffré, dédupliqué, idéal serveurs Linux | En ligne de commande |
| **Duplicati** | Gratuit | ✅ Oui | GUI, vers le cloud, chiffré | Historiquement quelques soucis de fiabilité → **tester les restaurations** |
| **Sauvegarde M365** (Afi, Veeam M365, Synology ABM) | Payant / Gratuit* | Varie | Protège mails/SharePoint (le cloud n'est PAS sauvegardé !) | Coût ou matériel |

> 🎯 **Pour démarrer** : **Veeam Community** pour les serveurs/VM, et **Synology Active
> Backup** si le client a un NAS Synology (couvre postes + serveurs + M365, gratuitement).
> ⚠️ Quel que soit l'outil : **règle 3-2-1 + test de restauration mensuel** (cours 08).

---

## 6. Antivirus / EDR

*(Protection des postes. EDR = détection comportementale avancée. Voir [cours 09](../cours/09-securite-de-base/).)*

| Outil | 💶 | 🔓 | Avantages | Inconvénients |
|---|---|---|---|---|
| **Microsoft Defender** | Gratuit | ❌ Non | Intégré à Windows, correct, sans surcoût | Gestion centralisée = payante (Defender for Business via M365) |
| **Bitdefender GravityZone** | Payant | ❌ Non | Excellente détection, console MSP multi-clients | Payant par poste |
| **ESET PROTECT** | Payant | ❌ Non | Léger, fiable, console centrale | Payant |
| **Malwarebytes** | Freemium | ❌ Non | Bon en complément/nettoyage | Version gratuite = à la demande |
| **Wazuh** | Gratuit | ✅ Oui | XDR/SIEM open source, très puissant | Technique, pour profils avancés |

> 🎯 **Pour démarrer** : **Defender** suffit sur une TPE bien tenue. Dès que tu gères
> plusieurs clients, une **console centralisée** (Bitdefender/ESET) te fait gagner un temps
> fou et montre les alertes de tous tes clients au même endroit.

---

## 7. Gestionnaire de mots de passe

*(Ta responsabilité n°1. Voir [exploitation 06](../exploitation/06-gestion-acces-mots-de-passe.md).)*

| Outil | 💶 | 🔓 | Avantages | Inconvénients |
|---|---|---|---|---|
| **Bitwarden** | Freemium | ✅ Oui | Multi-organisations, partage d'équipe, pro abordable | Fonctions entreprise payantes |
| **Vaultwarden** | Gratuit | ✅ Oui | Serveur Bitwarden auto-hébergé, 0 € | À héberger et sécuriser soi-même |
| **KeePassXC** | Gratuit | ✅ Oui | Local, robuste, gratuit | Partage multi-clients peu pratique |
| **Keeper / 1Password** | Payant | ❌ Non | Pro, fonctions MSP, ergonomie | Abonnement |
| **Passbolt** | Freemium | ✅ Oui | Orienté équipe, auto-hébergeable | Technique |

> 🎯 **Pour démarrer** : **Bitwarden** (cloud, organisations par client) ou **Vaultwarden**
> (self-host gratuit). **Cloisonne par client** et **2FA obligatoire** sur le coffre.

---

## 8. Documentation & inventaire IT

*(Le « classeur » de chaque client. Voir [exploitation 05](../exploitation/05-documentation-client.md).)*

| Outil | 💶 | 🔓 | Avantages | Inconvénients |
|---|---|---|---|---|
| **BookStack** | Gratuit | ✅ Oui | Wiki simple et structuré, gratuit | Pas spécialisé IT |
| **Wiki.js** | Gratuit | ✅ Oui | Moderne, flexible | Mise en place technique |
| **GLPI** | Gratuit | ✅ Oui | Inventaire auto + base de connaissances | Doc moins souple qu'un wiki |
| **NetBox** | Gratuit | ✅ Oui | Référence inventaire **réseau** (IP, VLAN, racks) | Pour réseaux structurés |
| **Hudu** | Payant | ❌ Non | **Référence doc MSP**, mots de passe liés, relations | Payant |
| **IT Glue** | Payant | ❌ Non | Très complet pour MSP établis | Cher |

> 🎯 **Pour démarrer** : **BookStack** (ou GLPI que tu as déjà pour le ticketing). Un
> dossier structuré + coffre à mots de passe suffit au tout début (cf. modèle
> [dossier client](../exploitation/modeles/modele-dossier-client.md)).

---

## 9. Virtualisation

*(Faire tourner des serveurs virtuels. Voir [cours 15](../cours/15-serveur-entreprise/).)*

| Outil | 💶 | 🔓 | Avantages | Inconvénients |
|---|---|---|---|---|
| **Proxmox VE** | Gratuit | ✅ Oui | Hyperviseur pro gratuit, cluster, sauvegarde intégrée | Support payant (optionnel) |
| **VirtualBox** | Gratuit | ✅ Oui | Parfait pour le **labo** sur ton PC | Pas pour la production |
| **Hyper-V** | Gratuit* | ❌ Non | Inclus dans Windows Pro/Server | Écosystème Microsoft |
| **VMware ESXi / vSphere** | Payant | ❌ Non | Standard historique en entreprise | Offre gratuite supprimée (rachat Broadcom), coûteux |

> 🎯 **Pour démarrer** : **VirtualBox** pour apprendre (tes TP d'admin), **Proxmox** pour
> un vrai serveur de production chez un client.

---

## 10. VPN / accès distant sécurisé

*(Accès au réseau à distance. Voir [cours 10](../cours/10-vpn-acces-distant/).)*

| Outil | 💶 | 🔓 | Avantages | Inconvénients |
|---|---|---|---|---|
| **WireGuard** | Gratuit | ✅ Oui | Moderne, rapide, sûr, standard | Configuration manuelle |
| **Tailscale** | Freemium | ❌ Non (client OSS) | Ultra simple (basé WireGuard), gratuit pour petits usages | SaaS, payant en équipe |
| **Netbird / Headscale** | Gratuit | ✅ Oui | Alternatives open source à Tailscale, self-host | Plus techniques |
| **OpenVPN** | Freemium | ✅ Oui | Éprouvé, partout | Plus lourd que WireGuard |
| **VPN de la box/NAS** | Gratuit* | ❌ Non | Intégré (Synology, box) | Dépend du matériel |

> 🎯 **Pour démarrer** : **Tailscale** (le plus simple pour se lancer) ou **WireGuard**
> (gratuit, open source) quand tu veux maîtriser de bout en bout.

---

## 11. Outils réseau & diagnostic

*(La trousse de dépannage. Voir [cours 11](../cours/11-diagnostic-depannage/).)*

| Outil | 💶 | 🔓 | Rôle |
|---|---|---|---|
| **nmap / Zenmap** | Gratuit | ✅ Oui | Scanner le réseau, découvrir les machines/ports |
| **Angry IP Scanner** | Gratuit | ✅ Oui | Scan réseau simple et rapide |
| **Wireshark** | Gratuit | ✅ Oui | Analyser le trafic en détail (le « microscope » réseau) |
| **Advanced IP Scanner** | Gratuit | ❌ Non | Scan réseau Windows, très simple |
| **MobaXterm** | Freemium | ❌ Non | SSH/RDP/SFTP tout-en-un (Windows) |
| **PuTTY** | Gratuit | ✅ Oui | Client SSH classique |
| **WinSCP** | Gratuit | ✅ Oui | Transfert de fichiers SFTP (Windows) |
| **Termius** | Freemium | ❌ Non | Client SSH moderne multi-plateforme |

> 🎯 **Indispensables gratuits** : **nmap**, **Wireshark**, un **client SSH** (PuTTY/MobaXterm
> sous Windows ; terminal natif sous Linux/Mac).

---

## 12. Microsoft 365 / cloud (gestion MSP)

*(Administrer les tenants clients. Voir [cours 19](../cours/19-microsoft-365/).)*

| Outil | 💶 | 🔓 | Avantages | Inconvénients |
|---|---|---|---|---|
| **Centre d'admin M365** | Inclus | ❌ Non | Gestion native d'un tenant | Un tenant à la fois |
| **Microsoft Partner Center** | Gratuit (programme) | ❌ Non | Gérer plusieurs clients, licences CSP | Nécessite statut partenaire |
| **CIPP** | Gratuit | ✅ Oui | Gestion **multi-tenant** M365 pour MSP, automatisations | Avancé, à héberger/sécuriser |

> 🎯 **Pour démarrer** : le **centre d'admin** classique. Quand tu gères plusieurs tenants,
> regarde le **programme partenaire** Microsoft et **CIPP**.

---

## 13. Déploiement & automatisation

*(Installer/configurer en masse, gagner du temps.)*

| Outil | 💶 | 🔓 | Avantages | Inconvénients |
|---|---|---|---|---|
| **Chocolatey** | Freemium | ✅ Oui | Installer/mettre à jour les logiciels Windows en ligne de commande | Fonctions pro payantes |
| **PDQ Deploy & Inventory** | Freemium | ❌ Non | Déploiement Windows très pratique | Payant pour l'essentiel |
| **Ansible** | Gratuit | ✅ Oui | Automatisation puissante (Linux surtout) | Courbe d'apprentissage |
| **PowerShell / scripts** | Gratuit | ✅ Oui | Natif Windows, incontournable | À apprendre (cf. [admin](../administration/)) |

> 🎯 **Pour démarrer** : **Chocolatey** + **PowerShell** côté Windows ; **Ansible** quand tu
> gères beaucoup de serveurs.

---

## 14. Gestion de l'activité (devis, factures)

*(Pas de l'IT, mais indispensable pour ton entreprise d'infogérance.)*

| Outil | 💶 | 🔓 | Notes |
|---|---|---|---|
| **Dolibarr** | Gratuit | ✅ Oui | ERP/CRM + **facturation** auto-hébergeable, **Factur-X natif** (voir note e-invoicing) |
| **Odoo Community** | Gratuit | ✅ Oui | ERP complet open source (e-invoicing souvent en édition Enterprise) |
| **Invoice Ninja** | Freemium | ✅ Oui | Facturation auto-hébergeable, e-invoicing/Factur-X via module |
| **Facturation FR** (Henrri, Facture.net) | Gratuit/Freemium | ❌ Non | SaaS, simples pour démarrer |
| **Pennylane / QuickBooks / Sellsy** | Payant | ❌ Non | Compta + facturation + lien expert-comptable |
| **Un PSA** (Atera, Autotask…) | Payant | ❌ Non | Facturation **liée aux tickets/contrats** (voir §1 et §4) |

> 🎯 **Pour démarrer (open source)** : **Dolibarr** (que tu utilises déjà) reste le bon
> choix — ERP + facturation, auto-hébergé, tes données chez toi.
> 🧾 **Facture électronique** : conforme avec Dolibarr v19 + module eInvoicing + une
> **Plateforme Agréée** — détails dans la [note de la stack souveraine](#-note--facture-électronique-réforme-fr-2026-2027).
> 💡 Pense aussi à l'**expert-comptable** : incontournable, et source de clients !

---

## 15. Audit & inventaire client (découverte du parc)

*(Pour faire un audit **sérieux** — et pas « à la feuille » — qui scanne le parc
automatiquement et sort un rapport pro. Lié au cours [infogérance 02 — l'audit](../infogerance/02-audit-client.md).)*

### a) Scan réseau rapide (lister les appareils en 2 min, sur place)

| Outil | 💶 | 🔓 | Pour quoi |
|---|---|---|---|
| **Fing** | Freemium | ❌ Non | Appli PC **et mobile** : liste tous les appareils (IP, MAC, fabricant). Rapide, rendu propre → impressionne en clientèle |
| **Advanced IP Scanner** | Gratuit | ❌ Non | Windows, ultra simple, machines + partages |
| **Angry IP Scanner / nmap** | Gratuit | ✅ Oui | Multi-plateforme, scan complet (ports, OS) |

### b) Inventaire détaillé automatique (matériel + logiciels + rapport)

| Outil | 💶 | 🔓 | Avantages | Inconvénients |
|---|---|---|---|---|
| **Lansweeper** | Freemium (gratuit ≤ ~100 appareils) | ❌ Non | Le plus « waouh » : scan sans agent, inventaire complet, **rapports pros** | Payant au-delà du quota |
| **GLPI + agent GLPI** | Gratuit | ✅ Oui | Référence FR : inventaire auto **+ tickets** (deux besoins en un) | À héberger/configurer |
| **OCS Inventory NG** | Gratuit | ✅ Oui | Inventaire auto, se marie avec GLPI | Interface datée |
| **Spiceworks Inventory** | Gratuit | ❌ Non | Scan + rapports, facile, orienté PME | Financé par la pub |

### c) Audit de sécurité (pour un rapport qui pèse)

| Outil | 💶 | 🔓 | Pour quoi |
|---|---|---|---|
| **PingCastle** | Gratuit (éd. communautaire) | ❌ Non | **Audit Active Directory** → rapport **noté** (score de risque). PME avec domaine |
| **Nessus Essentials** | Gratuit (≤ 16 IP) | ❌ Non | Scan de **vulnérabilités** → rapport détaillé |
| **OpenVAS / Greenbone** | Gratuit | ✅ Oui | Alternative open source à Nessus |

> ⚠️ Les seuils gratuits bougent (Lansweeper ~100 appareils, Nessus 16 IP…) → **vérifie la
> limite à jour** avant une grosse mission.

> 🎯 **Pour démarrer** :
> - **TPE (audit ponctuel)** : **Fing**/Advanced IP Scanner (carte du réseau) + **Lansweeper
>   gratuit** ou **GLPI** (inventaire + export PDF) → synthèse dans ton
>   [rapport d'audit](../infogerance/modeles/modele-rapport-audit.md).
> - **PME avec AD** : ajoute **PingCastle** (rapport sécurité noté, très pro).
>
> 💡 **Le combo gagnant** : scan auto (le **technique**) **+** la
> [fiche d'audit](../infogerance/modeles/modele-fiche-audit.md) (l'**organisationnel** : qui
> gère l'IT, sauvegardes testées ?, contrats, mots de passe par défaut…) → **un seul
> rapport**. Les outils ne voient pas l'organisationnel ; la fiche n'est donc pas « pas
> sérieux », c'est la moitié que les scanners ignorent.
>
> 🔁 Une fois le client **sous contrat**, ton **RMM** (§1) refait cet inventaire **en
> continu, automatiquement** — plus besoin de rescanner à la main.

---

## 🎒 La stack recommandée pour démarrer

Si tu veux un **kit de départ cohérent, gratuit ou open source**, voici ce que je
monterais pour tes premiers clients :

| Besoin | Outil de départ | Pourquoi |
|---|---|---|
| Audit / inventaire | **Fing** + **Lansweeper** (ou GLPI) | Scanner le parc + rapport pro (pas « à la feuille ») |
| RMM / supervision | **TacticalRMM** ou **Action1** | Gérer le parc à distance, gratuitement |
| Prise à distance | **RustDesk** | Gratuit, open source |
| Monitoring simple | **Uptime Kuma** | 5 min à installer, suffit pour une TPE |
| Ticketing + inventaire | **GLPI** | Deux besoins en un, gratuit |
| Sauvegarde | **Veeam Community** / **Synology Active Backup** | Référence serveurs / NAS |
| Mots de passe | **Bitwarden / Vaultwarden** | Coffre pro cloisonné par client |
| Documentation | **BookStack** (ou GLPI) | Le classeur de chaque client |
| VPN | **Tailscale** ou **WireGuard** | Accès distant sécurisé |
| Labo / virtu | **VirtualBox** (labo), **Proxmox** (prod) | Apprendre puis produire |
| Diagnostic | **nmap, Wireshark, PuTTY** | La trousse de dépannage |
| Antivirus | **Defender** (→ console centralisée plus tard) | Déjà là, gratuit |
| Facturation | **outil FR gratuit** + expert-comptable | Lancer l'activité proprement |

> 💡 **Conseil anti-dispersion** : ne déploie pas 12 outils d'un coup. Commence par **3** :
> un **RMM** (voir le parc), un **coffre à mots de passe** (sécurité), une **sauvegarde**
> fiable. Le reste s'ajoute quand le besoin arrive.

> ⚠️ **Rappel RGPD** (cours 20) : pour chaque outil qui héberge des données clients,
> vérifie **où** sont les données (UE de préférence) et **qui** y a accès.

---

## 🔗 Liens officiels des outils

> ⚠️ Liens vérifiés à l'ajout ; un site peut changer d'adresse. En cas de lien mort,
> cherche simplement le **nom de l'outil** dans un moteur de recherche. Télécharge
> **toujours depuis le site officiel** (jamais un site tiers qui « reconditionne »).

### 1. Supervision & RMM
- Tactical RMM — https://tacticalrmm.com
- Action1 — https://www.action1.com
- Atera — https://www.atera.com
- NinjaOne — https://www.ninjaone.com
- Pulseway — https://www.pulseway.com
- MeshCentral — https://meshcentral.com

### 2. Prise en main à distance
- RustDesk — https://rustdesk.com
- MeshCentral — https://meshcentral.com
- AnyDesk — https://anydesk.com
- TeamViewer — https://www.teamviewer.com
- Apache Guacamole — https://guacamole.apache.org

### 3. Supervision d'infrastructure (monitoring)
- Uptime Kuma — https://github.com/louislam/uptime-kuma
- Zabbix — https://www.zabbix.com
- Checkmk — https://checkmk.com
- Grafana — https://grafana.com · Prometheus — https://prometheus.io
- PRTG — https://www.paessler.com/prtg
- LibreNMS — https://www.librenms.org · Nagios — https://www.nagios.org

### 4. Ticketing / helpdesk / inventaire
- GLPI — https://glpi-project.org
- Zammad — https://zammad.org
- osTicket — https://osticket.com
- Freshdesk — https://www.freshworks.com/freshdesk
- Autotask (Datto/Kaseya) — https://www.datto.com · ConnectWise — https://www.connectwise.com

### 5. Sauvegarde
- Veeam — https://www.veeam.com
- Synology Active Backup — https://www.synology.com
- UrBackup — https://www.urbackup.org
- Restic — https://restic.net · BorgBackup — https://github.com/borgbackup/borg
- Duplicati — https://www.duplicati.com
- Afi (sauvegarde M365) — https://afi.ai

### 6. Antivirus / EDR
- Microsoft Defender — https://www.microsoft.com/security
- Bitdefender GravityZone — https://www.bitdefender.com/business
- ESET PROTECT — https://www.eset.com
- Malwarebytes — https://www.malwarebytes.com
- Wazuh — https://wazuh.com

### 7. Gestionnaire de mots de passe
- Bitwarden — https://bitwarden.com · Vaultwarden — https://github.com/dani-garcia/vaultwarden
- KeePassXC — https://keepassxc.org
- Keeper — https://www.keepersecurity.com · 1Password — https://1password.com
- Passbolt — https://www.passbolt.com

### 8. Documentation & inventaire IT
- BookStack — https://www.bookstackapp.com
- Wiki.js — https://js.wiki
- NetBox — https://netbox.dev
- Hudu — https://www.hudu.com · IT Glue — https://www.itglue.com

### 9. Virtualisation
- Proxmox VE — https://www.proxmox.com
- VirtualBox — https://www.virtualbox.org
- Hyper-V — https://learn.microsoft.com/windows-server/virtualization/hyper-v/
- VMware (Broadcom) — https://www.vmware.com

### 10. VPN / accès distant sécurisé
- WireGuard — https://www.wireguard.com
- Tailscale — https://tailscale.com
- Netbird — https://netbird.io · Headscale — https://github.com/juanfont/headscale
- OpenVPN — https://openvpn.net

### 11. Outils réseau & diagnostic
- Nmap / Zenmap — https://nmap.org
- Angry IP Scanner — https://angryip.org
- Wireshark — https://www.wireshark.org
- Advanced IP Scanner — https://www.advanced-ip-scanner.com
- MobaXterm — https://mobaxterm.mobatek.net
- PuTTY — https://www.chiark.greenend.org.uk/~sgtatham/putty/
- WinSCP — https://winscp.net · Termius — https://termius.com

### 12. Microsoft 365 / cloud (gestion MSP)
- Centre d'admin M365 — https://admin.microsoft.com
- Microsoft Partner Center — https://partner.microsoft.com
- CIPP — https://cipp.app

### 13. Déploiement & automatisation
- Chocolatey — https://chocolatey.org
- PDQ Deploy & Inventory — https://www.pdq.com
- Ansible — https://www.ansible.com
- PowerShell — https://learn.microsoft.com/powershell

### 14. Gestion de l'activité (devis, factures)
- Henrri — https://www.henrri.com
- Facture.net — https://www.facture.net
- Pennylane — https://www.pennylane.com
- QuickBooks — https://quickbooks.intuit.com
- Sellsy — https://www.sellsy.com

### 15. Audit & inventaire client
- Fing — https://www.fing.com
- Advanced IP Scanner — https://www.advanced-ip-scanner.com
- Angry IP Scanner — https://angryip.org · Nmap — https://nmap.org
- Lansweeper — https://www.lansweeper.com
- GLPI — https://glpi-project.org · OCS Inventory NG — https://ocsinventory-ng.org
- Spiceworks Inventory — https://www.spiceworks.com
- PingCastle — https://www.pingcastle.com
- Nessus Essentials — https://www.tenable.com/products/nessus/nessus-essentials
- OpenVAS / Greenbone — https://www.greenbone.net

### 🔓 Compléments open source (stack souveraine)
- Proxmox Backup Server — https://www.proxmox.com/en/proxmox-backup-server
- Bareos — https://www.bareos.org · Bacula — https://www.bacula.org
- Kopia — https://kopia.io
- ClamAV — https://www.clamav.net
- Docmost — https://docmost.com
- Firezone — https://www.firezone.dev
- OPSI (gestion parc Windows) — https://www.opsi.org
- FOG Project (imaging) — https://fogproject.org
- Remmina (client RDP/VNC/SSH) — https://remmina.org
- Dolibarr — https://www.dolibarr.org · Odoo Community — https://www.odoo.com/page/community
- Invoice Ninja — https://www.invoiceninja.com

---

⬅️ [Retour au sommaire](../README.md) · 🧭 [Parcours](../PARCOURS.md)
