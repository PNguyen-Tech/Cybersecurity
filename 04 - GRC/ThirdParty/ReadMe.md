# 📝 Third-Party Risk & Vendor Assessments

## Overview

This directory contains a collection of simulated audits, framework deconstructions, and risk assessments. These projects demonstrate the practical application of Governance, Risk, and Compliance (GRC) principles to external environments, vendor services, and third-party integrations.
---

## 📂 Directory Contents

### 1. GRC Project Initiation: Decoding a SOC 2 Type 2 Report

A foundational project deconstructing a real-world SOC 2 Type 2 report to understand how enterprise cloud service providers map technical configurations to formal auditing standards.

* **Phase 1 - Document Analysis & Framework Deconstruction:** Analyzing system boundaries (Infrastructure, Software, People, Procedures, Data) and Trust Services Criteria (Security, Availability, Confidentiality).
* **Phase 2 - Control Extraction & Mapping:** Translating theoretical controls into practical checklists, mapping SOC 2 requirements to cloud-native architecture (e.g., Azure IAM policies, GitHub Actions).
* **Phase 3 - Simulated Audit & Technical Implementation:** Applying extracted controls to generate a formal GRC report demonstrating audit readiness.

### 2. Vanguard Vitality: Information Systems Risk Register

A targeted risk assessment evaluating a rapidly expanding regional fitness chain's onboarding processes and data handling practices.

* **The Threat Landscape:** Assessing the use of standard, public-facing Google Forms and Google Sheets for processing new member applications.
* **Risk Assessment Matrix:** Utilizing a standard Likelihood x Impact (1-5) scoring key to categorize threats from Low to Critical.
* **Key Findings:** Identification of High-risk financial data exfiltration vulnerabilities and Medium-risk "Shadow IT" database access issues, paired with proposed mitigation strategies like migrating to PCI-compliant payment gateways.

### 3. Azure Storage Account (Customer Invoices): ISO 27001 Assessment

A comprehensive technical evaluation of a high-value cloud asset through the lens of the CIA triad, mapping identified vulnerabilities directly to ISO 27001 standards and Azure technical controls.

* **Confidentiality:** Mitigating unauthorized data exfiltration risks by enforcing blocked public access and strict Role-Based Access Control (RBAC) via Microsoft Entra ID (ISO 27001 Annex A 5.15, 8.24).
* **Integrity:** Preventing malicious alteration of generated customer invoices by implementing Immutable Storage and WORM (Write Once, Read Many) policies.
* **Availability:** Ensuring business continuity against regional outages or accidental deletion through Geo-Redundant Storage (GRS) replication and Blob Soft Delete retention policies (ISO 27001 Annex A 8.14).
* **Risk Treatment Summary:** A formal register tracking inherent risk levels against the applied Azure technical controls to prove managed residual risk.
