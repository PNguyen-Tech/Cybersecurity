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
* **Critical Policies in Place:**
**Code of Business Conduct:** Formally documents the organization's values and ethical behavioral standards to ensure all staff operate with integrity.  
  Example: An employee is offered a gift from a potential vendor in exchange for a contract. The Code of Business Conduct provides the rules that tell the employee they must decline the gift to avoid a conflict of interest and maintain integrity.  
**Change Management:** Guides staff in documenting, reviewing, and implementing application and infrastructure changes to prevent service degradation or the introduction of vulnerabilities.  
  Example: A developer wants to push a new feature to the Product Fruits platform. Before it goes live, the policy requires them to submit a Pull Request in GitHub for a peer review. This ensures a second pair of eyes checks the code for security flaws before it reaches the production servers.  
**Information Security:** Defines the organization's approach to protecting systems and data, covering design, development, and operational security.  
  Example: The policy dictates that all data must be encrypted. Because of this, the engineering team ensures that the AWS PostgreSQL database is configured with AES 256-bit encryption, ensuring that even if a physical hard drive were stolen, the data would be unreadable.  
**Vendor Management:** Provides guidance on performing risk assessments of third-party suppliers and critical vendors to ensure they meet the company's security standards.  
  Example: Product Fruits uses AWS to host their servers. Under this policy, the Information Security Officer must perform an annual review of AWS’s own SOC 2 report to verify that Amazon is keeping the physical data centers secure.  
**Risk Management:** Describes the formal process for identifying, measuring, and mitigating threats that could impair system security, availability, and confidentiality.  
  Example: During an annual assessment, the team identifies that a specific server is running an outdated version of Linux. They give this a "High Risk" score based on likelihood and impact. They then schedule a patch (mitigation) to fix the vulnerability and lower the risk score.  

* **Policy Enforcement:** 
All staff members have been the the policy and the expectation that they need to follow through. Staff members are required to acknowledge to understanding the policies and complete yearly reviews of them. 

### 6. Data Classification (Data is split into different categories to allow employees to understand it better)
* **Classification Tiers:** 3 Tier model of Confidential/Restrict, Internal/Prviate, and Public. 
* **Encryption Standards:** Data encrypted over HTTPS and data at rest in encrypted Advanced Encrypted Standard (AES) 256-bit algorithm.  

---

## 🚧 System Boundaries & Shared Responsibility

### Boundaries of the Scope (Informs the client of what was audited and what was not)
* **What is Included:** The cloud-hosted software application was audited to determine its effetives in security, confidentality, and availability.
* **What is Excluded (Vendor Risk):** AWS, GitHub, and Microsoft Office 365. 

### Complementary User Entity Controls (CUECs) - (This is the users' responsibility to ensure the software will work as intended as long as users follow the guidelines)
* **Customer Responsibilities:** Customers must actively manage their software application account and establish customized security solutions or automated processes. They must ensure only authorized users are appointed as administrators for granting access, and they must immediately notify Product Fruits of any unauthorized account use or suspected security breaches. Additionally, customers are fully responsible for any data modifications or changes made to user and organizational data stored within the application, and they must communicate all relevant security and availability issues to Product Fruits through identified corporate support channels.

---

## 💡 Key Takeaways for Cloud Compliance
This case study highlights the critical operational mechanics of the Cloud Shared Responsibility Model in modern cloud deployments. It clearly defines security boundaries, illustrating where the infrastructure provider's liability ends and the organization's technical ownership begins. Whether deploying in AWS or Microsoft Azure, foundational GRC strategies remain identical: enforcing strict Role Based Access Control (RBAC) and the Principle of Least Privilege to effectively minimize the blast radius of a potential breach.

Furthermore, this report demonstrates that modern compliance relies heavily on cloud native automation and strict version control. Rather than relying on manual checks, written policies are  enforced through tools like GitHub peer reviews for change management and Sprinto for continuous compliance monitoring. Finally, the report highlights the  procedures required to respond to a data breach—such as severity classification and customer notification timelines—paired alongside the  preventative security measures (like MFA and AES 256 bit encryption at rest) designed to prevent a breach from occurring in the first place. Ultimately, auditing a modern cloud application requires evaluating an interconnected ecosystem of third party tools, verifying that every automated workflow aligns seamlessly with organizational risk boundaries.
