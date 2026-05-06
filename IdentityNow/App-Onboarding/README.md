# 🔌 IdentityNow – Application Onboarding (Architect View)

## 🎯 Objective
Provide an architect-level understanding of how applications are onboarded into IdentityNow, including design decisions, integration strategies, and trade-offs in real enterprise environments.

---

## 🏢 Real-World Business Scenario

A large enterprise operates:

- Workday (HR – Source of Truth)
- Active Directory (Authentication)
- Salesforce (CRM)
- ServiceNow (ITSM)
- Multiple SaaS + legacy apps

Challenges:
- Disconnected identity data
- Manual provisioning delays (2–5 days)
- Audit failures due to orphan accounts

👉 Objective:
Design a **scalable, secure, cloud IAM onboarding model**.

---

## 🧠 Architecture Design Approach

### 🔑 Core Principle
**IdentityNow = Aggregation + Correlation + Governance Layer**

---

### 🔹 Source Classification Strategy

| Type | Example | Design Decision |
|------|--------|----------------|
| Authoritative Source | Workday | Drives identity lifecycle |
| Managed Source | AD, Salesforce | Supports provisioning |
| Entitlement Source | DB, SaaS | Access governance only |

👉 WHY:
- Prevents conflicting identity data
- Establishes clear ownership

---

### 🔹 Connector Strategy

| Scenario | Decision |
|---------|---------|
| SaaS apps | Use API-based connectors |
| On-prem systems | Use Virtual Appliance |
| Custom systems | Use REST / Web Services |

👉 Trade-off:
- API connectors = fast, scalable  
- VA = required for legacy, adds infra overhead  

---

## ⚙️ End-to-End Flow (Architect View)

1. **Source Onboarding**
   - Define source type (authoritative vs managed)

2. **Schema Strategy**
   - Standardize attributes across sources
   - Avoid attribute duplication

3. **Aggregation Design**
   - Full aggregation during onboarding
   - Incremental for daily sync

4. **Correlation Logic**
   - Primary key: email or employeeId
   - Fallback logic required

5. **Identity Profile Mapping**
   - Drives lifecycle state
   - Controls identity creation

6. **Access Modeling**
   - Use Access Profiles (not roles)

7. **Provisioning Enablement**
   - Enable only where required
   - Avoid over-provisioning

---

## ⚖️ Key Design Decisions

### 🔹 Decision 1: Single Authoritative Source
👉 WHY:
Avoid identity conflicts

---

### 🔹 Decision 2: Email as Correlation Key
👉 Trade-off:
- Easy → but risky if email changes  
- Employee ID → more stable but not always available  

---

### 🔹 Decision 3: Incremental Aggregation
👉 WHY:
- Performance optimization  
- Reduces API load  

---

### 🔹 Decision 4: Limit Provisioning Scope
👉 WHY:
- Not all apps need provisioning  
- Reduces failure points  

---

## ⚠️ Failure Scenarios & Mitigation

### ❌ Duplicate Identities
- Cause: Poor correlation logic  
- Fix: Use composite keys  

---

### ❌ Aggregation Overload
- Cause: Large datasets  
- Fix: Incremental aggregation  

---

### ❌ API Throttling
- Cause: SaaS rate limits  
- Fix: Stagger schedules  

---

### ❌ Provisioning Failures
- Cause: Endpoint issues  
- Fix: Retry + alerting  

---

## 🎤 Architect-Level Interview Answer

“If I onboard an application in IdentityNow, I first classify it as authoritative or managed. I design schema normalization, define correlation logic using stable identifiers, and implement aggregation with incremental updates. I minimize provisioning scope and ensure access is modeled via access profiles for scalability.”

---

## 🚀 Key Takeaways

- Architecture decisions impact scalability  
- Source classification is critical  
- Correlation logic is high-risk area  
- Over-provisioning must be avoided  

---
