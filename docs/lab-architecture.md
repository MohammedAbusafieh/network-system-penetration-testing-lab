# 🧪 Laboratory Environment

## Overview

The Network & System Penetration Testing Lab was conducted within an isolated virtual laboratory environment designed for cybersecurity training and vulnerability assessment.

The environment consisted of one attacker machine and multiple intentionally vulnerable target systems. The purpose of this setup was to safely perform reconnaissance, vulnerability identification, exploitation testing, and security analysis without affecting real-world systems.

---

# 🏗️ Lab Architecture

The laboratory environment consisted of:

```text
                    ┌─────────────────────┐
                    │     Kali Linux      │
                    │                     │
                    │  Attacker Machine   │
                    │                     │
                    │  - Nmap             │
                    │  - Metasploit       │
                    │  - Hydra            │
                    │  - SMB Tools        │
                    └──────────┬──────────┘
                               │
                    Isolated Virtual Network
                               │
          ┌────────────────────┼────────────────────┐
          │                    │                    │
          ▼                    ▼                    ▼

 ┌────────────────┐   ┌────────────────┐   ┌────────────────┐
 │ Metasploitable │   │  Windows XP    │   │  Windows 7     │
 │                │   │                │   │                │
 │ Linux Target   │   │ Windows Target │   │ Windows Target │
 │ Vulnerable VM  │   │ Vulnerable VM  │   │ Vulnerable VM  │
 └────────────────┘   └────────────────┘   └────────────────┘
```

---

# 💻 Systems and Roles

## 🐉 Kali Linux

### Role

Attacker machine used to perform penetration testing activities.

### Purpose

Kali Linux provided the security testing tools required for:

- Network discovery
- Port scanning
- Service enumeration
- Vulnerability assessment
- Exploitation testing
- Credential testing

### Main Tools Used

- Nmap
- Metasploit Framework
- Hydra
- SMB utilities
- Linux command-line tools

---

# 🎯 Metasploitable

### Role

Intentionally vulnerable Linux target machine.

### Purpose

Used to demonstrate vulnerabilities in outdated services and insecure configurations.

### Tested Services

- FTP
- Telnet
- SSH
- Web services
- Network services

### Security Issues Identified

- vsFTPd 2.3.4 backdoor vulnerability
- Weak credentials
- Insecure service configurations

---

# 🪟 Windows XP

### Role

Legacy vulnerable Windows target machine.

### Purpose

Used to assess security weaknesses associated with outdated Windows systems.

### Tested Vulnerabilities

- MS08-067
- MS17-010 / EternalBlue

### Security Issues Identified

- Missing security patches
- Vulnerable SMB services
- Remote code execution risks

---

# 🪟 Windows 7

### Role

Windows target machine used for security assessment.

### Purpose

Used to analyze SMB security and authentication weaknesses.

### Tested Areas

- SMB services
- Anonymous share access
- Network exposure
- Authentication security

### Security Issues Identified

- SMB misconfiguration
- Weak access controls
- Exposed network shares

---

# 🌐 Network Configuration

The virtual machines were connected using an isolated virtual network.

## Network Characteristics

- Private laboratory environment
- No exposure to external networks
- Controlled communication between attacker and targets
- Safe environment for penetration testing activities

## Network Communication

The Kali Linux attacker machine was able to communicate with all target systems to perform:

- Discovery scans
- Service analysis
- Vulnerability testing
- Exploitation validation

---

# 🛠️ Software and Technologies

| Technology | Purpose |
|---|---|
| Kali Linux | Penetration testing platform |
| Metasploitable | Vulnerable Linux target |
| Windows XP | Legacy Windows target |
| Windows 7 | Windows security assessment target |
| VirtualBox | Virtual machine management |
| Nmap | Network scanning and service detection |
| Metasploit Framework | Vulnerability exploitation |
| Hydra | Credential testing |
| SMB Tools | SMB enumeration and analysis |

---

# ⚠️ Security Disclaimer

All systems used in this laboratory were intentionally vulnerable machines created for educational cybersecurity training.

Testing activities were performed only within an authorized and isolated environment.

The techniques demonstrated in this project should only be used against systems where explicit permission has been provided.

---

# Conclusion

The laboratory environment provided a controlled platform for practicing real-world penetration testing methodologies.

The combination of Kali Linux, vulnerable virtual machines, and security assessment tools allowed practical demonstration of reconnaissance, vulnerability discovery, exploitation, and security analysis.