# 🔐 IdentityNow – Access Model

## 🎯 Objective
Explain how IdentityNow models and manages access using Access Profiles and Entitlements.

---

## 🏢 Business Scenario
Users require access across multiple applications:
- Finance tools
- HR systems
- CRM

Access must be:
- Understandable
- Governable

---

## 🧠 IAM Design Approach

IdentityNow replaces complex RBAC with:

👉 **Access Profiles = Grouped Entitlements**

---

## 🔑 Key SailPoint Concepts Used

- Entitlements
- Access Profiles
- Identity Profiles
- Lifecycle States

---

## ⚙️ Step-by-Step Flow

### 🔹 Step 1: Entitlement Discovery
- Aggregated from source
- Examples:
  - AD Groups
  - Salesforce Roles

---

### 🔹 Step 2: Access Profile Creation
- Group related entitlements
- Define business-friendly name

---

### 🔹 Step 3: Assignment
- Assigned to identities manually or via rules

---

### 🔹 Step 4: Provisioning
- Access Profile triggers provisioning actions

---

## 🔄 Access Flow

Entitlements  
↓  
Access Profiles  
↓  
Assigned to Identity  
↓  
Provisioning  

---

## ⚠️ Common Issues

- Overlapping profiles  
- Poor grouping  
- Lack of naming standards  

---

## 🎤 Interview Talking Points

“IdentityNow uses Access Profiles instead of roles. These group entitlements into business-friendly units that can be assigned to users and provisioned automatically.”

---

## 🚀 Key Takeaways

- Simplifies RBAC  
- Business-friendly access  
- Easier governance  
