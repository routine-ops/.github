# Requirements Document

> **Purpose:** Capture and align all product requirements for Routine-Ops, ensuring clear planning and smooth collaboration between Dieticians, Cooks, End Users, and Dev teams.

---

## Document Control

| Version | Date       | Author             | Change Summary                                         |
| ------- | ---------- | ------------------ | ------------------------------------------------------ |
| 0.1     | 2025-08-02 | Satya Vishal Thota | Draft template creation                                |
| 0.2     | 2025-08-03 | Satya Vishal Thota | Added End-User, Shopping List & Chatbot FR             |
| 0.3     | 2025-08-03 | Satya Vishal Thota | Dietician dashboard access feature added & sections reordered |
| 0.4     | 2025-08-03 | Satya Vishal Thota | UI/Screen Mockups flow reordered to prioritize dashboards |

---

## 1. Overview

**1.1 Project Name:** Routine-Ops  
**1.2 Project Description:** A modular, agent-driven platform that plans, orchestrates, and tracks daily routines—from meal prep and supplements to workouts—via an intelligent Planning Engine, robust Backend, and interactive UI.  
**1.3 Scope:**

- **Planning Engine**  
  - Ingest Dietician-provided nutrition plans and output a strict DSL representation.  
  - Generate weekly/monthly routine templates for normal users based on chatbot input, also rendered in the same DSL.  
  - A strictly-defined DSL will standardize both flows.  
- **Backend Services**  
  - User authentication & authorization (JWT, role-based access).  
  - Serve DSL-generated plan data to the UI.  
  - Persist users’ daily event checklist entries.  
  - Calculate and update consistency scores in real time.  
  - Expose endpoints for dashboards, analytics, shopping-list, and chatbot interactions.  
- **UI Frontend**  
  - Tailored screens for Dieticians, Cooks, and End Users.  
  - Real-time daily checklist interface.  
  - Consistency dashboard, shopping lists, and chatbot plan builder.  

---

## 2. Stakeholders & Roles

| Stakeholder      | Role / Responsibility                       |
| ---------------- | ------------------------------------------- |
| Dietician        | Uploads plans; reviews compliance; monitors progress |
| Cook             | Receives & executes prep instructions       |
| End User         | Views & checks off routines; generates lists|
| Admin / DevOps   | System setup, monitoring, access management |
| External Systems | Webhooks, Databases, OAuth Providers        |

---

## 3. Functional Requirements

### 3.1 Authentication & Authorization

| ID    | Requirement                                                        | Priority | Notes            |
| ----- | ------------------------------------------------------------------ | -------- | ---------------- |
| FR-1  | Support Dietician, Cook, and End-User roles with role-based access | High     | JWT-based tokens |
| FR-2  | OAuth login via Google and Apple IDs                               | Medium   | Use secure SDKs  |
| FR-3  | Two-factor auth for Admin/DevOps                                   | Low      | Optional         |

### 3.2 End User App

| ID    | Requirement                                               | Priority | Acceptance Criteria                          |
| ----- | --------------------------------------------------------- | -------- | --------------------------------------------- |
| FR-10 | Daily routine view with time-based checklist toggles      | High     | Checklist persists state                      |
| FR-11 | Add/remove custom activities per day                      | High     | User-added items editable; predefined locked  |
| FR-12 | Activate reminders for individual or all activities       | Medium   | Local notifications scheduled correctly       |
| FR-13 | Monthly plan overview with interactive visualizer         | Medium   | Clickable nodes expand details inline         |
| FR-14 | Consistency report screen with dynamic scoring            | Medium   | Score and streaks computed per requirements   |

### 3.3 Shopping List Generator

| ID     | Requirement                                              | Priority | Acceptance Criteria                                                |
| ------ | -------------------------------------------------------- | -------- | ------------------------------------------------------------------- |
| FR-17  | Daily shopping list                                      | High     | Lists ingredients for selected day; dynamic day swap works          |
| FR-18  | Weekly shopping list                                     | Medium   | Aggregates quantities over 7 days                                  |
| FR-19  | Monthly shopping list                                    | Low      | Aggregates quantities for calendar month; export/share functionality|

### 3.4 Cook Interface

| ID    | Requirement                          | Priority | Acceptance Criteria                     |
| ----- | ------------------------------------ | -------- | --------------------------------------- |
| FR-7  | Morning prep instructions generation | High     | Available by 07:30 daily                |
| FR-8  | Evening prep instructions generation | High     | Available by 19:30 daily                |
| FR-9  | Map Cooks → End-Users (1:N)          | High     | Cook sees only assigned End-Users       |

### 3.5 Dietician Portal

| ID    | Requirement                                              | Priority | Acceptance Criteria                                       |
| ----- | -------------------------------------------------------- | -------- | ---------------------------------------------------------- |
| FR-4  | List of users and their active plans                     | High     | Table view with filter & search                            |
| FR-5  | Upload & initiate monthly plan for selected user         | High     | PDF/CSV upload flow with validation                        |
| FR-6  | Map Dieticians → End-Users (1:N)                         | High     | Assign-user UI; mapping stored                             |
| FR-7  | Access End-User dashboards & swap between user contexts  | Medium   | Dietician can view any End-User’s dashboard; user switcher |

---

## 4. UI/Screen Mockups & Flows

1. **Login Screen**  
   - Role selector, Google & Apple ID buttons  
2. **Monthly Overview**  
   - Node-based calendar; expand/collapse day details  
3. **Consistency Report**  
   - Score, streak cards, heatmap calendar, analytics charts  
4. **End User Daily View**  
   - Timeline-based checklist with add/remove controls  
5. **Shopping List**  
   - Daily/Weekly/Monthly tabs; export/share controls  
6. **Cook Instructions**  
   - Tabs: Morning / Evening prep; send notifications  
7. **Dietician Dashboard**  
   - Sidebar: End-User list; Main: plan upload & user-switcher & dashboards  
8. **Chatbot Planner**  
   - Chat UI; step-by-step prompts; draft plan preview  

*(Attach wireframes or link to designs.)*

---

## 5. Non-Functional Requirements

| ID     | Requirement                                  | Priority | Notes                      |
| ------ | -------------------------------------------- | -------- | -------------------------- |
| NFR-1  | System uptime ≥99.9%                         | High     | HA clusters, health checks |
| NFR-2  | API response ≤200 ms (p95)                   | High     | Load testing required      |
| NFR-3  | Secure communication (TLS, OWASP compliance) | High     | Penetration testing        |
| NFR-4  | Scalability to 10,000 concurrent users       | Medium   | Horizontal scaling plan    |
| NFR-5  | Offline support for daily checklist          | Low      | Sync queue when online     |

---

## 6. Assumptions & Constraints

- Platform handles all messaging and notifications.  
- PDF/CSV formats adhere to pre-defined schema.  
- Webhook sources follow agreed event schema.  
- Reminders use device/local notification APIs.  

---

## 7. Glossary

| Term               | Definition                                           |
| ------------------ | ---------------------------------------------------- |
| DSL                | Domain-specific language for plan representation     |
| Agent              | Autonomous unit performing a specific task           |
| Consistency Score  | % of completed predefined tasks per day              |
| Heatmap Calendar   | Color-coded calendar view of daily completion rates  |
| Chatbot Planner    | AI interface for building/customizing routines       |
