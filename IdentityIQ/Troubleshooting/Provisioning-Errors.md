# ⚙️ Provisioning Errors

## 🎯 Objective
Explain common provisioning failures and how to resolve them.

---

## 🏢 Business Scenario
Provisioning is responsible for:
- Creating accounts  
- Updating access  
- Removing access  

Failures impact security and user productivity.

---

## 🧠 IAM Design Approach
- Ensure correct provisioning logic
- Validate connectors and policies
- Monitor execution

---

## 🔑 Key SailPoint Concepts Used
- Provisioning Plan  
- Provisioning Policy  
- Connectors  
- Workflows  

---

## ⚙️ Step-by-Step Flow

1. Role assigned  
2. Provisioning plan generated  
3. Request sent to target system  
4. Action executed  

---

## ⚠️ Common Issues & Troubleshooting

### ❌ Account Not Created
- Missing provisioning policy  

**Fix:** Configure create operation

---

### ❌ Access Not Assigned
- Entitlement mapping incorrect  

**Fix:** Verify role-entitlement mapping

---

### ❌ Provisioning Failure
- API/connector issue  

**Fix:** Validate endpoint and credentials

---

### ❌ Access Not Removed 🚨
- Leaver logic missing  

**Fix:** Ensure disable/delete configured

---

## 🎤 Interview Talking Points
- Provisioning plan concept  
- Common failures  
- Debugging approach  

---
