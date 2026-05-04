# IdentityIQ JML Lifecycle

## Objective
Demonstrate end-to-end implementation of Joiner-Mover-Leaver (JML) lifecycle automation in SailPoint IdentityIQ to manage user identities and access efficiently.

---

## Business Scenario
In an enterprise environment:
- New employees join frequently (Joiner)
- Existing employees change roles or departments (Mover)
- Employees leave the organization (Leaver)

Manual access management leads to:
- Delayed onboarding
- Excess access (security risk)
- Compliance violations

Goal: Automate identity lifecycle and access provisioning.

---

## IAM Design Approach

The JML lifecycle is driven by:
- Authoritative source (HR system)
- Identity attributes (department, role, status)
- Role-Based Access Control (RBAC)
- Provisioning workflows

Core strategy:
1. Detect identity changes from HR system
2. Trigger lifecycle events
3. Assign/remove access automatically
4. Maintain audit and compliance

---

## Key SailPoint Concepts Used

- Identity Lifecycle Management
- Authoritative Source (HR Feed)
- Identity Attributes
- RBAC (Roles & Entitlements)
- Lifecycle Events (Joiner, Mover, Leaver)
- Provisioning Policies
- Workflows
- Access Revocation

---

## Step-by-Step Flow

### Joiner (New Hire)
1. User created in HR system
2. Identity aggregated into IdentityIQ
3. Identity attributes assigned (department, title)
4. Role assigned based on business rules
5. Provisioning triggered to target systems
6. Accounts created automatically

---

### Mover (Role Change)
1. Change detected in HR system (department/title)
2. Identity updated in IdentityIQ
3. Old roles removed
4. New roles assigned
5. Access updated across applications

---

### Leaver (Termination)
1. Termination status received from HR system
2. Identity marked inactive
3. All roles removed
4. Access revoked across systems
5. Accounts disabled or deleted

---

## Supporting Files in This Module

### Business-Scenario.md
- Detailed enterprise use case for JML lifecycle

### Lifecycle-Flow.md
- Deep dive into lifecycle execution flow

### Provisioning-Logic.md
- How provisioning decisions are made
- Role-based vs direct provisioning

### Identity-Attributes.md
- Key attributes used in lifecycle decisions
- Mapping logic (e.g., department → role)

### Common-Issues.md
- Real-world problems and fixes

---

## Common Issues & Troubleshooting

### Identity Not Created
- Aggregation not configured correctly
- HR source not defined as authoritative

### Roles Not Assigned
- Missing or incorrect attribute mapping
- Role rules not configured properly

### Provisioning Failure
- Provisioning policy misconfiguration
- Target system connectivity issues

### Access Not Revoked (Leaver Risk )
- Lifecycle event not triggered
- Disable/delete logic missing

---

## End-to-End JML Flow (Conceptual)

HR System  
↓  
IdentityIQ Aggregation  
↓  
Identity Creation / Update  
↓  
Role Assignment (RBAC)  
↓  
Provisioning Engine  
↓  
Target Applications  

---

## Interview Talking Points

If asked: “Explain JML lifecycle”

You can say:

“JML lifecycle in IdentityIQ is driven by an authoritative HR source. When a user joins, moves, or leaves, IdentityIQ detects changes through aggregation, assigns or removes roles based on identity attributes, and provisions or deprovisions access automatically across connected systems.”

---

## Key Strengths Demonstrated

- Strong understanding of identity lifecycle automation
- Practical RBAC implementation
- Real-world provisioning logic
- Security and compliance awareness
- Ability to troubleshoot lifecycle issues

---

## Notes for Reviewers

- This module focuses on conceptual clarity + real-world implementation
- Designed to be easy to explain during interviews
- Reflects enterprise IAM practices

---
