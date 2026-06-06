#  System Architecture

## 1 Overview

The BADR Invest platform follows a 3-layer architecture designed for a mobile-first financial simulation system:

- Presentation Layer (UI)
- Business Layer (Application Logic)
- Data Layer (Local Storage)

This architecture ensures separation of concerns, maintainability, and simulation of real-world brokerage systems.

---

## 2 Presentation Layer (UI - IHM)

**Components:**
- Android Activities / Screens
- Graphical User Interfaces

**Role:**
- Provide an intuitive and ergonomic user interface
- Allow users to interact with the system (orders, portfolio, market data)
- Display real-time simulation results (market, orders, account status)

---

## 3 Business Layer (Application Logic)

**Components:**
- Controllers
- Service classes
- Validation modules

**Role:**
- Implement core business logic of the system
- Handle:
  - KYC simulation workflow
  - Portfolio computation
  - Order processing (buy/sell)
  - Business rule enforcement

This layer represents the actual financial system logic of the platform.

---

## 4 Data Layer (Local Storage)

**Components:**
- SQLite Embedded Database (Android Local Storage)

**Role:**
- Store all system data locally on the device
- Manage persistent relational data (users, orders, portfolios, KYC, etc.)

---

## 5 Design Decision: Why Local Storage (SQLite)

The system uses **local storage (SQLite)** instead of a remote backend for the following reasons:

### 1. Security & Confidentiality Constraints
The platform is a **simulation of a real brokerage system** and does not connect to external banking or central financial infrastructure (such as BADR central systems).

Direct integration with real banking systems would require:
- High-level security certifications
- Regulatory approval
- Real financial data handling compliance

---

### 2. Educational / Simulation Purpose

This project is designed as a **functional simulation of a real brokerage workflow**, not a production financial system.

Therefore:
- All operations are simulated locally
- Data is persisted locally to emulate real system behavior
- No external APIs or banking connections are used

---

### 3. Offline-First Architecture Choice

The system follows an **offline-first design approach**, where:
- The local database is the primary source of truth
- All operations (orders, KYC, portfolio updates) are executed locally
- No dependency on network connectivity

This design ensures:
- Fast response time
- Full system autonomy
- Controlled and safe environment for simulation

---

## 6 Global Architecture Summary

The system is structured as:

---
User Interface (Android UI)
→
Business Logic Layer (Services + Controllers)
→
Local Database (SQLite)

---

This simple layered architecture ensures:
- Clear separation of concerns
- Easy maintainability
- Realistic simulation of financial workflows
- Independence from external systems
