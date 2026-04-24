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
