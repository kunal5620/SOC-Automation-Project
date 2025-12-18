# DFIR SOC Automation Project – Wazuh, Shuffle & TheHive

## 📌 Project Overview
This project demonstrates an **automated SOC & DFIR workflow** designed to detect, enrich, and respond to security alerts using **Wazuh**, **Shuffle SOAR**, and **TheHive**.

The automation focuses on **Windows-based attack detection (Mimikatz execution)** and performs **hash enrichment, threat intelligence lookup, analyst notification, and incident creation** without manual intervention.

---

## 🎯 Project Objectives
- Detect malicious activity on a Windows endpoint using **custom Wazuh rules**
- Automate alert ingestion using **Shuffle Webhooks**
- Perform **SHA-256 hash extraction and enrichment**
- Query **VirusTotal** for threat intelligence
- Notify SOC analysts via **Email**
- Automatically create **cases in TheHive**
- Demonstrate real-world **DFIR & SOC automation capabilities**

---

## 🛠 Tools & Technologies Used
- **Wazuh** – SIEM / XDR (Custom Rules)
- **Shuffle** – SOAR Automation Platform
- **TheHive** – Incident Response & Case Management
- **VirusTotal API** – Threat Intelligence Enrichment
- **Windows OS** – Monitored Endpoint
- **VirtualBox** – Virtualized Lab Environment
- **Ubuntu Linux** – SOC Infrastructure
- **Webhooks & REST APIs**

---

## 🏗 Lab Environment
The project is deployed in a **VirtualBox-based SOC lab**:

- **Windows VM**
  - Wazuh Agent installed
  - Mimikatz execution simulated
- **Linux VM**
  - Wazuh Manager
  - Shuffle SOAR
  - TheHive

---

## 🔄 SOC Automation Workflow (Shuffle)

The following automation was implemented in **Shuffle**:

### 🔹 Workflow Steps
1. **Webhook Trigger**
   - Wazuh sends alerts to Shuffle via **Webhook**
   - Triggered when the custom Mimikatz rule fires

2. **SHA-256 Hash Processing**
   - Extracts **SHA-256 file hash** from the alert payload
   - Prepares data for threat intelligence lookup

3. **VirusTotal Authentication (VT-Auth)**
   - Authenticates to VirusTotal using API
   - Submits hash for reputation analysis

4. **Parallel Automated Actions**
   - 📧 **Email Notification**
     - Sends alert details to the SOC team
     - Includes severity, hostname, user, and threat context
   - 🐝 **TheHive Case Creation**
     - Automatically creates a case in TheHive
     - Populates alert metadata and enrichment results

---

## 🧠 Use Case: Mimikatz Execution Detection

### 🔍 Detection Logic
- A **custom Wazuh rule** detects **Mimikatz execution artifacts** on Windows
- Indicators include:
  - Process name
  - Command-line strings
  - Credential dumping behavior

### 🧩 MITRE ATT&CK Mapping
- **T1003 – Credential Dumping**
- **TA0006 – Credential Access**

---

## 📸 Automation Screenshot
The following image shows the complete Shuffle automation pipeline:

- Webhook ingestion
- Hash extraction
- VirusTotal enrichment
- Email alerting
- TheHive case creation

