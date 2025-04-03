# GithubAGL
#  Application de Réservations d'Hôtel  

 Date de soumission : 07-04-2025  
 Auteurs : Ilef Marouani - Linda Hajjeji - Chayma kouki - Molka Mansouri 

---

## 1️⃣ Introduction au projet  
L'objectif de ce projet est de développer une application permettant la gestion des **réservations d'hôtel**.  
Cette application vise à **simplifier la gestion des chambres, des clients et des réservations** en offrant une plateforme **intuitive et efficace**.  

---

## 2️⃣ Spécification du projet  

###  a) Notions de base et contraintes  
✔️ **Authentification des utilisateurs** (administrateurs et clients).  
✔️ **Interface utilisateur intuitive** avec menu interactif.  
✔️ **Gestion des clients** (ajout, suppression, consultation).  
✔️ **Gestion des chambres** (ajout, suppression, consultation des disponibilités).  
✔️ **Gestion des réservations** (ajout, suppression, consultation de l'historique).  
✔️ **Sécurité des données** et gestion des rôles (droits d'accès différents pour administrateurs et clients).  

###  b) Acteurs et fonctionnalités attendues  

#### 🛠 **Administrateur**  
- ➕ Ajouter, supprimer et consulter la liste des **clients**.  
- 🏨 Ajouter, supprimer et consulter la liste des **chambres**.  
- 📅 Gérer les **réservations** (ajouter, supprimer, consulter toutes les réservations).  

#### 🏷 **Client**  
- 🛏 Réserver une **chambre**.  
- 📜 Consulter ses **réservations**.  
- ❌ Annuler une **réservation**.  

#### 🔐 **Système**  
- 🔑 **Authentifier les utilisateurs**.  
- 🔒 **Assurer l'intégrité et la sécurité des données**.  

## 3️⃣ Diagrammes UML

### a) Diagramme de cas d'utilisation
Voici le diagramme représentant les cas d'utilisation principaux de l'application.

![Diagramme Cas d'Utilisation](Diagrammes/diag_cas_utilisation.png)

### b) Raffinement du diagramme de cas d'utilisation
Le diagramme suivant reprèsente le raffinement des cas d'utilisation de l'admin .

![Diagramme de Cas d'utilisation](Diagrammes/raffinement_cas_utilisation.png)

### c) Diagramme de classes
Le diagramme suivant illustre la structure des classes principales du système.

![Diagramme de Classe](Diagrammes/diag_classe.png)

### d) Diagramme de séquence système
Le diagramme suivant illustre les interactions principales entre les acteurs et le système lors des différents processus de gestion des réservations d’hôtel.

![Diagramme de séquence système](Diagrammes/diag_sequence_systeme.png)

### e) Diagramme de séquence détaillé - Authentification
Le diagramme suivant représente en détail le processus d’authentification d’un utilisateur (client par défaut). Il montre les interactions entre l’utilisateur et le système, ainsi que la validation des informations d’identification avant d’accorder l’accès aux fonctionnalités correspondantes.

![Diagramme de séquence système](Diagrammes/diag_sequence_authentification.png)

## 4️⃣ Priorités des cas d’utilisation

## Sprint 1 : Cas d’utilisation de haute priorité

Les fonctionnalités suivantes sont considérées comme essentielles et seront développées en priorité :

#### 🛑 1. Annuler une réservation

Ce cas d’utilisation permet à un client d’annuler une réservation existante sous certaines conditions (délai d’annulation autorisé, paiement effectué, etc.).

## 🔹 Diagramme de Séquence Détaillé – Annulation d’une Réservation
Le diagramme suivant illustre les interactions nécessaires pour que l'admin annule une réservation.
![Diagramme de séquence annuler_reservation](Diagrammes/diag_sequence_annuler_reservation.png)

## 🔹 Diagramme d’Activité – Annulation d’une Réservation
Le diagramme ci-dessous représente le flux des actions pour traiter une annulation de réservation.
![Diagramme  d'acrtivite annuler_reservation](Diagrammes/diag_activite_annuler_reservation.png)

#### 🏨 2. Réservation d’une chambre

Ce cas d’utilisation permet à un utilisateur (Admin) de réserver une chambre en fonction des disponibilités et de ses préférences.

 ## 🔹 Diagramme de Séquence Détaillé – Réservation d’une Chambre
Ce diagramme montre les étapes d’interaction entre l'Admin et le système pour effectuer une réservation.
![Diagramme de séquence ajout_reservation](Diagrammes/diag_sequence_ajout_reservation.png)

## 🔹 Diagramme d’Activité – Réservation d’une Chambre
Le diagramme d’activité suivant décrit le processus permettant à l'Admin de réserver une chambre.
![Diagramme d'acrtivite ajout_reservation](Diagrammes/diag_activite_ajout_reservation.png)







