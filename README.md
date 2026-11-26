# SOC-SIEM-Lab

A hands-on Security Operations Center (SOC) investigation lab using synthetic security events, Wazuh/SIEM concepts, detection rules, Python analysis, and analyst-ready incident reports.

> **Recruiter-safe scope:** all data is synthetic or anonymized. This repository is a learning and portfolio project, not a claim of production SOC ownership or a live Wazuh deployment.

## Live project demo

The `docs/` directory is designed for GitHub Pages. After Pages is enabled from the repository settings, the public demo can be shared at:

**https://harishdhake-hd.github.io/SOC-SIEM-Lab/**

## Project goals

- Demonstrate alert triage and incident investigation workflows.
- Convert raw security events into structured indicators and findings.
- Map detections to MITRE ATT&CK techniques.
- Produce concise analyst notes and evidence-based incident reports.
- Practice Python automation for parsing and summarizing SOC data.

## Included material

- Synthetic authentication, firewall, DNS, endpoint, and alert events.
- Detection descriptions and test scenarios.
- Python CLI for log triage and IOC searches.
- Triage timeline and incident templates.
- Wazuh setup guidance.
- Unit tests and GitHub Actions CI.
- Static GitHub Pages demo for recruiters and peers.

## Detection scenarios

| Scenario | ATT&CK technique | Example outcome |
|---|---|---|
| SSH brute force | T1110 - Brute Force | 12 failed logins from one source within 10 minutes |
| Successful login after failures | T1078 - Valid Accounts | Follow failed attempts with successful authentication |
| Port scanning | T1046 - Network Service Discovery | Multiple closed-port connections from one source |
| Suspicious PowerShell | T1059.001 - PowerShell | Encoded or download-oriented command activity |
| DNS tunneling indicators | T1071.004 - DNS | Extremely long subdomains or unusually high DNS volume |

## Repository structure

```text
SOC-SIEM-Lab/
├── docs/                  # GitHub Pages demo
├── detections/            # Detection documentation and examples
├── data/synthetic/        # Safe synthetic event datasets
├── src/                   # Python SOC analysis application
├── reports/incidents/     # Sample investigation reports
├── tests/                 # Unit tests
├── diagrams/              # Architecture and workflow diagrams
├── .github/workflows/     # Automated test workflow
└── README.md
```

## Quick start

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
python -m src.soc_analyzer data/synthetic/auth_events.jsonl
python -m pytest
```

On Windows:

```powershell
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
python -m src.soc_analyzer data\synthetic\auth_events.jsonl
python -m pytest
```

## Investigation method

1. Collect and normalize events.
2. Identify a time window and affected identity or host.
3. Preserve source evidence and raw event context.
4. Correlate authentication, network, endpoint, and DNS signals.
5. Assess severity and confidence separately.
6. Classify the event as benign, suspicious, confirmed malicious, or inconclusive.
7. Document recommended containment and follow-up actions.
8. Record false positives and limitations.

## Ethical use

Use only synthetic data or systems for which you have authorization. Do not test monitoring rules against third-party networks, reuse real employee information, or expose credentials and private infrastructure through public repositories.

## Author

**Harish Dhake** — aspiring SOC Analyst / Security Analyst

- [GitHub](https://github.com/harishdhake-hd)
- [Portfolio](https://portfolio-sooty-eta-9iubrd29jq.vercel.app/)
