# ⚠️ JML Lifecycle – Common Issues & Troubleshooting

## 🎯 Objective
Identify common real-world issues encountered during Joiner-Mover-Leaver (JML) lifecycle implementation in SailPoint IdentityIQ and provide practical troubleshooting approaches.

---

## 🏢 Business Scenario
In enterprise IAM environments, even well-designed JML implementations face issues due to:
- Data inconsistencies from HR systems
- Configuration errors
- Integration failures
- Timing and synchronization problems

These issues can impact:
- User onboarding
- Access accuracy
- Security and compliance

---

## 🧠 IAM Design Approach

Troubleshooting in IdentityIQ follows a structured approach:

1. Identify issue type (Aggregation / Correlation / Provisioning)
2. Validate input data (HR source)
3. Check IdentityIQ configuration
4. Review logs and task results
5. Reproduce and resolve issue

👉 Key principle:
**Every issue originates from data, logic, or integration**

---

## 🔑 Key SailPoint Concepts Used

- Aggregation Tasks
- Identity Cube
- Correlation Rules
- Provisioning Plans
- Lifecycle Events
- Workflows
- Logs (ccg.log, debug logs)
- Task Results

---

## ⚙️ Step-by-Step Troubleshooting Flow

1. Identify the issue (Joiner / Mover / Leaver)
2. Check HR data (source of truth)
3. Verify aggregation results
4. Validate identity attributes
5. Check role assignment logic
6. Review provisioning plan
7. Analyze logs
8. Fix configuration and re-run process

---

## ❌ Common Issues & Fixes

---

### 🔴 Issue 1: Identity Not Created (Joiner Failure)

**Symptoms:**
- New employee not visible in IdentityIQ

**Possible Causes:**
- Aggregation not executed
- HR source not configured as authoritative
- Data missing in HR feed

**Fix:**
- Run aggregation task
- Verify HR connector configuration
- Validate incoming data file/API

---

### 🔄 Issue 2: Incorrect Role Assignment (Mover Issue)

**Symptoms:**
- User retains old access after role change
- New access not assigned

**Possible Causes:**
- Attribute mapping incorrect
- Role assignment rules not dynamic
- Attribute change not detected

**Fix:**
- Verify attribute values (department, title)
- Check role rules logic
- Re-run identity refresh

---

### 🔴 Issue 3: Access Not Revoked (Leaver Risk 🚨)

**Symptoms:**
- Terminated user still has active accounts

**Possible Causes:**
- Status attribute not mapped correctly
- Leaver lifecycle event not triggered
- Disable/delete logic missing

**Fix:**
- Validate status field mapping (e.g., "Terminated")
- Check lifecycle event configuration
- Ensure provisioning policies include disable action

---

### ❌ Issue 4: Provisioning Failure

**Symptoms:**
- Access not created/updated in target system

**Possible Causes:**
- Connector configuration issue
- Target system not reachable
- Invalid credentials
- API failure

**Fix:**
- Check connector settings
- Validate endpoint connectivity
- Review provisioning logs
- Retry provisioning task

---

### ❌ Issue 5: Identity Correlation Failure

**Symptoms:**
- Duplicate identities created
- Accounts not linked to correct user

**Possible Causes:**
- Missing unique identifier (Employee ID / Email)
- Incorrect correlation rule

**Fix:**
- Update correlation rule logic
- Ensure unique attribute is consistent
- Clean duplicate identities if needed

---

### ❌ Issue 6: Aggregation Not Pulling Data

**Symptoms:**
- No accounts or entitlements imported

**Possible Causes:**
- Connector misconfiguration
- Query/filter issue
- Permission issues

**Fix:**
- Validate connector configuration
- Test connection manually
- Review aggregation logs

---

### ❌ Issue 7: Delayed Lifecycle Processing

**Symptoms:**
- Access changes not happening on time

**Possible Causes:**
- Aggregation schedule delay
- Task scheduling issues

**Fix:**
- Adjust aggregation frequency
- Verify task scheduler configuration

---

## 🔍 Debugging Tools in IdentityIQ

- **Task Results Page** → Check aggregation/provisioning results  
- **Identity Debug Page** → Inspect identity attributes and roles  
- **Logs (ccg.log)** → Identify system errors  
- **Provisioning Transactions** → Track provisioning execution  

---

## 🎤 Interview Talking Points

👉 If asked: “How do you troubleshoot IAM issues?”

You can say:

“I follow a structured approach—first identify whether the issue is in aggregation, correlation, or provisioning. Then I validate source data from HR, check identity attributes, review role assignment logic, and analyze provisioning plans and logs to find the root cause.”

---

## 🚀 Key Takeaways

- Most IAM issues are **data-related**
- HR system is the **source of truth**
- Correlation and attribute mapping are critical
- Logs are essential for debugging
- Structured troubleshooting saves time

---

## 📌 Notes for Reviewers

- This file reflects real-world IAM challenges
- Focus is on practical debugging, not theory
- Demonstrates production-level thinking
