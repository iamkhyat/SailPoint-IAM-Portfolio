# 🛡️ IdentityIQ Certifications (Access Reviews)

## 🎯 Objective
Demonstrate how access certifications (access reviews) are designed and executed in SailPoint IdentityIQ to ensure compliance and proper access governance.

---

## 🏢 Business Scenario
An enterprise must periodically review user access to:
- Ensure least privilege
- Detect excessive or inappropriate access
- Meet compliance requirements (SOX, GDPR)

Access is distributed across multiple systems and roles, requiring centralized review.

---

## 🧠 IAM Design Approach

Certification process follows:

1. Define certification campaign
2. Identify reviewers (managers/app owners)
3. Present access for review
4. Collect decisions (approve/revoke)
5. Trigger remediation
6. Maintain audit trail

---

## 🔑 Key SailPoint Concepts Used

- Certification Campaigns
- Reviewers (Manager / Owner)
- Access Reviews
- Revocation Requests
- Remediation
- Audit Logs
- Policies (SoD)

---

## ⚙️ Step-by-Step Flow

1. Create certification campaign  
2. Define scope (users/apps/roles)  
3. Assign reviewers  
4. Launch campaign  
5. Reviewers approve/revoke access  
6. Remediation triggered  
7. Track completion and audit  

---

## 📊 Architecture Flow (Conceptual)

Campaign Created  
↓  
Reviewers Assigned  
↓  
Access Review  
↓  
Approve / Revoke  
↓  
Remediation  
↓  
Audit Logging  

---

## ⚠️ Common Issues & Troubleshooting

- Reviewer not assigned → Incorrect configuration  
- Campaign delays → Notification/workflow issue  
- Revocation not executed → Provisioning issue  

---

## 🎤 Interview Talking Points

“Certifications in IdentityIQ ensure that user access is periodically reviewed by business owners. Reviewers validate whether access is still required, and revoked access is automatically remediated through provisioning workflows.”

---
