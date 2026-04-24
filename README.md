# SOC Analyst Technical Portfolio

This repository documents my hands-on experience in security monitoring, incident response, and threat hunting. My work follows a standardized lifecycle: **Detection, Triage, OSINT Enrichment, Containment, and Remediation.**

## 🛠️ Technical Skillset
- **SIEM/EDR Analysis:** Reviewing host telemetry, process trees, and network logs.
- **OSINT & Sandboxing:** Reputation checks via VirusTotal/AbuseIPDB and detonation via ANY.RUN/Hybrid Analysis.
- **Incident Response:** Effective host isolation, credential resets, and remediation tracking.

## 📂 Investigation Logs

### 🎣 [Phishing & Email Security](./Phishing-Investigations.md)
* **Internal Phishing (SOC120):** Analyzing internal meeting requests and SMTP reputation.
* **Malicious Attachments (SOC140):** Sandbox detonation and perimeter block validation.
* **URL Execution (SOC141):** Investigating `KBDYAK.exe` downloads and performing host isolation.

### 🦠 [Malware Analysis](./Malware-Investigations.md)
* **C2 Beaconing (SOC138):** Identifying outbound HTTP requests to malicious Brazilian infrastructure.
* **Obfuscated Macros (SOC137):** De-obfuscating PowerShell commands within `.docm` files.
* **False Positive Validation (SOC104):** Using dynamic analysis to verify legitimate software installers.

### 🌐 [Web & Vulnerability Attacks](./Web-Attacks.md)
* **SharePoint RCE (SOC342):** Investigating CVE‑2025‑53770 via Base64 and ToolPane.aspx analysis.
* **Checkpoint Gateway LFI (SOC287):** Analyzing directory traversal attacks (`/etc/passwd`) targeting CVE-2024-24919.
