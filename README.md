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
✔️ **Gestion des chambres** (ajout, suppression, modification et consultation des disponibilités).  
✔️ **Gestion des réservations** (ajout, suppression, modification et consultation de l'historique).  
✔️ **Sécurité des données** et gestion des rôles (droits d'accès différents pour administrateurs et clients).  

###  b) Acteurs et fonctionnalités attendues  

#### 🛠 **Administrateur**  
- ➕ Ajouter, supprimer et consulter la liste des **clients**.  
- 🏨 Ajouter, supprimer , modifier et consulter la liste des **chambres**.  
- 📅 Gérer les **réservations** (ajouter, supprimer, modifier et  consulter toutes les réservations).  

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

### c) Diagramme de séquence détaillé - Authentification
Le diagramme suivant représente en détail le processus d’authentification d’un utilisateur (client par défaut). Il montre les interactions entre l’utilisateur et le système, ainsi que la validation des informations d’identification avant d’accorder l’accès aux fonctionnalités correspondantes.

![Diagramme de séquence système](Diagrammes/diag_sequence_authentification.png)

## 4️⃣ Priorités des cas d’utilisation

## Sprint 1 : Cas d’utilisation de haute priorité

Les fonctionnalités suivantes sont considérées comme essentielles et seront développées en priorité :

#### 🛑 1. Annuler une réservation

Ce cas d’utilisation permet à un utilisateur (Admin) d’annuler une réservation existante sous certaines conditions (délai d’annulation autorisé, paiement effectué, etc.).

#### 🏨 2. Réservation d’une chambre

Ce cas d’utilisation permet à un utilisateur (Admin) de réserver une chambre en fonction des disponibilités et de ses préférences.

 
# 5️⃣Spécifications et Tests de Validation  

## 📌 Cas d’utilisation : Annuler une réservation  

### ✅ Préconditions  
- **∧ ID de la réservation bien formé** (¬ null ∧ ¬ vide)  
- **∧ La réservation existe** dans le système  
- **∧ La réservation est toujours active** (non expirée)  
- **∧ L'administrateur est bien authentifié**  

### 📖 Scénario principal  
1. **L'administrateur accède au menu de gestion des réservations**  
   - Il interagit avec l'interface utilisateur.  
2. **Il sélectionne l'option "Annuler une réservation"**  
3. **Le système demande l’ID de la réservation**  
4. **L'administrateur saisit l’ID de la réservation**  
5. **Le système vérifie l'existence et la validité de la réservation**  
   - Vérifie si la réservation est active et non annulée.  
6. **Si la réservation est valide, le système :**  
   - Marque la chambre comme **disponible**.  
   - Supprime la réservation de la **base de données**.  
   - Met à jour le **nombre de réservations du client**.  
   - Affiche un message ✅ **"Réservation annulée avec succès !"**  
7. **Si la réservation n'existe pas ou est invalide, le système :**  
   - Affiche un message ❌ **"Aucune réservation correspondante trouvée !"**  

### 🎯 Postconditions  
- ✅ **∧ La réservation est supprimée** du système.  
- ✅ **∧ La chambre est marquée disponible**.  
- ✅ **∧ Le nombre total de réservations du client est mis à jour**.  

### 📊 Table de décision des tests  

| **Précondition**                                        | 1  | 2  | 3  | 4  | 5  | 6  | 7  |
|---------------------------------------------------------|----|----|----|----|----|----|----|
| **ID réservation bien formé (¬ null ∧ ¬ vide)**        | ❌  | ✅  | ✅  | ✅  |  ✅  |
| **Réservation existe dans le système**                 | -  | ❌  | ✅  | ✅  |  ✅  |
| **Réservation toujours active (non expirée)**          | -  | -  | ❌  | ✅  |  ✅  |
| **Administrateur authentifié**                         | -  | -  | -  | ❌   | ✅  |
| **Postcondition**                                      |    |    |    |      |    |
| **Réservation supprimée du système**                   | ❌  | ❌  | ❌  | ❌  |  ✅  |
| **Chambre marquée comme disponible**                   | -  | -  | -  | -  | ✅  |
| **Nombre total de réservations mis à jour**            | ❌  | ❌  | ❌  | ❌   | ✅  |
| **Nombre de jeux de tests**                            | 2  | 1  | 1  | 1  | 1  | 

---

## 📌 Cas d’utilisation : Réservation d’une chambre  

### ✅ Préconditions  
- **∧ ID du client bien formé** (¬ null ∧ ¬ vide)  
- **∧ ID de la chambre bien formé** (¬ null ∧ ¬ vide)  
- **∧ Date de début et date de fin bien formées** (¬ null ∧ date_fin > date_debut)  
- **∧ Le client existe** dans le système  
- **∧ Le client n’a pas d’impayés ou restrictions**  
- **∧ La chambre existe et est disponible**  

### 📖 Scénario principal  
1. **L'administrateur accède au menu de gestion des réservations**  
2. **Il sélectionne "Ajouter une réservation"**  
3. **Le système demande les informations nécessaires :**  
   - ID du client, ID de la chambre  
   - Nombre d'adultes et d'enfants  
   - Type de séjour (Demi-pension / Pension complète)  
   - Date de début et de fin  
4. **L'administrateur saisit les informations**  
5. **Le système vérifie les données**  
   - **La date de fin > date de début**  
   - **Le client existe et n’a pas d'impayés**  
   - **La chambre est disponible**  
6. **Si tout est valide, le système :**  
   - ✅ Calcule le **montant total**  
   - ✅ Génère un **ID unique**  
   - ✅ Enregistre la **réservation**  
   - ✅ Marque la **chambre comme occupée**  
   - ✅ Affiche **"Réservation ajoutée avec succès !"**  
7. **Si une condition échoue :**  
   - ❌ **Message d'erreur correspondant**  

### 🎯 Postconditions  
- ✅ **∧ La réservation est enregistrée**  
- ✅ **∧ La chambre est marquée comme occupée**  
- ✅ **∧ Le nombre total de réservations du client est mis à jour**  

### 📊 Table de décision des tests  

| **Précondition**                                       | 1  | 2  | 3  | 4  | 5  | 6  | 7  | 8  |
|--------------------------------------------------------|----|----|----|----|----|----|----|----|
| **ID du client bien formé (¬ null ∧ ¬ vide)**         | ❌  | ✅  | ✅  | ✅  | ✅  | ✅  | ✅  | ✅  |
| **ID de la chambre bien formé (¬ null ∧ ¬ vide)**     | -  | ❌  | ✅  | ✅  | ✅  | ✅  | ✅  | ✅  |
| **Date de début et de fin bien formées**              | -  | -  | ❌  | ✅  | ✅  | ✅  | ✅  | ✅  |
| **Client existe dans le système**                     | -  | -  | -  | ❌  | ✅  | ✅  | ✅  | ✅  |
| **Chambre existe et disponible**                      | -  | -  | -  | -  | ❌  | ✅  | ✅  | ✅  |
| **Postcondition**                                     |    |    |    |    |    |    |    |    |
| **Réservation ajoutée**                               | ❌  | ❌  | ❌  | ❌  | ❌  | ❌  | ✅  | ✅  |
| **Chambre marquée comme occupée**                     | -  | -  | -  | -  | -  | -  | ❌  | ✅  |
| **Nombre total de réservations mis à jour**           | ❌  | ❌  | ❌  | ❌  | ❌  | ❌  | ❌  | ✅  |
| **Nombre de jeux de tests**                           | 2  | 2  | 2  | 1  | 1  | 1  | 1  | 1  |


## 6️⃣ Conception Préliminaire – Diagramme de Classes

### 🧠 Étape 1 : Identification des classes métier

À partir du document de spécifications et des cas d’utilisation , nous avons identifié les **classes métier** suivantes :

- **Utilisateur** : classe générale représentant une personne ayant un accès au système (héritée par Admin et Client).
- **Client** : utilisateur pouvant effectuer, consulter ou annuler des réservations.
- **Admin** : utilisateur responsable de la gestion des clients, chambres et réservations.
- **Chambre** : unité disponible à la réservation, caractérisée par son type, son état et son prix.
- **Reservation** : entité représentant l’action de réserver une chambre pour une période donnée.

---

### 🧱 Étape 2 : Diagramme de classes – version préliminaire

📎 Diagramme de classes :

![Diagramme de Classes](Diagrammes/diag_classe_préliminaire.png)



##  Patron de Conception Utilisé – MVC

Nous avons adopté le patron de conception **Modèle-Vue-Contrôleur (MVC)** pour organiser notre application.  
Ce modèle permet de séparer la logique métier (modèle), la gestion des interactions (contrôleur) et l'affichage (vue).

📎 Diagramme de conception MVC utilisé dans notre projet :

![Diagramme MVC](Diagrammes/patron_conception.png)



## 7️⃣ Conception Dynamique – Diagrammes de Séquence

### 🛠️ Cas d'utilisation 1 : Ajouter une réservation 

Diagramme de séquence représentant le **scénario principal** de l’ajout d’une réservation par l’administrateur.

📎 Diagramme :

![Diagramme de séquence ajout_reservation](Diagrammes/diag_sequence_ajout_dynamique.png)



---

### 🛠️ Cas d'utilisation 2 : Annuler une réservation 

Diagramme de séquence représentant le **scénario principal** de l’annulation d’une réservation par l’administrateur.

📎 Diagramme :

![Diagramme de séquence annuler_reservation](Diagrammes/diag_sequence_annuler_dynamique.png)



# 🧩 Étape 8 : Conception détaillée

## 8.1 Raffinement du diagramme de classe préliminaire

Le diagramme de classes initial a été raffiné pour mieux représenter les détails nécessaires à l’implémentation du système de réservation. 

![Diagramme de Classes](Diagrammes/raf1_diag_classe_preliminaire.png)

## 8.2 Diagramme d'états-transitions de l’objet `Chambre`

Le diagramme d’états-transitions suivant décrit le comportement dynamique de l’objet `Chambre`, en fonction des opérations exécutées sur le système.

### 🔄 États de la chambre
![Diagramme_etat_transition_chambre](Diagrammes/diag_etat_transition_chambre.png)

## 8.3 Raffinement des diagrammes

## Raffinement du diagramme de classe

![Diagramme_claase-raffiné](Diagrammes/raf2_diag_classe.png)

## Traduction du diagramme de séquence "Ajouter Réservation" en algorithme

Procédure ajouterReservation(idClient, idChambre, dateDebut, dateFin, nbAdultes, nbEnfants, typeSejour)

    // 1. Vérification des dates
    Si dateFin ≤ dateDebut Alors
        afficher("Date de fin invalide")
        Retourner
    Fin Si

    // 2. Vérification de l'existence du client
    client ← rechercherClientParId(idClient)
    Si client = null Alors
        afficher("Client invalide")
        Retourner
    Fin Si

    // 3. Vérification de la disponibilité de la chambre
    chambre ← rechercherChambreParId(idChambre)
    Si chambre = null OU chambre.etat = "occupée" Alors
        afficher("Chambre indisponible")
        Retourner
    Fin Si

    // 4. Calcul du montant
    montant ← calculerMontant(chambre, typeSejour, dateDebut, dateFin, nbAdultes, nbEnfants)

    // 5. Génération d’un identifiant unique
    idReservation ← genererIdReservation()

    // 6. Création et enregistrement de la réservation
    reservation ← nouvelle Réservation(
        idReservation, dateDebut, dateFin, montant,
        typeSejour, nbAdultes, nbEnfants, client, chambre
    )

    enregistrerReservation(reservation)

    // 7. Mise à jour de l'état de la chambre
    chambre.etat ← "occupée"
    mettreAJourChambre(chambre)

    // 8. Confirmation à l’utilisateur
    afficher("Réservation ajoutée avec succès")

Fin Procédure

## Traduction du diagramme de séquence "Annuler Réservation" en algorithme

Procédure annulerReservation(idReservation)

    // 1. Vérification de l'existence de la réservation
    reservation ← rechercherReservationParId(idReservation)
    Si reservation = null Alors
        afficher("Réservation non trouvée")
        Retourner
    Fin Si

    // 2. Vérification de l’état de la réservation
    Si reservation.estExpirée = vrai Alors
        afficher("Réservation déjà expirée")
        Retourner
    Fin Si

    // 3. Suppression de la réservation
    supprimerReservation(reservation)

    // 4. Mise à jour de l’état de la chambre associée
    chambre ← reservation.chambre
    chambre.etat ← "libre"
    mettreAJourChambre(chambre)

    // 5. Confirmation à l’administrateur
    afficher("Réservation annulée avec succès")

Fin Procédure

## Traduction du diagramme Etat Transition de l'objet "chambre" en algorithme

Procédure gererEtatChambre(etatActuel, action)

    Selon (etatActuel)

        Cas "EnConstruction":
            Si action = "finirConstruction" Alors
                etatActuel ← "Consultable"
            Fin Si

        Cas "Consultable":
            Si action = "rendreReservable" Alors
                etatActuel ← "Reservable"
            Sinon Si action = "detruire" Alors
                etatActuel ← "EnDestruction"
            Fin Si

        Cas "Reservable":
            Si action = "réserver" Alors
                etatActuel ← "Réservé"
            Sinon Si action = "rendreNonReservable" Alors
                etatActuel ← "Consultable"
            Sinon Si action = "detruire" Alors
                etatActuel ← "EnDestruction"
            Fin Si

        Cas "Réservé":
            Si action = "libérer" Alors
                etatActuel ← "Reservable"
            Fin Si

        Cas "EnDestruction":
            etatActuel ← "Supprimée"  // état terminal

    Fin Selon

Fin Procédure














