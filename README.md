# NOEMVEX APEX PREDATOR v3.0
![Python](https://img.shields.io/badge/Python-3.x-blue) ![License](https://img.shields.io/badge/License-MIT-grey) ![Focus](https://img.shields.io/badge/Focus-AD%20Security-yellow) ![Type](https://img.shields.io/badge/Edition-Apex%20Predator-red)

> **"Hunt the Vulnerabilities, Dominate the Directory."**
> The ultimate Active Directory Offensive Suite. Engineered for targeted RPC/SMB exploitation, LAPS password extraction, and executive-level HTML reporting.
> ⚠️ **Disclaimer:** This tool is for educational purposes and authorized security testing only.

---
## About
**NOEMVEX APEX PREDATOR** is designed for the modern Active Directory (AD) environment. Standard scanners create excessive noise and alert the Blue Team. The Apex Engine focuses on high-impact, stealthy misconfigurations and vulnerabilities (such as unsigned SMB and ZeroLogon) using direct RPC bindings and raw LDAP queries. It bridges the gap between deep technical exploitation and C-Level reporting by generating automated, executive-friendly HTML dashboards.

## Capabilities
* **SMB Signing Audit:** Analyzes the Domain Controller for missing SMB signing enforcement, revealing critical NTLM Relay attack paths.
* **ZeroLogon (CVE-2020-1472) Hunter:** Safely probes Netlogon RPC endpoints for exposure without crashing the Domain Controller.
* **LAPS Extraction:** Authenticated LDAP queries to dump Microsoft Local Administrator Password Solution (LAPS) cleartext passwords.
* **Executive Dashboarding:** Automatically compiles findings, vulnerabilities, and looted credentials into a styled HTML report for immediate client delivery.

---
## Usage

### 1. Requirements
Ensure you have Python 3.x installed and root privileges. Install the core dependencies:
pip3 install -r requirements.txt

*Core dependencies include `impacket` for SMB/RPC interactions and `ldap3` for directory querying.*

### 2. Execution
Run the tool using the following command structure. ROOT privileges are required for stable socket creation.

Syntax:
sudo python3 noemvex_apex.py --ip <DC_IP> --domain <DOMAIN_NAME> [--user <USERNAME>]

Example (Unauthenticated Recon):
sudo python3 noemvex_apex.py --ip 192.168.1.100 --domain corp.local

Example (Authenticated LAPS Dump):
sudo python3 noemvex_apex.py --ip 192.168.1.100 --domain corp.local --user svc_account

---
## Output Preview

    ███╗   ██╗ ██████╗ ███████╗███╗   ███╗██╗   ██╗███████╗██╗  ██╗
    ████╗  ██║██╔═══██╗██╔════╝████╗ ████║██║   ██║██╔════╝╚██╗██╔╝
    ██╔██╗ ██║██║   ██║█████╗  ██╔████╔██║██║   ██║█████╗   ╚███╔╝ 
    ██║╚██╗██║██║   ██║██╔══╝  ██║╚██╔╝██║╚██╗ ██╔╝██╔══╝   ██╔██╗ 
    ██║ ╚████║╚██████╔╝███████╗██║ ╚═╝ ██║ ╚████╔╝ ███████╗██╗  ██╗
    ╚═╝  ╚═══╝ ╚═════╝ ╚══════╝╚═╝     ╚═╝  ╚═══╝  ╚══════╝╚═╝  ╚═╝
                   [ NOEMVEX APEX PREDATOR v3.0 ]

    [*] Engaging Target: 192.168.1.100 (corp.local)
    [*] Analyzing SMB Signing (Relay Attack Vector)...
    ┃  [VULN] SMB Signing is NOT required! Target is vulnerable to NTLM Relay.
    [*] Hunting for ZeroLogon (CVE-2020-1472)...
    ┃  [INFO] Netlogon RPC endpoint exposed.
    [*] Attempting LAPS Password Extraction...
    ┃  [LOOT] LAPS Found: WORKSTATION-01 -> P@ssw0rd123!
    [*] Generating Apex Dashboard...
    [√] Dashboard Generated: apex_loot_corp.local_20260410_1530/apex_dashboard.html

---
## ⚠️ Compliance & Ghost Mode
**Regulatory Context:** This tool assists in auditing privileged access management (PAM) and AD hardening, aligning with NIS2 requirements for infrastructure resilience and GDPR access control mandates.

**Ghost Mode:** All commits to this repository are GPG signed and metadata is strictly managed. The author assumes no liability for unauthorized usage.

---
### Developer
**Emre 'noemvex' Sahin**
*Cybersecurity Specialist & Red Team Tool Developer*
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?style=flat&logo=linkedin)](https://www.linkedin.com/in/emresahin-sec) [![GitHub](https://img.shields.io/badge/GitHub-Follow-black?style=flat&logo=github)](https://github.com/noemvex)
