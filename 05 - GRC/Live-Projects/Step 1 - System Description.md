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
* **Data Flow:**  
1) The data flow initiates when a client connects via the public internet utilizing TLS-encrypted HTTPS.  
2) Upon reaching the AWS EU-West-1 region, traffic is routed through either an Application Load Balancer (ALB) for standard web requests or an API Gateway for programmatic service requests.  
3) From the ALB, requests are processed by the core web application hosted on Elastic Container Service (ECS) Fargate instances.  
4) To decouple backend processing, the ECS services pass asynchronous tasks to SNS (notifications) and SQS (message queues).  
5) These queues trigger AWS Lambda functions, which execute the necessary backend logic.  
6) Finally, the Lambda functions write to the deepest layer of the private network: the data tier, consisting of Amazon DocumentDB (NoSQL) and PostgreSQL (Relational) databases.

### 3. Software
* **Key Applications/Tools:**
 **Product Fruits Application:** The core cloud-hosted SaaS platform being audited.  
 **AWS IAM:** Manages identity and access to AWS cloud resources.  
 **AWS Firewalls:** Protects the network perimeter and segregates backend database servers from internal traffic.  
 **GitHub:** Serves as the source code repository and enforces version control.  
 **Office 365:** Provides the internal identity/email provider and collaboration suite for employees.  
 **Sprinto:** A continuous compliance monitoring tool used to track the health of the security program.  
 **Primary Tech Stack:**
C#, javaScript, Go, and Python

### 4. People
* **Key Roles Identified:**  
**Senior Management**  Carries the ultimate responsibility for achieving the organization's mission and objectives while ensuring resources are effectively applied to the security program.  
**Information Security Officer** Assigned by Senior Management to manage the performance of the information security program, including identifying threats and implementing controls to mitigate risks.  
**Compliance Program manager** Responsible for the smooth functioning of the Information Security Program and ensuring the timely completion of tasks required for all information security controls.  
**System Users** Staff members who utilize the IT systems according to established policies and guidelines; they are required to complete annual security awareness training.  

* **Access Philosophy:**  
**Role-Based Access Control (RBAC):** The system utilizes a role-based security architecture that requires users to be identified and authenticated before accessing system resources.   
**Principle of Least Privilege (PoLP):** All access to critical systems is granted based on the minimum necessary permissions required for a staff member to perform their specific job function.  

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
