# 🔄 JML Lifecycle – Execution Flow

## 🎯 Objective
Explain the detailed execution flow of Joiner-Mover-Leaver (JML) lifecycle in SailPoint IdentityIQ, from data ingestion to provisioning and deprovisioning.

---

## 🏢 Business Scenario
An enterprise uses an HR system as the authoritative source to manage employee data.  
IdentityIQ consumes this data and automates access provisioning based on lifecycle events.

---

## 🧠 IAM Design Approach

The lifecycle flow is driven by:

- **Authoritative Source (HR System)**
- **Aggregation Process**
- **Identity Correlation**
- **Lifecycle Event Detection**
- **RBAC (Role-Based Access Control)**
- **Provisioning Engine**

👉 Key idea:  
**Any change in HR data → triggers identity lifecycle event → triggers access change**

---

## 🔑 Key SailPoint Concepts Used

- Aggregation Task
- Identity Cube
- Correlation Rules
- Lifecycle Events (Joiner, Mover, Leaver)
- Role Assignment Rules
- Provisioning Plans
- Workflows
- Task Execution

---

## ⚙️ Step-by-Step Flow

### 🔹 Step 1: Data Ingestion (Aggregation)

1. HR system sends employee data (via file/API)
2. IdentityIQ runs **aggregation task**
3. Data stored in IdentityIQ as accounts

---

### 🔹 Step 2: Identity Correlation

1. IdentityIQ matches accounts to identities
2. Based on:
   - Email
   - Employee ID
3. If no match:
   - New identity is created (Joiner)

---

### 🔹 Step 3: Identity Creation / Update

- Identity Cube is created or updated
- Attributes populated:
  - Department
  - Title
  - Manager
  - Location

---

### 🔹 Step 4: Lifecycle Event Detection

IdentityIQ evaluates changes:

- New identity → **Joiner**
- Attribute change → **Mover**
- Status = terminated → **Leaver**

👉 This is the **decision engine**

---

### 🔹 Step 5: Role Assignment (RBAC)

1. Identity attributes evaluated
2. Roles assigned automatically

Example:
- Department = Finance → Finance Role
- Title = Manager → Manager Role

---

### 🔹 Step 6: Provisioning Plan Creation

IdentityIQ generates a **provisioning plan**:
- What access to add/remove
- Which applications to target

---

### 🔹 Step 7: Provisioning Execution

Provisioning engine:
- Sends requests to target systems
- Creates / updates / disables accounts

Examples:
- Create AD account
- Assign email access
- Remove ERP access

---

### 🔹 Step 8: Workflow Execution

Workflows handle:
- Approvals (if required)
- Notifications
- Error handling

---

### 🔹 Step 9: Post-Provisioning Validation

- Verify account creation
- Check entitlement assignment
- Log success/failure

---

## 🔄 Lifecycle Flow by Event Type

### 🟢 Joiner Flow

HR → Aggregation → Identity Created  
→ Role Assigned → Provisioning Plan  
→ Accounts Created → Access Ready  

---

### 🔄 Mover Flow

HR Update → Aggregation → Identity Updated  
→ Old Role Removed → New Role Assigned  
→ Access Updated Across Systems  

---

### 🔴 Leaver Flow

Termination → Aggregation → Identity Disabled  
→ Roles Removed → Provisioning Plan  
→ Accounts Disabled/Deleted  

---

## ⚠️ Common Issues & Troubleshooting

### ❌ Aggregation Not Triggering Lifecycle
- Task not scheduled
- HR feed not updated

---

### ❌ Incorrect Lifecycle Detection
- Attribute mapping issue
- Status field not configured

---

### ❌ Roles Not Updating (Mover)
- Role rules not dynamic
- Caching issue in IdentityIQ

---

### ❌ Provisioning Failures
- Target system not reachable
- Connector misconfiguration

---

## 🎤 Interview Talking Points

👉 If asked: “Explain lifecycle flow in IdentityIQ”

You can say:

“The lifecycle flow starts with aggregation from an authoritative HR source, followed by identity correlation and creation. IdentityIQ then detects lifecycle events such as joiner, mover, or leaver based on attribute changes. Roles are assigned using RBAC, provisioning plans are generated, and access is provisioned or revoked across target systems through connectors and workflows.”

---

## 🚀 Key Takeaways

- Lifecycle flow is **event-driven**
- HR system is the **source of truth**
- RBAC simplifies access assignment
- Provisioning ensures automation
- Entire process is **auditable and scalable**

---

## 📌 Notes for Reviewers

- This flow represents a real-world IdentityIQ implementation
- Simplified for clarity but aligned with enterprise practices
- Focused on execution logic rather than configuration details


