# Phase 1: System Description Analysis

## 🎯 Objective
To deconstruct the "Description of the System" (Section 3) from the Product Fruits SOC 2 Type 2 report. This analysis identifies how the organization defines its boundaries and categorizes its core components prior to applying security controls. This sample report also allows me to practice translating Azure to AWS system. 

---

## 🏗️ System Components Breakdown

### 1. Overview of Operations
* **Primary Service Provided:**
Product Fruits is a cloud-hosted software application acting as a digital adoption platform for web applications.
* **Core Commitments:**
 The company utilizes role-based authentication to enforce least privilege and actively monitors key infrastructure components to generate alerts. Data is protected via industry-standard encryption both at rest and in transit. Furthermore, non-disclosure agreements are enforced across employees, contractors, and third parties to ensure information is only used for its explicit purpose. Product Fruits s.r.o. commits to continuous system monitoring, timely customer response procedures, and periodic testing of their business continuity and disaster recovery plans to ensure viable product delivery.

### 2. Infrastructure & Network Architecture
* **Cloud Provider:**
AWS
* **Network Security Mechanisms:**
Product Fruits secures its network by using a Virtual Prviate CLoud that has a single authrozied point of entry with firewalls. As users connects with the the web application, data is encrypted over HTTPS
* **Data Flow:** [Briefly map how a user connects to the application from the internet to the internal servers.]

### 3. Software
* **Key Applications/Tools:** [List the main software components utilized, e.g., GitHub for version control, Office 365 for communication.]
* **Primary Tech Stack:** [List languages/frameworks if mentioned.]

### 4. People
* **Key Roles Identified:** [List the essential security and operational roles, e.g., Information Security Officer, Compliance Program Manager.]
* **Access Philosophy:** [Describe the overarching approach to user access, e.g., Principle of Least Privilege, Role-Based Access Control (RBAC).]

### 5. Procedures
* **Critical Policies in Place:** [List 3-5 major policies mentioned, e.g., Change Management, Incident Management, Data Retention.]
* **Policy Enforcement:** [How are employees held accountable? e.g., Annual acknowledgments, security awareness training.]

### 6. Data Classification
* **Classification Tiers:** [Define the data tiers used by the organization, e.g., Customer Confidential, Company Confidential, Public.]
* **Encryption Standards:** [Note the encryption used for data at rest and in transit, e.g., AES 256-bit, TLS 1.2+.]

---

## 🚧 System Boundaries & Shared Responsibility

### Boundaries of the Scope
* **What is Included:** [Define exactly what parts of the business are covered by this audit.]
* **What is Excluded (Vendor Risk):** [Identify what relies on third parties and how that risk is managed, e.g., relying on AWS physical security reports.]

### Complementary User Entity Controls (CUECs)
* **Customer Responsibilities:** [List key actions the end-user must take to maintain security, e.g., managing their own user access, reporting suspicious activity.]

---

## 💡 Key Takeaways for Cloud Compliance
[Write a short paragraph reflecting on how this system description applies to modern cloud deployments. For example, note how heavily the organization relies on automated cloud-native tools or strict version control (like GitHub) to enforce their written procedures.]
