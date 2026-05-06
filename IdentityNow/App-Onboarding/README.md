# 🔌 IdentityNow – Application Onboarding

## 🎯 Objective
Provide a comprehensive understanding of how applications (Sources) are onboarded into SailPoint IdentityNow to enable identity aggregation, access management, and governance in a cloud-based IAM environment.

---

## 🏢 Business Scenario
An enterprise uses multiple systems:

- Workday (HR system)
- Active Directory (User directory)
- Salesforce (CRM)
- ServiceNow (ITSM)

Each system manages:
- User accounts
- Access permissions

👉 Challenges:
- No centralized visibility
- Manual provisioning
- Compliance risks

👉 Goal:
Onboard all applications into IdentityNow for centralized governance.

---

## 🧠 IAM Design Approach

IdentityNow uses a **Source-based onboarding model**:

- Each application is onboarded as a **Source**
- Connectors handle integration
- Aggregation pulls accounts and entitlements
- Identity Profiles manage identity correlation

👉 Key principle:  
**Source → Aggregation → Identity → Access Governance**

---

## 🔑 Key SailPoint Concepts Used

- Sources (Applications)
- Connectors (SaaS / Virtual Appliance)
- Aggregation (Full / Incremental)
- Identity Profiles
- Correlation Rules
- Provisioning Policies

---

## ⚙️ End-to-End Onboarding Flow

### 🔹 Step 1: Source Creation
- Add application as a Source
- Select appropriate connector

---

### 🔹 Step 2: Connector Configuration
- Configure authentication:
  - OAuth / API Token / Credentials
- Validate connectivity

---

### 🔹 Step 3: Schema Discovery
- Import:
  - Account attributes
  - Entitlement attributes

---

### 🔹 Step 4: Aggregation
- Run full aggregation
- Import accounts and access data

---

### 🔹 Step 5: Identity Correlation
- Link accounts to identities using:
  - Email
  - Employee ID

---

### 🔹 Step 6: Access Modeling
- Create Access Profiles from entitlements

---

### 🔹 Step 7: Provisioning Enablement
- Configure create/update/delete operations

---

## 🔄 Architecture Flow

Source System  
↓  
Connector  
↓  
Aggregation  
↓  
IdentityNow  
↓  
Identity Profiles  
↓  
Access Profiles  
↓  
Provisioning  

---

## ⚠️ Common Issues & Troubleshooting

### ❌ Connection Failure
- Invalid credentials  
- API misconfiguration  

---

### ❌ Aggregation Issues
- Missing accounts  
- Incorrect filters  

---

### ❌ Correlation Failure
- Missing unique attributes  

---

### ❌ Provisioning Not Enabled
- Policy not configured  

---

## 🎤 Interview Talking Points

👉 If asked: “How do you onboard applications in IdentityNow?”

You can say:

“Applications are onboarded as sources using connectors. After configuring authentication and schema, aggregation pulls account and entitlement data. Identity profiles correlate accounts to identities, and access is managed using access profiles and provisioning policies.”

---

## 🚀 Key Takeaways

- Source-based onboarding model  
- Connector-driven integration  
- Aggregation is foundational  
- Identity profiles drive correlation  
- Enables full lifecycle governance  

---

## 📌 Notes for Reviewers

- Reflects real-world IdentityNow onboarding  
- Focus on architecture + execution  
- Designed for scalability and governance  
