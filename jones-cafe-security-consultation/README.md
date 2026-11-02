# Security Consultation – Jones Café & Bakery

**Module:** Network and System Security – BSc (Hons) Computing & IT, CCT College Dublin (2026)
**Author:** Silmara Souto

📄 **[Read the full report (PDF)](Jones_Cafe_Security_Consultation_Report.pdf)**

## Overview

A security assessment for a fictional small business, Jones Café & Bakery, before its website went live. The project covered the on-premise network, the web server, and the AWS cloud platform hosting the website. It ended with a practical attack demonstration against a vulnerable lab machine.

## Objectives

- Identify the main security weaknesses in the existing network
- Recommend practical controls for the on-premise network, the web server and the cloud
- Demonstrate reconnaissance techniques against a vulnerable machine in a safe lab

## Key findings

| Risk | Why it matters |
|---|---|
| End-of-life systems (Windows Server 2016, Ubuntu 16.04) | No more security updates, exposed to known exploits such as CVE-2017-0144 (WannaCry) |
| Web server inside the internal network | A compromised website would give an attacker direct access to internal PCs |
| Shared accounts and no security policies | No accountability and a high risk of credential misuse |

## Recommendations

**On-premise network**
- Patch management process and upgrade of end-of-life systems
- Network segmentation with VLANs and a DMZ for the web server
- Firewall rules following the principle of least privilege
- Individual accounts with multi-factor authentication (MFA)
- Switch security and staff security awareness training

**Web server**
- Hardening before going live (removing unused services, secure configuration)

**AWS cloud**
- IAM (least privilege), Security Groups, WAF & Shield (web attacks and DDoS)
- GuardDuty (threat detection), CloudTrail (activity logging), Config (configuration monitoring) and Inspector (vulnerability scanning)

## Lab: reconnaissance with Nmap

Isolated virtual lab with **Kali Linux** (attacker) and **Metasploitable2** (deliberately vulnerable target) on a private network.

| Scan | Command | Purpose |
|---|---|---|
| Basic | `nmap <target>` | Open ports and services |
| Version detection | `nmap -sV <target>` | Service versions, to match against known vulnerabilities |
| OS detection | `nmap -O <target>` | Operating system fingerprinting |
| SYN stealth | `nmap -sS <target>` | Half-open scan that is harder to log |
| Aggressive | `nmap -A <target>` | OS, versions, scripts and traceroute combined |

## Tools and frameworks

Nmap · Kali Linux · Metasploitable2 · AWS (IAM, Security Groups, WAF, Shield, GuardDuty, CloudTrail, Config, Inspector) · VLANs · Firewalls · MFA · PCI-DSS · OWASP Top 10

> ⚠️ All testing was carried out in an isolated lab environment for educational purposes only.
