# Requirements Document Template

> **Purpose:** Describe the intent of this document and how it supports development planning and stakeholder alignment.

---

## Document Control

| Version | Date       | Author    | Change Summary                     |
| ------- | ---------- | --------- | ---------------------------------- |
| 0.1     | YYYY-MM-DD | Your Name | Draft template creation            |
| 0.2     | YYYY-MM-DD | Your Name | Updated based on stakeholder input |

---

## 1. Overview

**1.1 Project Name:**

**1.2 Project Description:**
*Briefly summarize the product/service and its key goals.*

**1.3 Scope:**

* What is in scope
* What is out of scope

---

## 2. Stakeholders & Roles

| Stakeholder      | Role / Responsibility                       |
| ---------------- | ------------------------------------------- |
| Dietician        | Uploads plans; reviews compliance           |
| Cook             | Receives & executes prep instructions       |
| End User         | Views & checks off routines                 |
| Admin / DevOps   | System setup, monitoring, access management |
| External Systems | Webhooks, Databases                         |

---

## 3. Functional Requirements

### 3.1 Authentication & Authorization

| ID   | Requirement                                                        | Priority | Notes            |
| ---- | ------------------------------------------------------------------ | -------- | ---------------- |
| FR-1 | Support Dietician, Cook, and End User roles with role-based access | High     | JWT-based tokens |
| FR-2 | Two-factor auth for Admin/DevOps                                   | Medium   |                  |

### 3.2 Dietician Portal

| ID   | Requirement                                      | Priority | Acceptance Criteria                 |
| ---- | ------------------------------------------------ | -------- | ----------------------------------- |
| FR-3 | List of users and their active plans             | High     | Table view with filter & search     |
| FR-4 | Upload & initiate monthly plan for selected user | High     | PDF/CSV upload flow with validation |

### 3.3 Cook Interface

| ID   | Requirement                          | Priority | Acceptance Criteria                     |
| ---- | ------------------------------------ | -------- | --------------------------------------- |
| FR-5 | Morning prep instructions generation | High     | Instructions available by 7:30 AM daily |
| FR-6 | Evening prep instructions generation | High     | Instructions available by 7:30 PM daily |

### 3.4 End User App

| ID   | Requirement                                               | Priority | Acceptance Criteria                |
| ---- | --------------------------------------------------------- | -------- | ---------------------------------- |
| FR-7 | Daily routine view with time-based checklist toggles      | High     | Checklist persists state           |
| FR-8 | Monthly plan overview with mindmap/calendar visualization | Medium   | Clickable nodes expand details     |
| FR-9 | Consistency report screen with dynamic scoring            | Medium   | Score ≥80%; view by day/week/month |

### 3.5 Custom Planner (Normal Users)

| ID    | Requirement                                | Priority | Acceptance Criteria           |
| ----- | ------------------------------------------ | -------- | ----------------------------- |
| FR-10 | Custom routine builder integrates with DSL | Low      | Save & export custom routines |

---

## 4. UI/Screen Mockups & Flows

1. **Login Screen**

   * Fields: username, password, role selector
2. **Dietician Dashboard**

   * Sidebar: user list
   * Main: plan details; upload widget
3. **Cook Instructions**

   * Tabs: Morning / Evening
   * Preview & send platform notifications
4. **End User Daily View**

   * Timeline-based checklist
5. **Monthly Overview**

   * Visual grid/mindmap; click to expand day details
6. **Consistency Report**

   * Graphs for daily/weekly/monthly scores; filters

*(Attach wireframes or link to designs.)*

---

## 5. Non-Functional Requirements

| ID    | Requirement                                  | Priority | Notes                      |
| ----- | -------------------------------------------- | -------- | -------------------------- |
| NFR-1 | System uptime ≥99.9%                         | High     | HA clusters, health checks |
| NFR-2 | API response ≤200ms (p95)                    | High     | Load testing required      |
| NFR-3 | Secure communication (TLS, OWASP compliance) | High     | Penetration testing        |
| NFR-4 | Scalability to 10,000 concurrent users       | Medium   | Horizontal scaling plan    |

---

## 6. Assumptions & Constraints

* Platform handles all messaging and notifications
* PDF/CSV formats adhere to pre-defined schema
* Webhook sources follow agreed event schema

---

## 7. Glossary

| Term  | Definition                                       |
| ----- | ------------------------------------------------ |
| DSL   | Domain-specific language for plan representation |
| Agent | Autonomous unit performing a specific task       |

---

## 8. Version History

See Section 0 (Document Control) above.

*End of Template*
