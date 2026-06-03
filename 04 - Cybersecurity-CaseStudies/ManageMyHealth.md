# Case Study: ManageMyHealth Data Breach (2025)

## 📊 Overview

* **Incident Period:** December 30, 2025 (Discovery) – January 2026
* **Threat Actor:** Unknown / Claimed by "Kazu" (Cybercriminal/Extortionist)
* **Target:** ManageMyHealth (New Zealand's largest online patient portal)
* **Primary Vector:** Unauthorized external access via a vulnerability in the platform's document storage module API/code.

## 🚨 The Incident

In late December 2025, ManageMyHealth, the widely used patient portal in New Zealand, suffered a major cybersecurity breach. Discovered on December 30, 2025, unauthorized actors exploited a vulnerability to access a specific feature of the platform, exposing over 400,000 sensitive medical documents. The breach affected approximately 120,000 to 127,000 registered users. The compromised data included highly sensitive clinical documents such as hospital discharge summaries, specialist referrals, laboratory test results, and clinical correspondence. Following the breach, an actor using the moniker "Kazu" claimed responsibility and reportedly attempted extortion, leading the company to seek an urgent High Court injunction to prevent the dissemination of the stolen data.

## 🥷 Attack Chain: How the Hackers Compromised the System

**1. Initial Access**
Sometime prior to December 30, 2025, the attackers exploited specific code gaps related to the platform's "My Health Documents" storage module. This vulnerability allowed unauthorized API or web-facing access without requiring direct compromise of individual user passwords.

**2. Data Exfiltration**
Once access to the module was established, the attackers systematically copied and exfiltrated over 400,000 files. These files contained deep clinical histories, some dating back to 2017, bypassing the core patient database but severely compromising user privacy.

**3. Discovery & Initial Response**
ManageMyHealth was notified of the unauthorized access by a partner organization on December 30. The company immediately mobilized a response team, contained the vulnerability, and engaged independent forensic specialists alongside notifying New Zealand Police, Health New Zealand, and the Privacy Commissioner.

**4. Extortion & Legal Action**
Early in the incident, the attackers leaked a small number of documents online and reportedly demanded a ransom (alleged to be around $60,000). In response, ManageMyHealth secured an interim High Court injunction to legally restrict the publication, reporting, or misuse of the stolen data by third parties and media organizations.

## 🔍 Root Cause

The attackers exploited a structural vulnerability (code gaps) within the document storage module of the platform. Excessive data accessibility and insufficient access controls on this specific module allowed bulk exfiltration of files, demonstrating a failure in API security governance, anomaly detection, and zero-trust segmentation.

## 💥 Business & Human Impact

* **Data Exposure:** Sensitive medical histories, including lab results and specialist letters for over 120,000 patients, were exposed, leaving them vulnerable to identity theft, medical fraud, and targeted phishing/blackmail.
* **Reputational Damage & Loss of Trust:** As New Zealand's largest patient portal (with 1.8 million users), the incident deeply eroded public trust in digital healthcare infrastructure and third-party health data custodians.
* **Legal & Regulatory Scrutiny:** The breach triggered sweeping reviews by Health New Zealand, the Office of the Privacy Commissioner, and the National Cyber Security Centre (NCSC), alongside the unprecedented use of a High Court injunction to suppress data dissemination.

## 🛠️ Remediation & Lessons Learned

* **Immediate Response:** ManageMyHealth secured the compromised feature, mandated strict Two-Step Verification (MFA) for all users, preserved forensic evidence, and directly notified affected patients via dashboard alerts.
* **Strategic Lessons:**
  * **Identity & Access as Critical Infrastructure:** Web-facing healthcare APIs require banking-grade security, continuous session anomaly detection, and strict zero-trust authorization.
  * **Blast Radius Containment:** Patient portals must enforce least privilege by default and segment patient records to prevent bulk data aggregation and exfiltration if a single module is compromised.
  * **Proactive Threat Modeling:** Security monitoring must look beyond standard malware alerts to detect "impossible" behavior, such as abnormal download volumes and repeated document access patterns.

---

### Citations

* Manage My Health. (2026, March 4). *MMH Privacy Breach Public Notice.*
* Wikipedia. (2026). *ManageMyHealth data breach.*
* Accredian / Taiyab Lokhandwala. (2026, February 6). *Case Study: ManageMyHealth Data Breach.*
* Bright Defense. (2026, March 15). *ManageMyHealth Breach Exposes 126K Users.*
* The HiNZ eHealth Forum. (2026, January). *Manage My Health cybersecurity breach 30 Dec 2025.*
