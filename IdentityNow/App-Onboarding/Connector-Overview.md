# 🔗 IdentityNow – Connector Overview

## 🎯 Objective
Explain how SailPoint IdentityNow integrates with external applications using connectors, enabling secure data aggregation and provisioning in a cloud-based IAM environment.

---

## 🏢 Business Scenario
An enterprise uses multiple cloud and on-prem applications:

- Workday (HR system)
- Active Directory (User directory)
- Salesforce (CRM)
- ServiceNow (ITSM)

Each system stores:
- User accounts
- Access permissions

👉 The organization needs:
- Centralized visibility
- Automated access control
- Governance across all systems

IdentityNow connectors enable this integration.

---

## 🧠 IAM Design Approach

IdentityNow follows a **connector-based integration model**:

- Each application is onboarded as a **Source**
- Connectors handle:
  - Authentication
  - Data extraction (aggregation)
  - Provisioning actions

👉 Key principle:  
**Source System ↔ Connector ↔ IdentityNow**

---

## 🔑 Key SailPoint Concepts Used

- Sources (Applications)
- Connectors (SaaS / Virtual Appliance-based)
- Aggregation
- Provisioning Policies
- Identity Profiles
- API Integration
- Authentication (OAuth / Basic / Token-based)

---

## ⚙️ Types of Connectors in IdentityNow

### 🔹 1. SaaS Connectors (Cloud-native)

- Direct integration via APIs
- No infrastructure required

Examples:
- Salesforce
- ServiceNow
- Workday

👉 Best for: Cloud applications

---

### 🔹 2. Virtual Appliance (VA) Connectors

- Required for on-prem systems
- Uses IdentityNow Virtual Appliance

Examples:
- Active Directory
- LDAP
- Databases

👉 VA acts as a secure bridge between cloud and on-prem

---

## ⚙️ Step-by-Step Flow

### 🔹 Step 1: Source Creation

- Add new Source in IdentityNow
- Select connector type

---

### 🔹 Step 2: Authentication Configuration

Depending on connector:
- OAuth
- API Token
- Username/Password

👉 Secure credential storage is critical

---

### 🔹 Step 3: Schema Discovery

- IdentityNow fetches:
  - Account attributes
  - Entitlement attributes

Examples:
- username
- email
- groups

---

### 🔹 Step 4: Aggregation Setup

- Configure aggregation schedule
- Define:
  - Full aggregation
  - Incremental updates

---

### 🔹 Step 5: Identity Correlation

- Accounts mapped to identities using:
  - Email
  - Employee ID

---

### 🔹 Step 6: Provisioning Enablement

- Enable create/update/delete operations
- Configure provisioning policies

---

## 🔄 Data Flow Overview

Source System  
↓  
Connector (API / VA)  
↓  
Aggregation  
↓  
IdentityNow  
↓  
Identity Profile  
↓  
Access Assignment  

---

## ⚠️ Common Issues & Troubleshooting

### ❌ Authentication Failure
- Invalid credentials
- Expired tokens

**Fix:**
- Reconfigure authentication
- Validate API permissions

---

### ❌ Aggregation Failure
- API limits exceeded
- Incorrect endpoint

**Fix:**
- Check logs
- Validate API connectivity

---

### ❌ Missing Attributes
- Schema not mapped correctly

**Fix:**
- Review schema configuration

---

### ❌ Provisioning Not Working
- Provisioning disabled
- Incorrect policy

**Fix:**
- Enable operations
- Validate policy logic

---

## 🎤 Interview Talking Points

👉 If asked: “How do connectors work in IdentityNow?”

You can say:

“IdentityNow uses connectors to integrate applications as sources. SaaS applications are connected via APIs, while on-prem systems use a Virtual Appliance. Connectors handle aggregation and provisioning, enabling IdentityNow to centrally manage accounts and access across systems.”

---

## 🚀 Key Takeaways

- Connectors are the **integration backbone**
- SaaS vs VA connectors is critical distinction
- API-driven architecture
- Enables both aggregation and provisioning
- Core to cloud IAM design

---

## 📌 Notes for Reviewers

- Reflects real-world IdentityNow onboarding approach
- Focuses on architecture + execution
- Simplified but aligned with enterprise implementation
