# Requirements - BADR Invest

This section defines the functional and non-functional requirements of the BADR Invest brokerage platform.

The system is designed to provide a digital solution for stock trading, portfolio management, and compliance (KYC + bank linking).

---

# 2. Functional Requirements (Besoins Fonctionnels)

The functional requirements define the core features provided to users (Investors) and internal operators.

---

## Investor Functional Requirements

| ID | Actor | Description |
|----|------|-------------|
| BF-01 | Investor | Register on the platform |
| BF-02 | Investor | Authenticate securely (login/logout) |
| BF-03 | Investor | Consult market data and track asset evolution in real time |
| BF-04 | Investor | Place a buy order on available assets |
| BF-05 | Investor | Place a sell order on owned assets |
| BF-06 | Investor | View portfolio (holdings and performance) |
| BF-07 | Investor | Track status of executed orders |
| BF-08 | Investor | View pending orders |
| BF-09 | Investor | View profile information |
| BF-10 | Investor | Update profile information |
| BF-11 | Investor | Delete user account |
| BF-12 | Investor | Logout from the platform |
| BF-13 | Investor | Submit KYC (Know Your Customer) file |
| BF-14 | Investor | Add bank account and link it to the platform |

---

## Internal Operator Functional Requirements

| ID | Actor | Description |
|----|------|-------------|
| BF-15 | Operator | Verify submitted bank account before approval |
| BF-16 | Operator | Process user requests and handle platform operations |

---

# 3. Non-Functional Requirements (Besoins Non Fonctionnels)

Les besoins non fonctionnels décrivent les contraintes de qualité, de performance, de sécurité et de disponibilité du système.

Dans le contexte du secteur bancaire et du courtage (BADR Invest), ces exigences sont critiques pour garantir un service fiable et sécurisé.

---

## Table 2.2 – Besoins Non Fonctionnels

| ID | Catégorie | Description |
|----|----------|-------------|
| BNF-01 | Performance | Le temps de réponse des requêtes standards doit être inférieur à 500 ms afin d’assurer une expérience fluide. |
| BNF-02 | Disponibilité | Le système doit garantir un taux de disponibilité de 99,9% (hors maintenance). |
| BNF-03 | Sécurité | Les données sensibles (utilisateurs, KYC, transactions) doivent être chiffrées et protégées contre tout accès non autorisé. |
| BNF-04 | Fiabilité | Les informations fournies par le système doivent être exactes, cohérentes et vérifiables. |

---

## Explication des exigences

### Performance
Le système doit répondre rapidement aux requêtes utilisateur afin de supporter une utilisation en temps réel (consultation de marché, ordres de trading).

### Disponibilité
La plateforme doit être accessible en permanence, car les marchés financiers fonctionnent en continu et les utilisateurs doivent pouvoir trader à tout moment.

### Sécurité
Étant une plateforme financière, la sécurité est une priorité absolue :
- chiffrement des données sensibles
- protection des comptes utilisateurs
- contrôle d’accès strict basé sur les rôles

### Fiabilité
Les données affichées (prix, ordres, portefeuille) doivent être cohérentes et refléter l’état réel du système sans erreurs ni pertes d’information.

---

## Lien avec le système

Ces exigences influencent directement :
- l’architecture logicielle
- la base de données
- les choix de sécurité
- les performances des opérations de trading

Elles complètent les besoins fonctionnels et garantissent la qualité globale du système BADR Invest.

# 4. Business Rules (Règles Métier)

- A user must complete KYC before executing financial transactions
- A user can only link one bank account at a time
- Orders must be validated before execution
- A sell order can only be placed if the user owns the asset
- All transactions must be recorded in portfolio history

---

# 5. Link with UML Model

The requirements are directly mapped to the UML diagrams:

- BF-01 → Use Case: User Registration
- BF-04 / BF-05 → Sequence Diagrams (Buy / Sell)
- BF-13 → KYC workflow in Use Case Diagram
- BF-14 → Bank linking process
- Business rules → Class diagram constraints (KYC, BankAccount, Order)

---

# Summary

This requirements specification defines the foundation of the BADR Invest system and ensures traceability between:
- Business needs
- System design (UML)
- Implementation logic (OOP + database design)
