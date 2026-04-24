---
tags:
  - phishing
  - labs
categories:
  - "[[Labs]]"
---
```table-of-contents
```
---
# 🗣️ TALION SCRIPT: The Phishing Workflow
> "When handling phishing, I follow a strict four-phase approach: **Ingestion**, **Enrichment**—where our SOAR automatically extracts the IOCs—**Investigation**, and finally **Response**, which usually involves purging the malicious emails. I make sure to document every step in the ticket to maintain that **'Glass Box' transparency** for the client. Keeping that workflow tight is exactly how we drive down the **MTTR**."

---

## 🟢 SOC120: Phishing Mail Detected (Internal to Internal)
**Verdict:** False Positive

### 1. Triage & Analysis
* **Alert:** Internal phishing from `john[@]letsdefend.io` to `susie[@]letsdefend.io`.
* **Investigation:** Extracted the `.eml` file; no malicious attachments were found. 
* **Enrichment:** Ran the SMTP address through VirusTotal (Clean). Evaluated Exchange Server network logs and found no anomalous routing activity.

### 2. Containment & Remediation
* **Transparency/Client Update:** Ticket updated to reflect benign internal communication. Recommended SIEM rule fine-tuning to reduce false-positive noise and improve MTTR.

### 3. Artifacts (IOCs)
* **Sender:** `john[@]letsdefend.io`
* **Recipient:** `susie[@]letsdefend.io`

---

## 🔴 SOC140: Malicious Phishing Mail with Attachment
**Verdict:** True Positive

### 1. Triage & Analysis
* **Alert:** Inbound email from `aaronluo@cmail.carleton.ca` to `mark@letsdefend.io` via SMTP `189.162.189.15`.
* **Investigation:** Detonated the payload in a Hybrid Analysis sandbox; results confirmed it was 100% malicious. 
* **Enrichment:** Checked device logs and verified the email security gateway successfully blocked delivery.

### 2. Containment & Remediation
* **Transparency/Client Update:** Added sender IP and domain to the global blocklist. No host containment required as the perimeter defense held. 

### 3. Artifacts (IOCs)
* **Sender IP:** `189.162.189.15`
* **Sender Address:** `aaronluo@cmail.carleton.ca`

---

## 🔴 SOC141: Phishing URL Detected (Compromised Endpoint)
**Verdict:** True Positive

### 1. Triage & Analysis
* **Alert:** Suspicious URL accessed internally: `hxxp://mogagrocol[.]ru...`.
* **Investigation:** Endpoint terminal history revealed a command executing the download of `KBDYAK.exe`. Network logs confirmed only this specific endpoint was communicating with the threat infrastructure.

### 2. Containment & Remediation
* **Action:** Immediately isolated the host from the network to prevent lateral movement.
* **Transparency/Client Update:** Alerted the affected user, removed the malicious payload, and monitored the endpoint post-restoration. 

### 3. Artifacts (IOCs)
* **Malicious URL:** `hxxp://mogagrocol[.]ru/wp-content/plugins/akismet/fv/index.php?email=ellie@letsdefend.io`
* **Payload:** `KBDYAK.exe`

---

# 🗣️ TALION SCRIPT: Operations & Handovers
> "I treat operations very seriously. My shift always starts with a **Morning Telemetry Integrity Check** to ensure our sensors are actually feeding data into the SIEM. At the end of the day, I prioritize the **live 10-to-15-minute shift handover briefing**. Good documentation is great, but a live sync ensures nothing falls through the cracks between shifts."

# 🚨 EMERGENCY PIVOT SCRIPT (If you don't know the answer)
> "That’s a great question. I haven't encountered that specific scenario yet, so I would consult our **internal knowledge base** first. If I couldn't verify the activity within my triage SLA, I would gather the relevant logs, document my findings clearly in the ticket, and **escalate to Tier 2 to preserve the SLA**."