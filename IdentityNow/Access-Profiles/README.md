# 🎯 IdentityNow – Access Profiles

## 🎯 Objective
Explain how Access Profiles are used in IdentityNow to simplify access management by grouping entitlements into business-friendly units.

---

## 🏢 Business Scenario
Applications provide access as:
- Groups (AD)
- Roles (Salesforce)
- Permissions (DB)

These are:
- Technical
- Hard to understand

👉 Business needs:
- Simple access representation

---

## 🧠 IAM Design Approach

IdentityNow uses:

👉 **Access Profiles = Logical grouping of entitlements**

This replaces complex RBAC structures.

---

## 🔑 Key SailPoint Concepts Used

- Access Profiles
- Entitlements
- Identity Profiles
- Provisioning

---

## ⚙️ Access Model Flow

Entitlements  
↓  
Access Profiles  
↓  
Assigned to Identity  
↓  
Provisioning  

---

## ⚙️ Step-by-Step Flow

### 🔹 Step 1: Entitlement Aggregation
- Pull entitlements from sources

---

### 🔹 Step 2: Profile Creation
- Group related entitlements
- Assign business-friendly name

---

### 🔹 Step 3: Assignment
- Assign to identities:
  - Manually
  - Rule-based

---

### 🔹 Step 4: Provisioning
- Access Profile triggers provisioning actions

---

## ⚠️ Common Issues & Troubleshooting

### ❌ Poor Grouping
- Leads to access confusion

---

### ❌ Overlapping Profiles
- Causes duplicate access

---

### ❌ Naming Issues
- Hard for business users to understand

---

## 🎤 Interview Talking Points

👉 If asked: “What are Access Profiles?”

You can say:

“Access Profiles in IdentityNow group entitlements into business-friendly units, simplifying access management compared to traditional roles. They are directly assigned to identities and drive provisioning.”

---

## 🚀 Key Takeaways

- Simplifies RBAC  
- Business-friendly  
- Scalable for cloud IAM  
- Easier governance  

---

## 📌 Notes for Reviewers

- Focuses on simplified access model  
- Designed for SaaS environments  
