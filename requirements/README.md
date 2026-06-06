# Requirements - BADR Invest

This section defines the functional and non-functional requirements of the BADR Invest brokerage platform.

The system provides a digital solution for stock trading, portfolio management, and regulatory compliance (KYC + bank account linking).

---

# 1. Functional Requirements

The functional requirements describe the core features provided to users (Investors) and internal operators.

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
| BF-14 | Investor | Add a bank account and link it to the platform |

---

## Internal Operator Functional Requirements

| ID | Actor | Description |
|----|------|-------------|
| BF-15 | Operator | Verify submitted bank account before approval |
| BF-16 | Operator | Process user requests and handle platform operations |

---

# 2. Non-Functional Requirements

Non-functional requirements define system quality constraints such as performance, security, reliability, and availability.

These requirements are critical in the context of a financial brokerage system.

---

## Table 2.2 – Non-Functional Requirements

| ID | Category | Description |
|----|----------|-------------|
| BNF-01 | Performance | Standard requests must respond in less than 500ms to ensure a smooth user experience. |
| BNF-02 | Availability | The system must guarantee 99.9% uptime (excluding maintenance). |
| BNF-03 | Security | Sensitive data (users, KYC documents, transactions) must be encrypted and protected against unauthorized access. |
| BNF-04 | Reliability | All system information must be accurate, consistent, and verifiable. |

---

## Explanation of Requirements

### Performance
The system must respond quickly to user requests, especially for real-time market consultation and trading operations.

### Availability
The platform must remain continuously accessible, as financial markets operate in real time and users may trade at any moment.

### Security
As a financial platform, security is a top priority:
- encryption of sensitive data
- secure authentication
- role-based access control

### Reliability
Market data, orders, and portfolio information must always reflect the real system state without inconsistencies or data loss.

---

# 3. Business Rules

- A user must complete KYC before executing financial transactions
- A user can only link one bank account at a time
- Orders must be validated before execution
- A sell order can only be placed if the user owns the asset
- All transactions must be recorded in portfolio history

---

# 4. Link with UML Model

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
