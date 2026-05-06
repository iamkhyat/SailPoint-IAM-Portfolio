# 🎯 Access Profiles (Architect View)

## 🎯 Objective
Explain how to design scalable and maintainable access models in IdentityNow using Access Profiles, including real-world trade-offs and governance implications.

---

## 🏢 Real-World Business Scenario

Enterprise has:
- 5000+ entitlements
- 200+ applications

Problem:
- Users receive inconsistent access
- Role explosion in legacy IAM

👉 Goal:
Simplify access model for cloud IAM

---

## 🧠 Architecture Design Approach

### 🔑 Principle
**Access Profiles = Simplified RBAC Layer**

---

## ⚙️ Design Strategy

### 🔹 Entitlement Grouping

Group based on:
- Job function
- Application usage
- Least privilege

---

### 🔹 Naming Convention

Example:
APP_SALESFORCE_READ_ONLY

👉 WHY:
Improves audit readability

---

### 🔹 Assignment Strategy

| Method | Use Case |
|-------|--------|
| Manual | Exceptions |
| Rule-based | Standard roles |

---

## ⚖️ Key Design Decisions

### 🔹 Avoid Role Explosion
👉 Decision:
Keep profiles broad but controlled

---

### 🔹 Granularity Balance

| Too Broad | Too Granular |
|----------|-------------|
| Security risk | Complexity |

👉 Architect choice: Balanced grouping

---

## ⚠️ Failure Scenarios

### ❌ Overlapping Profiles
- Leads to duplicate access  

---

### ❌ Poor Naming
- Confuses auditors  

---

## 🎤 Architect-Level Interview Answer

“I design access profiles by grouping entitlements based on job function and application usage. I avoid role explosion by maintaining a balance between granularity and simplicity, ensuring profiles are scalable and auditable.”

---

## 🚀 Key Takeaways

- Access model defines system usability  
- Simplicity > complexity in cloud IAM  
- Naming standards are critical  

---
