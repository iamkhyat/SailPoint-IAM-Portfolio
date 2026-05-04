# JML Lifecycle – Business Scenario

## Objective
Define a real-world business scenario where Joiner-Mover-Leaver (JML) lifecycle automation is required using SailPoint IdentityIQ.

---

## Business Scenario

A mid-to-large enterprise (e.g., finance or healthcare organization) has:
- 5,000+ employees
- Multiple departments (HR, IT, Finance, Operations)
- 20+ enterprise applications (Active Directory, ERP, Email, HRMS, etc.)

### Current Challenges

Access management is handled manually:
- IT team creates accounts manually
- Access is granted via email requests
- No centralized tracking of user access

---

## Problems Identified

### Joiner Issues (New Employees)
- Delay in account creation (1–3 days)
- New hires cannot access required systems on Day 1
- Productivity loss

---

### Mover Issues (Role/Department Change)
- Old access is not removed
- New access is delayed
- Users accumulate excessive privileges (security risk)

---

### Leaver Issues (Termination)
- Accounts remain active after employee leaves 🚨
- High risk of unauthorized access
- Compliance violations

---

### Additional Risks
- No audit trail of who has access and why
- Difficult to pass compliance audits (SOX, GDPR)
- Increased manual workload for IT team

---

## Business Requirements

The organization wants to:

### Automate Identity Lifecycle
- Automatically create user accounts when employee joins
- Update access when employee changes role
- Remove access immediately upon termination

---

### Implement Role-Based Access Control (RBAC)
- Assign access based on:
  - Department
  - Job title
  - Location
- Reduce manual access requests

---

### Improve Security & Compliance
- Ensure least privilege access
- Maintain audit logs
- Support certification campaigns

---

### Reduce Manual Effort
- Minimize IT intervention
- Automate provisioning and deprovisioning

---

## IAM Solution Overview

To address these challenges, the organization implements SailPoint IdentityIQ:

### Authoritative Source
- HR system becomes the **source of truth**

---

### Identity Lifecycle Automation
- IdentityIQ detects changes from HR system
- Triggers Joiner, Mover, Leaver events automatically

---

### Role-Based Access Assignment
- Access assigned using predefined roles
- Roles mapped based on identity attributes

---

### Automated Provisioning
- Accounts created/updated/disabled automatically
- Integrated with multiple target systems

---

### Governance & Compliance
- Access certifications enabled
- Audit logs maintained
- Policies enforced

---

## Expected Outcome

After implementation:

### Operational Benefits
- Day 1 access for new hires
- Faster role change handling
- Immediate access removal for leavers

---

### Security Benefits
- Reduced orphan accounts
- Enforced least privilege
- Improved visibility of access

---

### Compliance Benefits
- Audit-ready system
- Easy access reviews
- Better governance

---

### Efficiency Gains
- Reduced manual workload by IT team
- Standardized access management process

---

## Interview Talking Points

If asked: “Give a real-world JML scenario”

You can say:

“In a typical enterprise, manual access management leads to delays, excessive privileges, and compliance risks. By implementing JML lifecycle automation in IdentityIQ using an HR system as the authoritative source, we can automate onboarding, role changes, and offboarding, ensuring secure and efficient access management.”

---

## Key Takeaway

JML lifecycle is not just a technical implementation—it is a **business-critical process** that:
- Improves productivity
- Enhances security
- Ensures compliance
