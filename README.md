# Splunk Threat Hunting Query Arsenal

A collection of **125+ Splunk SPL queries** and reference material for Windows, Linux, and Active Directory threat hunting, mapped to the MITRE ATT&CK framework.

Plus a **threat hunting cheatsheet** covering event IDs, attack chains, and detection patterns.

![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)
![Splunk](https://img.shields.io/badge/Splunk-SPL-000000?logo=splunk)
![MITRE ATT&CK](https://img.shields.io/badge/MITRE-ATT%26CK-red)

---
## Preview 

<img width="1663" height="973" alt="html" src="https://github.com/user-attachments/assets/c7a0861a-1886-40ae-8403-8b78b8fe8571" />



---
## 📦 What's in the Repo

| File | Description |
|------|-------------|
| `Splunk_Threat_Hunting_Arsenal.html` | Interactive HTML with 125+ Splunk queries, search/filter, copy-to-clipboard |
| `Threat_Hunting_Cheatsheet.pdf` | Printable cheatsheet — event IDs, Kerberos reference, 18 attack chains, detection SPL |
| `README.md` | You're reading it |
| `LICENSE` | MIT License |

---

## 🎯 What's Covered

**Splunk Arsenal — 17 sections:**

- 🔥 First-Minute Triage
- 🔭 Reconnaissance
- 🎯 Initial Access
- ⚙️ Execution
- 🔩 Persistence
- 🪜 Privilege Escalation
- 🛡️ Defense Evasion
- 🔑 Credential Access (Mimikatz, Kerberoast, DCSync, Golden/Silver Ticket)
- 🗺️ Discovery
- ↔️ Lateral Movement
- 📡 Command & Control (incl. DGA, beacon detection)
- 📤 Exfiltration
- 💀 Ransomware Detection
- 🧬 IoC Hunting
- ⏱️ Timeline Reconstruction
- 🐧 Linux / Web Server
- 🌐 Web Application Attacks

**Cheatsheet — 3 parts:**

- **Part A** — Reference tables: Windows event IDs, Logon types, Kerberos, Sysmon, LOLBins, LSASS access masks, ADCS ESC map, tool fingerprints
- **Part B** — 18 MITRE ATT&CK attack chains (phishing→ransomware, NTLM relay, ADCS abuse, Zerologon, Golden Ticket, BYOVD, etc.)
- **Part C** — 60+ Splunk SPL detection queries organized by MITRE tactic

---

## 🚀 Quick Start

1. **Clone or download** this repo
2. Open `Splunk_Threat_Hunting_Arsenal.html` in any browser — it's self-contained, no dependencies
3. Use the search box to filter queries (e.g. `kerberoast`, `lsass`, `4624`, `DCSync`)
4. Click any query to copy it to clipboard
5. Paste into your Splunk search bar and **adapt to your environment**

---

## ⚠️ Important — Read Before Using

These queries are **patterns, not drop-in detection rules.** You will need to:

- **Adjust indexes and sourcetypes** — the queries assume conventions like `index=windows`, `sourcetype=XmlWinEventLog`. Your environment may differ.
- **Check field names** — field names vary by the Splunk TA (Add-on) you use. CIM-compliant naming helps.
- **Tune thresholds** — anything with `| where count >= N` is a starting point. Calibrate against your baseline.
- **Test before alerting** — some queries (e.g. Silver Ticket detection, beacon timing analysis) have meaningful false positive rates and should start as hunts, not alerts.

**The goal is inspiration + starting point, not copy-paste perfection.**

---

## 🎓 Who This Is For

- Blue team analysts learning Splunk threat hunting
- Detection engineers building out SOC content
- Anyone studying for threat hunting / DFIR certifications
- Students and hobbyists experimenting in home labs

## 🚫 What This Is NOT

- Not affiliated with any certification vendor or training provider
- Not reproduced from any proprietary course material
- Not a replacement for tuned, production-grade detection rules in your SIEM

---

## 📚 Sources & Inspiration

These materials were built by distilling publicly available threat intelligence and detection engineering knowledge, including:

- [MITRE ATT&CK](https://attack.mitre.org/)
- [Sigma rules](https://github.com/SigmaHQ/sigma)
- [LOLBAS project](https://lolbas-project.github.io/)
- [LOLDrivers](https://www.loldrivers.io/)
- Public blog posts and research by the DFIR community
- Splunk's own Security Essentials content

If you recognize a query pattern that deserves credit, please open an issue or PR.

---

## 🤝 Contributing

PRs welcome. Good contributions:

- New detection queries with a short description of what they catch
- Corrections to existing queries (false positives, syntax bugs)
- New attack chains with MITRE mapping
- Notes on environment-specific gotchas

When submitting a query, please include:
- What it detects (one sentence)
- Expected Splunk TA / sourcetype
- Any known false positive sources

---

## 📄 License

[MIT License](LICENSE) — see the LICENSE file for details.

You're free to use, modify, and distribute this — including commercially — as long as you include the copyright notice.

---

## 🙋 Questions / Feedback

Open an issue, or reach me on LinkedIn: [Payam Samimi](https://www.linkedin.com/in/payam-samimi/)
