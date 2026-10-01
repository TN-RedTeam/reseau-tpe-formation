# 📖 Glossaire

Tous les termes techniques de la formation, chacun expliqué **en une phrase
simple**. Un mot t'échappe ? Il est là. (Classé par ordre alphabétique.)

---

**Adresse IP** — L'adresse postale d'un appareil sur le réseau (ex : `192.168.1.25`).

**Adresse MAC** — Le numéro de série unique « gravé » dans une carte réseau (comme
le numéro de châssis d'une voiture).

**Antivirus** — Un logiciel qui détecte et bloque les programmes malveillants.

**Bande passante** — La « largeur du tuyau » : la quantité de données qui peut
passer par seconde.

**Box** — Le boîtier de ton fournisseur d'accès qui fait office de routeur (le
« gardien » du réseau).

**Câble Ethernet** — Le câble réseau qu'on branche pour relier un appareil à la box
(la « porte », rapide et fiable).

**Chiffrement** — Transformer des données en charabia illisible pour tout le monde
sauf celui qui a la clé.

**Cloud** — Des serveurs sur internet où l'on stocke des données « ailleurs » (ex :
pour une sauvegarde hors site).

**Client** — L'appareil qui demande un service (ton PC qui demande une page web).

**DHCP** — Le « gardien de parking » qui donne automatiquement une adresse IP à
chaque appareil qui se connecte.

**DNS** — L'annuaire qui traduit un nom de site (google.com) en adresse IP.

**Ethernet** — La technologie des réseaux locaux filaires (le câble réseau).

**Pare-feu (firewall)** — Le « vigile » qui filtre ce qui entre et sort du réseau.

**FAI (Fournisseur d'Accès à Internet)** — L'entreprise qui te fournit internet
(Orange, Free, SFR…).

**Gateway (passerelle)** — La porte de sortie vers internet : l'adresse de la box
(souvent `192.168.1.1`).

**GNS3** — Un simulateur de réseau avancé (alternative à Packet Tracer).

**IP (voir Adresse IP)** — Le système d'adressage des appareils sur un réseau.

**IPv4** — La version courante des adresses IP : 4 nombres séparés par des points.

**IPv6** — La nouvelle version des adresses IP, plus longue, créée car les IPv4
viennent à manquer.

**LAN (réseau local)** — Ton réseau « à la maison » ou « au bureau » (ton immeuble).

**Masque de sous-réseau** — Le nombre (ex : `255.255.255.0`) qui indique où s'arrête
le « quartier » dans une adresse IP.

**NAS** — Une armoire à fichiers du réseau, toujours allumée (*Network Attached
Storage*).

**Packet Tracer** — Le simulateur gratuit de Cisco pour construire des réseaux
virtuels et s'entraîner.

**Pare-feu (voir Firewall)** — Le vigile du réseau.

**Passerelle (voir Gateway)** — La porte vers internet.

**Phishing (hameçonnage)** — Un email/message piégé qui essaie de te faire cliquer
ou donner un mot de passe.

**Ping** — Un petit « coucou, tu es là ? » envoyé à un appareil pour voir s'il
répond.

**Port (réseau)** — Un « guichet » numéroté sur un appareil, dédié à un type de
service (ex : le web passe souvent par le port 80 ou 443).

**Port (physique)** — La prise où l'on branche un câble réseau.

**Raspberry Pi** — Un mini-ordinateur bon marché (~50 €), pratique pour s'entraîner.

**RAID** — Une technique qui fait travailler plusieurs disques ensemble ; le RAID
miroir écrit tout en double pour survivre à la panne d'un disque.

**RAID ≠ sauvegarde** — Rappel essentiel : le RAID protège d'une panne disque, pas
d'un virus, d'un vol ou d'une erreur.

**Redirection de port** — Ouvrir une « porte » sur la box pour qu'un service interne
soit joignable depuis internet (à éviter, préférer un VPN).

**Réseau** — Plusieurs appareils reliés pour échanger des informations.

**Réseau invité** — Un Wi-Fi séparé pour les visiteurs, qui n'accède pas à tes
fichiers.

**Routeur** — L'appareil qui relie ton réseau à internet et oriente les informations
(le « gardien »). En TPE, c'est la box.

**Sauvegarde** — Une copie séparée de tes données, rangée ailleurs (le « 3-2-1 »).

**Serveur** — Un appareil qui rend un service aux autres (fichiers, web, DHCP…).

**Serveur de fichiers** — Un serveur dont le rôle est de stocker et partager des
fichiers (souvent un NAS).

**SSID** — Le nom d'un réseau Wi-Fi, celui qui s'affiche dans la liste.

**Switch** — Une « multiprise réseau » qui relie des appareils entre eux (n'ouvre
pas sur internet, contrairement au routeur).

**Tailscale** — Un outil moderne et simple pour monter un VPN.

**TrueNAS / OpenMediaVault** — Des logiciels gratuits pour transformer un vieux PC en
NAS.

**VPN** — Un tunnel privé et chiffré qui relie un appareil distant à ton réseau (pour
le télétravail notamment).

**Wi-Fi** — La connexion réseau sans fil (la « fenêtre », pratique mais plus
variable que le câble).

**WireGuard** — Une technologie de VPN moderne, rapide et sécurisée.

**WPA2 / WPA3** — Les bons niveaux de chiffrement du Wi-Fi (à utiliser ; éviter le
vieux WEP).

**2FA (double authentification)** — Une 2ᵉ preuve d'identité (code par SMS/appli) en
plus du mot de passe ; le réflexe sécurité le plus efficace.

**2,4 GHz / 5 GHz** — Les deux « routes » du Wi-Fi : 2,4 GHz va plus loin mais plus
lentement, 5 GHz va plus vite mais moins loin.

---

## 🏢 Termes PME, infogérance & cloud

**Active Directory (AD)** — La « réception centrale » d'une PME : gère de façon centralisée
les comptes utilisateurs et les ordinateurs d'un domaine.

**Agent (RMM)** — Petit programme installé sur une machine pour la superviser et la gérer à
distance.

**Audit IT** — Le « bilan de santé » complet de l'informatique d'un client avant de
proposer un contrat.

**Contrôleur de domaine** — Le serveur qui fait tourner Active Directory.

**DPO** — Délégué à la protection des données : responsable de la conformité RGPD dans une
organisation.

**Entra ID (ex-Azure AD)** — La version cloud d'Active Directory, liée à Microsoft 365.

**GPO** — *Group Policy Object* : une règle appliquée automatiquement à tout un parc depuis
Active Directory.

**Helpdesk** — Centre d'assistance qui centralise les demandes des utilisateurs sous forme
de tickets.

**Hyperviseur** — Le logiciel qui fait tourner plusieurs machines virtuelles sur un même
serveur physique (ex : Proxmox, Hyper-V, VMware).

**IaaS** — *Infrastructure as a Service* : louer des machines/serveurs dans le cloud.

**Infogérance** — Prendre en charge, dans la durée, la gestion informatique d'une entreprise
(souvent via un contrat mensuel).

**MFA / 2FA** — Authentification à plusieurs facteurs : une 2ᵉ preuve d'identité en plus du
mot de passe.

**Microsoft 365** — La suite bureautique + messagerie + collaboration de Microsoft, en
abonnement cloud.

**OneDrive** — Le stockage en ligne **personnel** d'un utilisateur M365.

**On-premise (local)** — Des services hébergés sur le matériel du client, par opposition au
cloud.

**Onboarding** — La prise en main d'un nouveau client (récupérer les accès, monter le
dossier, déployer les outils).

**Onduleur (UPS)** — Batterie de secours qui permet un arrêt propre des équipements lors
d'une coupure de courant.

**PaaS** — *Platform as a Service* : louer une plateforme pour développer/héberger des
applications.

**PoE** — *Power over Ethernet* : alimentation électrique transportée par le câble réseau.

**PRA / PCA** — Plan de Reprise / de Continuité d'Activité : comment repartir après un
sinistre informatique.

**QoS** — *Quality of Service* : priorité donnée à un trafic (ex : la voix) sur le réseau.

**Reporting** — Le compte-rendu périodique remis au client (ce qui a été fait, l'état du
parc).

**RGPD** — Règlement européen sur la protection des données personnelles.

**RMM** — *Remote Monitoring and Management* : l'outil central de l'infogéreur pour
superviser et gérer les machines à distance.

**SaaS** — *Software as a Service* : un logiciel prêt à l'emploi, utilisé via internet (ex :
Microsoft 365, Gmail).

**SharePoint** — Les espaces de fichiers **partagés** d'équipe dans Microsoft 365.

**SLA** — *Service Level Agreement* : les délais garantis par contrat (prise en compte,
rétablissement).

**Softphone** — Une application qui transforme un PC/smartphone en téléphone (VoIP).

**Switch managé** — Un switch configurable (VLAN, QoS, supervision), par opposition au switch
« non managé » basique.

**Ticket** — Une demande/incident client tracé dans le helpdesk (numéro, priorité, statut).

**Trunk SIP** — La « ligne » téléphonique VoIP fournie par un opérateur.

**Virtualisation** — Faire tourner plusieurs serveurs virtuels (VM) sur une seule machine
physique.

**VLAN** — Réseau local virtuel : découpe un réseau physique en plusieurs réseaux isolés.

**VM (machine virtuelle)** — Un ordinateur « dans » un ordinateur, créé par virtualisation.

**VoIP** — *Voice over IP* : la téléphonie qui passe par le réseau internet.

---

> 💡 Un terme manque ? Note-le, et on l'ajoutera. Un glossaire, ça vit !

⬅️ [Retour au sommaire](README.md)
