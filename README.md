<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/banner-dark.png" />
    <img src="assets/banner-light.png" alt="Rahul Shrivastava — Security Operations Engineer" width="100%" />
  </picture>
</p>

<p align="center">
  🛡️ <b>SOC (L2)</b> · 🚨 <b>Incident Response</b> · ⚙️ <b>Security Automation</b> · 🤖 <b>AI-assisted triage with guardrails</b>
</p>

<p align="center"><i>🤖 AI assists. 🧠 Humans decide. 🔗 Everything is logged.</i></p>

<p align="center">
  <a href="https://www.rahulshrivastava.co.in"><img src="https://img.shields.io/badge/Website-rahulshrivastava.co.in-0B1426?style=flat-square&logo=googlechrome&logoColor=22D3EE" alt="Website"></a>
  <a href="https://www.linkedin.com/in/shriv-rahul/"><img src="https://img.shields.io/badge/LinkedIn-shriv--rahul-0A66C2?style=flat-square&logo=linkedin&logoColor=white" alt="LinkedIn"></a>
  <a href="mailto:shrivastava.rahul97@gmail.com"><img src="https://img.shields.io/badge/Email-shrivastava.rahul97%40gmail.com-D14836?style=flat-square&logo=gmail&logoColor=white" alt="Email"></a>
  <img src="https://img.shields.io/badge/Status-Open%20to%20SecOps%20roles%20·%20Immediate%20joiner-34D399?style=flat-square" alt="Open to work">
</p>

---

### 👨‍💻 `$ whoami`

```yaml
# rahul.yaml — policy-as-code, applied to a career
name:        Rahul Shrivastava
role:        Security Operations Engineer
experience:  "3+ years — SOC L2 @ WellMark Technology · freelance IR, SOC monitoring & VAPT"
operates:    [Splunk, Microsoft Sentinel, Google Chronicle, Defender XDR, Splunk SOAR, Palo Alto XSOAR]
builds:      "Python automation that makes SOCs faster — and auditable"
principles:
  - signal_over_noise        # tune with context, never by muting coverage
  - recommend_before_act     # automation proposes; policy gates what executes
  - evidence_or_it_didnt_happen
frameworks:  [MITRE ATT&CK, NIST CSF 2.0, NIST SP 800-61, ISO 27001, SOC 2, CIS Controls]
open_to:     [Security Operations Engineer, SOC Analyst, Information Security Engineer]
```

---

### 📈 Impact in production — numbers, not adjectives

| | Outcome | How |
|---|---|---|
| 🔇 | **False-positive rate ↓ 20–40%** | Correlation + refined triage criteria across three SIEMs |
| ⏱️ | **MTTR improved up to 25%** | Streamlined escalation workflows, firewall/VPN fixes |
| 🚨 | **50–100 alerts/day** triaged | Splunk · Google Chronicle · Microsoft Sentinel |
| 🖥️ | **200+ endpoints** hardened & monitored | Microsoft Defender · Fortinet · Sophos |
| 🔎 | **4–10 incident reports & RCAs / month** | Root cause, not just closure |
| 🧪 | **16–30 freelance engagements** | Pentests, SOC monitoring, IR — FMCG, e-commerce, Web3 |
| 📊 | **500+ weekly alerts analysed → ~60% FPs** | Turned into alert-handling playbooks |

---

### 🕹️ Live &amp; interactive — click and try

| | Project | |
|---|---|---|
| 🎯 | **[AI Red-Team Playground](https://github.com/CdxDebian/AI-Redteam-Playground)** — break an AI agent in your browser; a provenance-aware gate decides every tool call live, mapped to MITRE ATLAS &amp; OWASP LLM. | [**▶ Live demo**](https://cdxdebian.github.io/AI-Redteam-Playground/) |
| 🧭 | **[SOC Field Manual](https://github.com/CdxDebian/SOC-Field-Manual)** — a searchable analyst reference: event IDs, KQL/SPL, ATT&CK, IR steps, India cyber clocks. | [**▶ Live demo**](https://cdxdebian.github.io/SOC-Field-Manual/) |
| 🛡️ | **[AgentGate](https://github.com/CdxDebian/AgentGate)** — the tested Python guardrail behind the playground; CI red-team gate drives attack success **54% → 0%**. | `code` |
| 📓 | **[IR-Playbooks](https://github.com/CdxDebian/IR-Playbooks)** — 10 scenario playbooks mapped to MITRE ATT&CK, ATLAS &amp; OWASP LLM. | `code` |

---

### 🚀 Featured builds

#### 🛡️ [SOC Incident Orchestrator](https://github.com/CdxDebian/SOC-Incident-Orchestrator) — AI-assisted incident response pipeline
Ingests security telemetry, correlates it into incidents, scores risk *with its reasons*, and lets an LLM summarise — while a policy layer decides what may actually happen.

```mermaid
flowchart LR
    A[Telemetry<br/>untrusted] --> B[Normalise &<br/>dedupe]
    B --> C[Correlate<br/>host · user · IOC · time]
    C --> D[TI enrichment<br/>timeouts + fallback]
    D --> E[Explainable<br/>risk score]
    E --> F[LLM summary<br/>evidence boundary]
    F --> G{Policy-as-code}
    G -->|ALLOW| H[Idempotent ticket]
    G -->|REQUIRE_APPROVAL| I[Human approval] --> H
    G -->|BLOCK| J[Rejected]
    H --> K[(Hash-chained<br/>audit trail)]
    J --> K
```

- 💉 **Prompt-injection defence:** telemetry is treated as data, never instructions; schema validation, confidence thresholds, retry/fallback
- 🧩 **Explainability:** every score persists its contributing factors; behaviour mapped to MITRE ATT&CK with evidence
- 🔗 **Audit-ready:** tamper-evident hash chain with secret redaction; compliance-evidence mapping to SOC 2, ISO 27001, NIST CSF
- 🐳 **Shipped like software:** Docker / docker-compose, pytest adversarial suite (injection, malformed input, policy correctness, idempotency), threat model

`Python` `FastAPI` `Pydantic` `SQLite` `Ollama` `Docker` `pytest` `MITRE ATT&CK`

#### 🤖 [AI-SOC Alert Triage](https://github.com/CdxDebian/AI-SOC-Alert-Triage) — dual-signal, advisory-only triage
A local LLM and a deterministic rule engine score every alert independently. **Disagreement is surfaced, not averaged away.**

```mermaid
flowchart LR
    A[Alert] --> B[Rule engine<br/>deterministic]
    A --> C[Local LLM<br/>Llama 3.2 3B]
    B --> D{Agree?}
    C --> D
    D -->|yes| E[Advisory verdict]
    D -->|no| F[Disagreement flagged]
    E --> G[HUMAN_REVIEW_REQUIRED]
    F --> G
```

- 📦 Structured JSON: severity, ATT&CK mapping, plain-English summary, next action, confidence
- 🚫 **Never auto-blocks or remediates** · all inference local — no alert data leaves the host
- 📊 Streamlit review dashboard + CLI

`Python` `Ollama` `Streamlit` `MITRE ATT&CK`

---

### 🧭 How I build security tooling — my engineering creed

| Principle | In practice |
|---|---|
| 🕵️ **Telemetry is untrusted input** | Attackers write the logs you parse — delimit, validate, never execute |
| 🧾 **Explain every score** | A verdict without reasons can't be audited or tuned |
| 🔁 **Idempotent by default** | Retries must never double-ticket or double-act |
| ✋ **Humans own irreversible actions** | Isolation, blocks and disables pass an approval gate |
| 🪂 **Degrade gracefully** | A dead TI feed should slow enrichment, not stop response |
| 🔒 **Tamper-evident by design** | If a regulator asks "who decided?", the log answers |

---

### 🧰 Arsenal

🔭 **SIEM & Detection**
![Splunk](https://img.shields.io/badge/Splunk-000000?style=flat-square&logo=splunk&logoColor=white)
![Microsoft Sentinel](https://img.shields.io/badge/Microsoft%20Sentinel-0078D4?style=flat-square&logo=microsoftazure&logoColor=white)
![Google Chronicle](https://img.shields.io/badge/Google%20Chronicle-4285F4?style=flat-square&logo=google&logoColor=white)
![MITRE ATT&CK](https://img.shields.io/badge/MITRE%20ATT%26CK-C8102E?style=flat-square)

🖥️ **Endpoint & Network**
![Defender XDR](https://img.shields.io/badge/Defender%20XDR-0078D4?style=flat-square&logo=microsoft&logoColor=white)
![Fortinet](https://img.shields.io/badge/Fortinet-EE3124?style=flat-square&logo=fortinet&logoColor=white)
![Sophos](https://img.shields.io/badge/Sophos-005BC8?style=flat-square)
![Wireshark](https://img.shields.io/badge/Wireshark-1679A7?style=flat-square&logo=wireshark&logoColor=white)

⚙️ **SOAR & Threat Intel**
![Splunk SOAR](https://img.shields.io/badge/Splunk%20SOAR-000000?style=flat-square&logo=splunk&logoColor=white)
![Palo Alto XSOAR](https://img.shields.io/badge/Palo%20Alto%20XSOAR-FA582D?style=flat-square&logo=paloaltonetworks&logoColor=white)
![Shuffle](https://img.shields.io/badge/Shuffle-F86A3E?style=flat-square)
![MISP](https://img.shields.io/badge/MISP-1B3D6D?style=flat-square)
![VirusTotal](https://img.shields.io/badge/VirusTotal-394EFF?style=flat-square&logo=virustotal&logoColor=white)

🗡️ **Offensive & Vulnerability**
![Nmap](https://img.shields.io/badge/Nmap-4682B4?style=flat-square)
![Metasploit](https://img.shields.io/badge/Metasploit-2596CD?style=flat-square&logo=metasploit&logoColor=white)
![Burp Suite](https://img.shields.io/badge/Burp%20Suite-FF6633?style=flat-square&logo=burpsuite&logoColor=white)
![Nessus](https://img.shields.io/badge/Nessus-00C176?style=flat-square&logo=tenable&logoColor=white)
![Qualys](https://img.shields.io/badge/Qualys-ED2E26?style=flat-square&logo=qualys&logoColor=white)

🧑‍💻 **Engineering**
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![Pydantic](https://img.shields.io/badge/Pydantic-E92063?style=flat-square&logo=pydantic&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![pytest](https://img.shields.io/badge/pytest-0A9EDC?style=flat-square&logo=pytest&logoColor=white)
![Ollama](https://img.shields.io/badge/Ollama-000000?style=flat-square&logo=ollama&logoColor=white)
![Bash](https://img.shields.io/badge/Bash-4EAA25?style=flat-square&logo=gnubash&logoColor=white)

---

### 🎓 Certifications

✅ **Completed** — Google Cybersecurity Professional Certificate (v2) · Google AI Professional Certificate · Google Generative AI Leader · Google IT Support Professional Certificate · EC-Council Information Security Fundamentals · IBM Cybersecurity Roles, Processes & OS Security

⏳ **In progress** — ![SC-200](https://img.shields.io/badge/Microsoft%20SC--200-Feb%202027-lightgrey?style=flat-square&logo=microsoft) ![Security+](https://img.shields.io/badge/CompTIA%20Security%2B-Mar%202027-lightgrey?style=flat-square)

### 🏆 Hackathons
🥇 Winner — All India Hackathon 2022 (RPA) · 🥈 Runner-up — Vadodara Smart Hackathon 2020 (IoT) · Semi-finalist — All India Hackathon 2021 (DDoS protection)

---

### 🔭 On the roadmap
- 🧪 **Detection-as-code** — KQL/SPL detections mapped to ATT&CK, each with test data and a documented false-positive profile
- 📁 **Control-evidence automation** — scheduled control checks mapped to ISO 27001 / NIST CSF, packaged as hash-verified audit evidence

---

### 🎯 Currently
- 📚 Studying for **Microsoft SC-200** and **CompTIA Security+**
- 🔬 Hardening my builds with adversarial tests and evaluation data
- 💼 Open to **Security Operations / SOC / Information Security Engineer** roles — ⚡ immediate joiner

---

<p align="center">
  <sub>🧾 Every alert closed with a reason. 🔎 Every incident ends with a root cause.</sub><br/>
  <a href="https://www.rahulshrivastava.co.in">rahulshrivastava.co.in</a> ·
  <a href="https://www.linkedin.com/in/shriv-rahul/">LinkedIn</a> ·
  <a href="https://github.com/CdxDebian">GitHub</a>
</p>

