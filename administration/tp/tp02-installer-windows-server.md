# TP02 — Installer Windows Server + contrôleur de domaine

🎯 **Objectif** : installer Windows Server dans une VM et le **promouvoir contrôleur de
domaine** (créer ton propre domaine AD). 🕐 Durée : ~60 min · Prérequis : TP01, admin 03/04.

> 🏆 C'est un gros TP, le plus formateur. Fais-le en 2 fois si besoin (snapshot entre les
> deux !).

---

## 1. Récupérer Windows Server (gratuit pour tester)

Microsoft propose une **version d'évaluation gratuite (180 jours)** de Windows Server :
cherche **« Windows Server evaluation ISO »** sur le site de Microsoft (Evaluation Center)
et télécharge l'**ISO**.

## 2. Créer la VM

- Dans VirtualBox : **Nouvelle** → nom `SRV01`.
- Type : Microsoft Windows, Version : Windows Server (64-bit).
- RAM : **4096 Mo** (4 Go) · Disque : **40 Go**.
- Réseau : rattache la VM au **réseau du labo** (voir [TP01, section 5](tp01-labo-virtuel.md#5-le-réseau-du-labo)).
  Pour démarrer, l'**option simple « Réseau NAT » (`LAB-NAT`)** suffit ; tu passeras aux
  **2 cartes** le jour de l'exercice DHCP. Dans tous les cas, on donne à Windows Server une
  **IP fixe** (étape 4) : un contrôleur de domaine doit avoir une adresse stable.
- Branche l'ISO (Stockage) et **démarre**.

## 3. Installer le système

1. Choisis la langue → **Installer maintenant**.
2. **Important** : choisis l'édition **« Desktop Experience »** (avec interface graphique),
   pas « Core ».
3. Type : **Personnalisé** → installe sur le disque de 40 Go.
4. Patiente, la VM redémarre, puis **définis le mot de passe Administrateur** (fort !).

> 🔑 Astuce VirtualBox : pour envoyer Ctrl+Alt+Suppr à la VM, menu **Entrée → Insérer
> Ctrl-Alt-Suppr**.

## 4. Réglages de base du serveur

Dans le **Gestionnaire de serveur** (s'ouvre tout seul) :

1. **Renomme** le serveur en `SRV01` (Serveur local → Nom de l'ordinateur) → redémarre.
2. Donne-lui une **IP fixe** — un contrôleur de domaine ne doit pas changer d'adresse.
   Dans *Serveur local → la carte réseau* :
   - Adresse IP : **`10.10.10.10`** · Masque : `255.255.255.0`
   - **Passerelle** : `10.10.10.1` *(option simple Réseau NAT)* — ou **vide** *(option
     avancée : la passerelle est sur l'autre carte, la NAT)*.
   - **DNS préféré** : **`127.0.0.1`** (lui-même — il deviendra serveur DNS à l'étape 6).
   > 💡 Astuce : ajoute **`1.1.1.1`** en **DNS secondaire** le temps des mises à jour (pour
   > résoudre les noms internet), tu l'enlèveras une fois les redirecteurs DNS configurés.
   > En **option avancée (2 cartes)**, l'autre carte (NAT) reste en **automatique** et fournit
   > internet.

## 5. Ajouter le rôle Active Directory

1. Gestionnaire de serveur → **Gérer → Ajouter des rôles et fonctionnalités**.
2. Coche **« Services AD DS » (Active Directory Domain Services)** → Suivant → Installer.

## 6. Promouvoir en contrôleur de domaine ⭐

1. Après l'install, clique sur la **bannière d'avertissement** (drapeau en haut) →
   **« Promouvoir ce serveur en contrôleur de domaine »**.
2. **Ajouter une nouvelle forêt** → nom de domaine racine : **`labo.local`**.
3. Définis un **mot de passe DSRM** (mode restauration) et note-le.
4. Laisse les options par défaut (le rôle **DNS** s'ajoute automatiquement — cf. admin 08).
5. **Installer** → le serveur **redémarre**.

```mermaid
flowchart LR
    A[Windows Server installé] --> B[IP fixe + renommé SRV01]
    B --> C[Rôle AD DS ajouté]
    C --> D[Promu contrôleur de domaine<br/>labo.local]
    D --> E[✅ Domaine opérationnel + DNS]
```

## 7. Vérifier

Après redémarrage, connecte-toi en `LABO\Administrateur`. Ouvre le Gestionnaire de serveur :
tu vois maintenant **AD DS** et **DNS**. Ouvre **Outils → Utilisateurs et ordinateurs Active
Directory** : ton domaine `labo.local` est là. 🎉

---

## ✅ Réussite

Tu as **ton propre domaine Active Directory** qui tourne. C'est l'équivalent de ce qu'on
installe au cœur d'une PME.

## 🧠 Snapshot !

Fais un **instantané** nommé « Domaine prêt ». Tu repartiras de là aux TP suivants sans tout
réinstaller.

---

⬅️ [TP01](tp01-labo-virtuel.md) · ➡️ [TP03 — AD : utilisateurs, groupes, GPO](tp03-ad-utilisateurs-gpo.md)
