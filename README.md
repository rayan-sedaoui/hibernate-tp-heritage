Ce TP montre comment enregistrer des classes Java liées par héritage (parents et enfants) 
dans une base de données avec Hibernate.


https://github.com/user-attachments/assets/39fe830d-7e35-42fa-a9e6-526400ee91ec

Diagramme de classe de ce Tp :

```mermaid
classDiagram
    direction BT

    %% 1. Stratégie SINGLE_TABLE
    class Vehicule {
        +Long id
        +String marque
        +String modele
        +double prix
    }
    class Voiture {
        +int nombrePortes
        +boolean climatisation
        +String typeCarburant
    }
    class Moto {
        +int cylindree
        +String typeTransmission
    }
    Voiture --|> Vehicule : Hérite
    Moto --|> Vehicule : Hérite

    %% 2. Stratégie JOINED
    class Employe {
        +Long id
        +String nom
        +String prenom
        +String email
    }
    class Developpeur {
        +String langage
        +String specialite
        +int anneeExperience
    }
    class Manager {
        +String service
        +int nombreSubordonnes
        +double bonus
    }
    Developpeur --|> Employe : Hérite
    Manager --|> Employe : Hérite

    %% 3. Stratégie TABLE_PER_CLASS
    class Produit {
        <<abstract>>
        +Long id
        +String nom
        +double prix
    }
    class Livre {
        +String auteur
        +String isbn
        +int nombrePages
    }
    class Electronique {
        +String marque
        +String modele
        +int garantieMois
    }
    Livre --|> Produit : Hérite
    Electronique --|> Produit : Hérite




    
