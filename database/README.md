# Database Design - BADR Invest

This section defines the logical data model of the BADR Invest system.

It translates the system requirements and UML class diagram into a relational database schema suitable for implementation.

The design follows the relational model, ensuring data integrity through primary keys, foreign keys, and normalized structures.

---

# 1. Logical Data Model (Relational Schema)

## USER
- userId (PK)
- nom
- prenom
- motDePasse
- email

---

## INVESTISSEUR
- idInvestisseur (PK)
- userId (FK → USER.userId)
- telephone
- adresse
- statutCompte
- KYCSoumis
- idCompteTitres
- idCompteEspece

---

## OPERATEUR_INTERNE
- idOperateur (PK)
- userId (FK → USER.userId)

---

## DOSSIER_KYC
- idDossierKYC (PK)
- idInvestisseur (FK → INVESTISSEUR.idInvestisseur)
- dateSoumission
- dateValidation
- statutKYC
- pieceIdentite
- obligatoire
- motifRejet
- justificatifDomicile
- photoSelfie

---

## PORTEFEUILLE
- idPosition (PK)
- idOrdreBourse (FK → ORDRE_BOURSE.idOrdreBourse)
- valorisation

---

## MARCHE
- idMarche (PK)
- heureOuverture
- heureFermeture

---

## MARCHE_PRIMAIRE
- idMarche (PK, FK → MARCHE.idMarche)
- quantiteMinimale
- description
- dateDebut
- dateFin

---

## MARCHE_SECONDAIRE
- idMarche (PK, FK → MARCHE.idMarche)
- prixCommission

---

## TITRE
- idTitre (PK)
- idMarche (FK → MARCHE.idMarche)
- idPortefeuille (FK → PORTEFEUILLE.idPosition)
- code
- nom
- coursActuel
- coursEmission
- variation
- volumeEchange
- disponible
- description

---

## ORDRE_BOURSE
- idOrdreBourse (PK)
- idInvestisseur (FK → INVESTISSEUR.idInvestisseur)
- idOperateur (FK → OPERATEUR_INTERNE.idOperateur)
- idTitre (FK → TITRE.idTitre)
- dateCreation
- dateDecision
- quantite
- coursLimite
- statutOrdre
- typeOrdre

---

# 2. Design Interpretation

This database schema is derived directly from:

- Functional requirements (BF-01 to BF-16)
- UML class diagram (User, Investor, Order, Portfolio, KYC)
- Business rules (KYC validation, bank linking, order constraints)

---

# 3. Key Design Principles

## Relational Integrity
All relationships are enforced using primary and foreign keys to maintain consistency.

## Normalization
The schema reduces redundancy by separating:
- User identity (USER)
- Investor-specific data (INVESTISSEUR)
- Administrative roles (OPERATEUR_INTERNE)

## Traceability
Each table maps directly to system behavior:
- ORDRE_BOURSE → trading operations
- DOSSIER_KYC → compliance workflow
- PORTEFEUILLE → investment tracking

---

# 4. Link with System Design

- USER → authentication system
- INVESTISSEUR → main actor in UML use case diagram
- ORDRE_BOURSE → buy/sell sequence diagrams
- DOSSIER_KYC → KYC workflow
- PORTEFEUILLE → portfolio management

---

# Summary

This database design completes the system architecture by providing a structured, relational representation of all core business entities in BADR Invest.
