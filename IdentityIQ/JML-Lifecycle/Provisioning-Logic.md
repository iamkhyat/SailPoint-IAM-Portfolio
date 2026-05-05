# ⚙️ JML Lifecycle – Provisioning Logic

## 🎯 Objective
Explain how SailPoint IdentityIQ determines, generates, and executes provisioning actions (create, modify, disable accounts) based on identity lifecycle events.

---

## 🏢 Business Scenario
An organization wants to automate access across multiple systems (AD, ERP, Email, etc.).

Whenever a user:
- Joins
- Changes role
- Leaves

👉 IdentityIQ should automatically:
- Grant correct access
- Update access
- Remove access

Without manual intervention.

---

## 🧠 IAM Design Approach

Provisioning logic is driven by:

- Identity attributes (department, title, status)
- Role-Based Access Control (RBAC)
- Provisioning policies
- Lifecycle events (JML)

👉 Key idea:  
**Identity change → Role change → Provisioning action**

---

## 🔑 Key SailPoint Concepts Used

- Provisioning Plan
- Provisioning Policy
- Role-Based Access Control (RBAC)
- Entitlements
- Application Connectors
- Workflows (Approval / Execution)
- Identity Cube
- Account Operations (Create / Modify / Disable)

---

## ⚙️ Step-by-Step Flow

### 🔹 Step 1: Identity Evaluation

- IdentityIQ evaluates identity attributes:
  - Department
  - Title
  - Status
- Determines applicable roles

---

### 🔹 Step 2: Role Assignment Change

- Roles are:
  - Assigned (Joiner)
  - Updated (Mover)
  - Removed (Leaver)

👉 Roles act as the **bridge between identity and access**

---

### 🔹 Step 3: Entitlement Calculation

- Each role contains entitlements
- IdentityIQ determines:
  - What access to ADD
  - What access to REMOVE

---

### 🔹 Step 4: Provisioning Plan Generation

IdentityIQ creates a **Provisioning Plan**:

Includes:
- Target application
- Account operation:
  - Create
  - Modify
  - Disable/Delete
- Entitlements to add/remove

---

### 🔹 Step 5: Policy & Approval Check

- If approval required:
  - Workflow triggered
  - Manager/owner approves

- If auto-approved:
  - Move directly to execution

---

### 🔹 Step 6: Provisioning Execution

Provisioning engine:
- Sends request via connector
- Executes action on target system

Examples:
- Create AD account
- Add user to group
- Remove ERP access
- Disable account

---

### 🔹 Step 7: Result Handling

- Success → Logged in system
- Failure → Error captured
- Retry or manual intervention triggered

---

## 🔄 Provisioning Logic by Lifecycle Event

### 🟢 Joiner (New User)

- Identity created
- Roles assigned
- Provisioning plan:
  - Create accounts
  - Assign entitlements

👉 Outcome: User gets Day 1 access

---

### 🔄 Mover (Role Change)

- Identity updated
- Role recalculated
- Provisioning plan:
  - Remove old access
  - Add new access

👉 Outcome: Access aligned with new role

---

### 🔴 Leaver (Termination)

- Identity disabled
- Roles removed
- Provisioning plan:
  - Disable or delete accounts
  - Remove all entitlements

👉 Outcome: No active access (critical for security 🚨)

---

## ⚠️ Common Issues & Troubleshooting

### ❌ Provisioning Plan Not Generated
- Role assignment missing
- No entitlement mapping

---

### ❌ Incorrect Access Provisioned
- Role design issue
- Entitlement mapping incorrect

---

### ❌ Provisioning Failure
- Connector issue
- Target system unreachable
- Invalid credentials

---

### ❌ Access Not Removed (High Risk 🚨)
- Leaver event not triggered
- Disable logic not configured

---

## 🎤 Interview Talking Points

👉 If asked: “How does provisioning work in IdentityIQ?”

You can say:

“Provisioning in IdentityIQ is driven by role-based access. When identity attributes change, roles are assigned or removed, which triggers a provisioning plan. This plan defines what accounts and entitlements need to be created, modified, or removed. The provisioning engine then executes these actions on target systems through connectors, optionally going through approval workflows.”

---

## 🚀 Key Takeaways

- Provisioning is **role-driven**
- Provisioning plan is the **core execution unit**
- Connectors enable system integration
- Automation reduces manual effort
- Critical for security and compliance

---

## 📌 Notes for Reviewers

- This represents real-world provisioning logic in IdentityIQ
- Focus is on decision-making and execution flow
- Simplified for clarity but aligned with enterprise implementation
