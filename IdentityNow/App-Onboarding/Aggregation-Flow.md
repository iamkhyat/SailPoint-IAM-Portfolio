# 🔄 IdentityNow – Aggregation Flow

## 🎯 Objective
Explain how IdentityNow aggregates accounts and entitlements from connected sources and links them to identities for access governance.

---

## 🏢 Business Scenario
An enterprise uses multiple systems (Workday, AD, Salesforce) where:
- User accounts are created independently
- Access is distributed

👉 IdentityNow must:
- Collect all account data
- Maintain a unified identity view

---

## 🧠 IAM Design Approach

IdentityNow uses **aggregation jobs** to pull data from sources:

👉 Key idea:  
**Source Data → Aggregation → Identity Correlation → Governance**

---

## 🔑 Key SailPoint Concepts Used

- Sources
- Aggregation (Full / Incremental)
- Identity Profiles
- Correlation Rules
- Account Attributes
- Entitlements

---

## ⚙️ Step-by-Step Flow

### 🔹 Step 1: Source Configuration
- Source (e.g., AD, Workday) is configured
- Connector authentication established

---

### 🔹 Step 2: Aggregation Trigger
- Scheduled or manual aggregation
- Full or incremental

---

### 🔹 Step 3: Data Retrieval
Connector fetches:
- Accounts
- Attributes (email, username)
- Entitlements (groups, roles)

---

### 🔹 Step 4: Data Storage
- Data stored in IdentityNow
- Accounts exist independently before correlation

---

### 🔹 Step 5: Identity Correlation
- Accounts linked to identities via:
  - Email
  - Employee ID

---

### 🔹 Step 6: Identity Profile Assignment
- Identity profiles define:
  - Attribute mapping
  - Lifecycle state

---

## 🔄 Aggregation Types

### 🟢 Full Aggregation
- Pulls all data
- Used during onboarding

### 🔄 Incremental Aggregation
- Pulls only changes
- Used for daily sync

---

## ⚠️ Common Issues & Troubleshooting

### ❌ Missing Accounts
- Aggregation not executed
- Filter misconfigured

---

### ❌ Duplicate Identities
- Correlation rule issue

---

### ❌ Stale Data
- Incremental sync not configured

---

## 🎤 Interview Talking Points

“Aggregation in IdentityNow pulls accounts and entitlements from sources, then correlates them to identities using identity profiles. This enables centralized governance of access across systems.”

---

## 🚀 Key Takeaways

- Aggregation is the **data foundation**
- Correlation is critical
- Identity profiles drive identity creation
- Supports real-time governance
