# 🔐 Network & System Penetration Testing Lab

<p align="center">
  <strong>Hands-on penetration testing assessment of intentionally vulnerable systems in an isolated virtual lab environment.</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Kali%20Linux-557C94?style=for-the-badge&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Framework-Metasploit-red?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Focus-Penetration%20Testing-blue?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Environment-Isolated%20Lab-success?style=for-the-badge" />
</p>

---

## 📌 Overview

This repository documents a hands-on Network & System Penetration Testing Lab conducted against intentionally vulnerable virtual machines in an isolated and authorized laboratory environment.

The project demonstrates a complete penetration testing workflow, starting with reconnaissance and host discovery and progressing through port scanning, service enumeration, vulnerability identification, credential security testing, SMB assessment, and controlled exploitation.

The laboratory environment consists of Kali Linux as the penetration testing platform and intentionally vulnerable systems including Metasploitable, Windows XP, and Windows 7.

The purpose of this project is to demonstrate practical cybersecurity skills, understand real-world attack techniques, identify security weaknesses, evaluate their potential impact, and develop appropriate remediation recommendations.

> ⚠️ **Ethical Disclaimer:** All activities documented in this repository were performed exclusively against intentionally vulnerable systems within an authorized and isolated laboratory environment for educational purposes.

---

## 🎯 Objectives

The primary objectives of this penetration testing assessment were to:

- Identify active hosts within the laboratory network
- Discover open ports and exposed services
- Perform service and version enumeration
- Identify potential vulnerabilities
- Assess insecure configurations
- Evaluate authentication security
- Perform SMB enumeration and security assessment
- Conduct controlled credential testing
- Validate selected vulnerabilities through exploitation
- Assess the potential impact of identified weaknesses
- Document findings and security risks
- Provide remediation recommendations

---

## 🧪 Laboratory Environment

| System | Role | Purpose |
|---|---|---|
| 🐉 Kali Linux | Attacker | Penetration Testing Platform |
| 🎯 Metasploitable | Target | Intentionally Vulnerable Linux System |
| 🪟 Windows XP | Target | Vulnerable Legacy Windows System |
| 🪟 Windows 7 | Target | Vulnerable Windows System |

All systems were deployed within an isolated virtual laboratory network.

---

## 🏗️ Laboratory Architecture

```text
                         ┌─────────────────────┐
                         │     Kali Linux      │
                         │                     │
                         │  Attacker Machine   │
                         │                     │
                         │  • Nmap             │
                         │  • Metasploit       │
                         │  • Hydra            │
                         │  • SMB Tools        │
                         └──────────┬──────────┘
                                    │
                         Isolated Virtual Network
                                    │
              ┌─────────────────────┼─────────────────────┐
              │                     │                     │
              ▼                     ▼                     ▼
      ┌──────────────┐      ┌──────────────┐      ┌──────────────┐
      │Metasploitable│      │  Windows XP  │      │  Windows 7   │
      │              │      │              │      │              │
      │ Vulnerable   │      │ Vulnerable   │      │ Vulnerable   │
      │ Linux Target │      │ Windows      │      │ Windows      │
      └──────────────┘      └──────────────┘      └──────────────┘
```

---

# 🔍 Penetration Testing Methodology

The assessment followed a structured penetration testing workflow:

```text
Reconnaissance
      ↓
Host Discovery
      ↓
Port Scanning
      ↓
Service Enumeration
      ↓
Vulnerability Assessment
      ↓
Credential Security Testing
      ↓
SMB Enumeration
      ↓
Controlled Exploitation
      ↓
Impact Assessment
      ↓
Reporting & Remediation
```

---

# 🔎 1. Reconnaissance & Host Discovery

The assessment began with network reconnaissance and host discovery.

The objective was to identify active systems within the isolated laboratory network and establish the available attack surface.

Network discovery techniques were used to determine which systems were reachable before conducting further security testing.

---

# 🔌 2. Port Scanning

Nmap was used to identify open TCP/UDP ports and determine which network services were exposed by the target systems.

Example:

```bash
nmap <target-ip>
```

Additional scanning options were used when required for service and operating system identification.

Example:

```bash
nmap -sV -sC -O <target-ip>
```

The resulting port information was used to determine which services required further enumeration.

---

# 🔍 3. Service Enumeration

After identifying open ports, exposed services were enumerated to determine:

- Service names
- Service versions
- Available functionality
- Potential misconfigurations
- Known security weaknesses
- Possible attack vectors

Particular attention was given to services such as FTP and SMB because of their relevance to the vulnerable laboratory systems.

---

# 📂 4. SMB Security Assessment

SMB services were assessed to identify security weaknesses and insecure configurations.

The assessment included:

- SMB service identification
- SMB version detection
- Share enumeration
- Authentication testing
- Configuration analysis
- Identification of known SMB vulnerabilities

The assessment demonstrated the security risks associated with outdated SMB implementations and improperly secured network services.

---

# 🔑 5. Credential Security Testing

Credential security was assessed against intentionally vulnerable laboratory services.

Hydra was used to demonstrate controlled brute-force testing against selected services.

The assessment focused on:

- Weak credentials
- Default credentials
- Password strength
- Authentication weaknesses
- Brute-force resistance

The results demonstrated the importance of strong authentication policies, account protection, and secure password management.

---

# 💥 6. Vulnerability Assessment & Exploitation

Identified vulnerabilities were assessed and selected vulnerabilities were validated through controlled exploitation using the Metasploit Framework.

The project included testing vulnerabilities and weaknesses such as:

## FTP Backdoor

A vulnerable FTP service was identified and assessed.

The vulnerability demonstrated how outdated or compromised services can provide an attacker with unauthorized access to a system.

## MS08-067

The MS08-067 vulnerability was assessed against the vulnerable Windows environment.

This vulnerability demonstrates the significant risk associated with unpatched legacy Windows systems.

## MS17-010 / EternalBlue

The MS17-010 SMB vulnerability was also assessed within the vulnerable laboratory environment.

The vulnerability demonstrates how an unpatched SMB service can potentially allow remote compromise of an affected system.

---

# 📊 Findings Summary

| ID | Finding | Category | Risk |
|---|---|---|---|
| PT-01 | Vulnerable FTP Service | Service Vulnerability | 🔴 High |
| PT-02 | Weak Credentials | Authentication | 🟠 High |
| PT-03 | SMB Misconfiguration | Network Security | 🟠 High |
| PT-04 | MS08-067 | Remote Code Execution | 🔴 Critical |
| PT-05 | MS17-010 / EternalBlue | SMB Vulnerability | 🔴 Critical |
| PT-06 | Exposed Network Services | Attack Surface | 🟡 Medium |

---

# 📈 Risk Assessment

The identified vulnerabilities were evaluated based on their potential impact and the level of access they could provide to an attacker.

| Severity | Description |
|---|---|
| 🔴 Critical | Potential system compromise or remote code execution |
| 🟠 High | Significant unauthorized access or security impact |
| 🟡 Medium | Increased attack surface or information exposure |
| 🟢 Low | Limited security impact |

---

# 🛡️ Remediation Recommendations

## Patch Management

- Apply security updates regularly
- Replace unsupported operating systems
- Maintain current software versions
- Remove vulnerable legacy services

## Authentication

- Enforce strong password policies
- Disable default credentials
- Implement account lockout controls
- Consider multi-factor authentication
- Monitor repeated authentication failures

## Network Security

- Disable unnecessary services
- Restrict exposed ports
- Implement host-based and network firewalls
- Segment critical systems
- Limit access between network segments

## SMB Hardening

- Disable SMBv1 where possible
- Apply current security patches
- Restrict SMB access to trusted systems
- Review share permissions
- Monitor suspicious SMB activity

---

# 🛠️ Tools & Technologies

| Tool / Technology | Purpose |
|---|---|
| 🐉 Kali Linux | Penetration Testing Platform |
| 🔎 Nmap | Network Discovery & Port Scanning |
| 💥 Metasploit Framework | Vulnerability Validation & Exploitation |
| 🔐 Hydra | Credential Security Testing |
| 📂 SMB Tools | SMB Enumeration & Assessment |
| 🖥️ VirtualBox / Virtual Machines | Isolated Laboratory Environment |

---

# 🧠 Skills Demonstrated

Through this project, the following practical cybersecurity skills were demonstrated:

- Network reconnaissance
- Host discovery
- TCP/UDP port scanning
- Service enumeration
- Version detection
- Vulnerability assessment
- SMB enumeration
- Credential security testing
- Brute-force attack simulation
- Metasploit Framework
- Vulnerability validation
- Exploitation in controlled environments
- Security risk assessment
- Security documentation
- Remediation planning
- Penetration testing methodology

---

# 📁 Repository Structure

```text
network-system-penetration-testing-lab/
│
├── README.md
│
├── docs/
│   └── methodology.md
│
├── reports/
│   └── penetration-testing-report.pdf
│
└── screenshots/
    ├── reconnaissance/
    ├── nmap/
    ├── enumeration/
    ├── vulnerabilities/
    └── exploitation/
```

---

# 📸 Evidence & Documentation

The `screenshots/` directory contains selected evidence from the laboratory assessment.

Evidence may include:

- Network discovery results
- Nmap scans
- Service enumeration
- SMB enumeration
- Vulnerability identification
- Metasploit sessions
- Credential testing
- Exploitation results

Screenshots are included to demonstrate the practical execution of the assessment and support the documented findings.

---

# 📄 Reports

The `reports/` directory can contain the final penetration testing report documenting:

- Executive summary
- Assessment scope
- Laboratory architecture
- Testing methodology
- Reconnaissance results
- Enumeration results
- Vulnerability findings
- Exploitation evidence
- Risk assessment
- Remediation recommendations
- Final conclusion


---

# ⚠️ Ethical & Legal Disclaimer

This repository is intended strictly for educational and authorized cybersecurity testing.

All systems assessed during this project were intentionally vulnerable laboratory machines controlled for the purpose of security education and penetration testing practice.

The techniques demonstrated in this repository must only be used against systems for which explicit authorization has been obtained.

Unauthorized scanning, credential attacks, exploitation, or access to computer systems may be illegal.

---

# 👨‍💻 Author

**Mohammed Khalid Abusafieh**

BSc Information Technology — Networking & Security  
Ajman University

### Cybersecurity Interests

- Cybersecurity
- Network Security
- Penetration Testing
- Ethical Hacking
- Vulnerability Assessment
- Security Operations

---

<p align="center">
  <strong>Network & System Penetration Testing Lab</strong>
  <br>
  Built as a hands-on cybersecurity learning and penetration testing project.
</p>