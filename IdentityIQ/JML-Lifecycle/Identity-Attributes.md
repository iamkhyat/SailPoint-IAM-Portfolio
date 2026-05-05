# 🧾 JML Lifecycle – Identity Attributes

## 🎯 Objective
Explain how identity attributes are used in SailPoint IdentityIQ to drive lifecycle events, role assignment, and provisioning decisions.

---

## 🏢 Business Scenario
An enterprise receives employee data from an HR system containing user details such as:
- Name
- Email
- Department
- Job Title
- Employment Status

These attributes are used to:
- Create identities
- Assign roles
- Trigger lifecycle events (Joiner, Mover, Leaver)

---

## 🧠 IAM Design Approach

Identity attributes act as the **decision-making inputs** for IAM.

Key principle:
👉 **Attributes → Role Assignment → Access Provisioning**

Design strategy:
- Use HR system as authoritative source
- Map attributes correctly into IdentityIQ
- Use attributes for dynamic role assignment
- Ensure data consistency and uniqueness

---

## 🔑 Key SailPoint Concepts Used

- Identity Cube
- Authoritative Source
- Identity Attributes
- Correlation Rules
- Role Assignment Rules
- Lifecycle Events (JML)
- Attribute Mapping

---

## ⚙️ Step-by-Step Flow

### 🔹 Step 1: Attribute Ingestion

- HR system provides user data
- IdentityIQ performs aggregation
- Attributes imported into IdentityIQ

---

### 🔹 Step 2: Identity Creation

- Identity is created using key attributes:
  - Employee ID (unique identifier)
  - Email
  - Name

---

### 🔹 Step 3: Attribute Mapping

- Attributes mapped from source to IdentityIQ fields

Examples:
- `dept` → Department
- `title` → Job Title
- `status` → Employment Status

---

### 🔹 Step 4: Identity Update

- Any change in HR data updates identity attributes
- Triggers lifecycle evaluation

---

### 🔹 Step 5: Role Assignment Based on Attributes

- IdentityIQ evaluates attributes

Examples:
- Department = Finance → Assign Finance Role
- Title = Manager → Assign Manager Role
- Location = US → Assign regional access

---

### 🔹 Step 6: Lifecycle Event Trigger

- Status = Active → Joiner
- Attribute change → Mover
- Status = Terminated → Leaver

---

## 📊 Common Identity Attributes (Examples)

| Attribute        | Purpose                          |
|-----------------|----------------------------------|
| Employee ID     | Unique identity identifier       |
| Email           | Correlation & communication      |
| Department      | Role assignment                  |
| Job Title       | Role refinement                  |
| Manager         | Approval workflows               |
| Location        | Regional access control          |
| Status          | Lifecycle event trigger          |

---

## ⚠️ Common Issues & Troubleshooting

### ❌ Missing Attributes
- Incomplete HR data
- Incorrect schema mapping

---

### ❌ Incorrect Role Assignment
- Wrong attribute values
- Role rules not aligned with attributes

---

### ❌ Correlation Failures
- Duplicate or missing unique identifiers
- Email mismatch

---

### ❌ Lifecycle Not Triggered
- Status attribute not mapped correctly
- Incorrect lifecycle configuration

---

## 🎤 Interview Talking Points

👉 If asked: “What role do identity attributes play in IAM?”

You can say:

“Identity attributes are the foundation of IAM decision-making. In IdentityIQ, attributes like department, title, and status are used to determine role assignment and trigger lifecycle events. These roles then drive provisioning actions, ensuring users get the right access automatically.”

---

## 🚀 Key Takeaways

- Identity attributes drive **all IAM decisions**
- Accurate mapping is critical
- Attributes enable dynamic RBAC
- Poor data quality leads to security risks
- Core to lifecycle automation

---

## 📌 Notes for Reviewers

- This module highlights the importance of data in IAM
- Focus is on decision logic, not just configuration
- Reflects real-world enterprise implementation practices
