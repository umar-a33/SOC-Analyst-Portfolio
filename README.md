# My Cybersecurity Portfolio — Offensive & Defensive

**Umar Ahmed** — Cybersecurity Student · AWS Cloud Pentester · SOC Analyst in training · OSCP candidate.

> *Evidence over conversation. Terminal output or it didn't happen.*

---

## What's in here

This repo is my lab evidence — real investigations, real terminal logs, real screenshots. I do both **red team** (offensive) and **blue team** (defensive) work, because the 16‑week roadmap doesn't pick sides.

### 🔴 Offensive — Pentesting & Exploitation

- **Web Attacks** — SQLi, XSS, CSRF, SSRF, IDOR, Command Injection... the full OWASP Top 10, exploited blind
- **AWS Cloud Pentesting** — IAM privilege escalation, Lambda exploitation, IMDS attacks, S3 bucket hunting, cross‑service chains (Beanstalk, SNS)
- **Active Directory** — Kerberoasting, AS‑REP roasting, Golden Ticket, BloodHound mapping
- **AI / LLM Attacks** — Prompt injection, RAG exploitation, agentic workflow hijacking, Garak testing

### 🔵 Defensive — SOC & Incident Response

- **Phishing Triage** — Header analysis, payload extraction, domain reputation checks, containment playbooks
- **Malware Analysis** — Static & dynamic analysis, IOC extraction, sandboxing
- **Web Attack Detection** — Log analysis, WAF bypass detection, attack chain reconstruction

---

## The Pentesting Workflow (Hermes + Agent0)

I run an agentic workflow that splits thinking from execution:

| Role | Tool | What it does |
|------|------|-------------|
| **Brain** 🧠 | Hermes | Strategy, planning, research, vault management, cron jobs |
| **Hands** 🔧 | Agent0 | CLI execution, lab work, browser automation, evidence capture |
| **Memory** 📝 | Obsidian | PARA‑lite vault, synced phone↔desktop, managed by Hermes |
| **Backup** 🗄️ | GitHub | Hermes config, lab repos, portfolio evidence |

**The loop:**
```
Hermes plans → Umar reviews → Agent0 executes → Evidence captured → Hermes vaults it
```

This isn't just a study workflow — it's a **homelab‑adjacent portfolio builder**. Every lab session produces:
- Terminal output (real, raw, timestamped)
- Screenshots (exploit success, tool output, configurations)
- A note in Obsidian (PARA‑lite, searchable, reviewable)
- An artifact in this repo (for CV and interview evidence)

---

## Current Focus (16‑Week Roadmap)

| Phase | Timeline | Focus |
|-------|----------|-------|
| 1 | Weeks 1–4 | Web Fundamentals (PortSwigger Academy, OWASP Top 10) |
| 2 | Weeks 5–10 | AWS Pentesting — CORE (Simply Cyber, 67 lessons, 2 capstones) |
| 3 | Weeks 11–16 | Network + Active Directory (BloodHound, Impacket, Kerberos) |
| 4 | Weeks 17–22 | AI Logic + Agent Exploitation (Arcanum, Garak, RAG) |
| 5 | Ongoing | CTFs + Bug Bounty (HTB, THM, HackerOne) |
| 6 | Certifications | eJPT → AWS Security Specialty → OSCP |

*Currently on: AWS CORE — IAM enumeration phase.*

---

## Why this repo exists

Because a CV that says "I know cloud pentesting" means nothing.
A CV linked to a repo with terminal output, exploit logs, and documented methodologies means everything.

This is my proof of work.

---

*focused. minimal. execution‑first.*
