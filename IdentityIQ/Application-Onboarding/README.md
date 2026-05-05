# 🔌 IdentityIQ Application Onboarding

## 🎯 Objective
Demonstrate how enterprise applications are onboarded into SailPoint IdentityIQ to enable centralized access management, provisioning, and governance.

---

## 🏢 Business Scenario
An organization has multiple applications (AD, ERP, SaaS, DB) where:
- Access is managed manually
- No centralized visibility exists
- Compliance risks are high

👉 Goal: Integrate applications into IdentityIQ for automated governance.

---

## 🧠 IAM Design Approach

Application onboarding follows a structured process:

1. Connect application using connector
2. Define schema (accounts + entitlements)
3. Aggregate data into IdentityIQ
4. Correlate accounts to identities
5. Model access using roles (RBAC)
6. Enable provisioning and access requests
7. Govern via certifications

---

## 🔑 Key SailPoint Concepts Used

- Application Definition
- Connectors (JDBC / REST / LDAP)
- Schema (Accounts & Entitlements)
- Aggregation
- Correlation
- RBAC
- Provisioning Policies

---

## ⚙️ Step-by-Step Flow

1. Gather application requirements  
2. Configure connector  
3. Define account & entitlement schema  
4. Run aggregation  
5. Perform identity correlation  
6. Map entitlements to roles  
7. Configure provisioning  
8. Enable access requests  

---

## 📊 Architecture Flow Diagram

![Application Onboarding Flow](../../Diagrams/IdentityIQ-App-Onboarding.png)

---

## 🧾 Diagram Explanation

1. Requirement Gathering  
2. Application Configuration  
3. Aggregation  
4. Correlation  
5. Entitlement Modeling  
6. Role Creation  
7. Provisioning Setup  
8. Access Request Enablement  
9. JML Integration  
10. Certification & Governance  

---

## ⚠️ Common Issues & Troubleshooting

- Aggregation failure → Connector issue  
- Correlation issue → Attribute mismatch  
- Provisioning failure → Policy/config error  

---

## 🎤 Interview Talking Points

“Application onboarding in IdentityIQ involves integrating a target system using connectors, defining schema, aggregating accounts and entitlements, correlating identities, and enabling provisioning and access governance.”

---
