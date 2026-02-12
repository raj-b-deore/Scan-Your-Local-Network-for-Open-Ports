
# Network Port Scanning using Nmap

## Project Overview
This project demonstrates how to perform network reconnaissance by scanning a target system to identify open ports, running services, and potential security risks using **Nmap**. The results help administrators understand exposed services and improve network security.

---

## Objective
- Scan a target host to identify open TCP ports
- Detect running services and versions
- Analyze possible security risks
- Document findings and recommendations

---

## Tools Used
- Nmap (Network Mapper)
- Wireshark (optional packet capture)
- Operating System: Windows / Linux

---

## Target Information
**Target Host:** 10.170.191.101  
**Scan Type:** TCP SYN Scan with Service Detection

---

## Commands Used

Basic SYN Scan: nmap -sS 10.170.191.101
Service Version Detection: nmap -sS -sV 10.170.191.101

Save Scan Output: nmap -sS -sV 10.170.191.101 -oN scan_results.txt

---

## Scan Results

| Port | Service | Status | Description |
|------|--------|--------|------------|
| 135/tcp | MSRPC | Open | Microsoft Remote Procedure Call |
| 139/tcp | NetBIOS-SSN | Open | Windows NetBIOS session service |
| 445/tcp | Microsoft-DS | Open | SMB file sharing service |
| 4343/tcp | UniCall | Open | Application communication service |
| 4449/tcp | PrivateWire | Open | Private communication service |

(Complete output available in `scan_results.txt`)

---

## Security Observations
- Ports **139** and **445** expose SMB services that can be targeted by ransomware and network attacks.
- **Port 135** exposes RPC services that may allow remote enumeration.
- Unknown services on ports **4343** and **4449** should be verified for necessity and secured.
- Open ports increase the attack surface if not properly controlled.

---

## Recommendations
- Close unused ports using firewall rules.
- Disable unnecessary services.
- Apply regular security updates and patches.
- Use strong authentication mechanisms.
- Monitor network activity periodically.

---

## Project Structure
Network-Port-Scan-Project
│
├── README.md
├── scan_results.txt
├── report.pdf
└── screenshots/

---

## Conclusion
Network port scanning helps identify exposed services and potential vulnerabilities. Regular scanning and proper configuration of services significantly improve network security.
