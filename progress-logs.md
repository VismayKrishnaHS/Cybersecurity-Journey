# 🛡️ Cybersecurity Progress Log

This repository documents my ongoing journey into **ethical hacking, penetration testing, and cybersecurity fundamentals**.  
It serves as a structured record of my practical activities, tools explored, and skills developed — with each entry focusing on **what was done, why it was done, and the technical knowledge gained**.

---

## 📂 Progress Overview

### Virtual Lab Setup & OS Deployment
- Installed and configured **VirtualBox** for creating isolated virtual environments.
- Deployed **Kali Linux** as the main penetration testing OS.
  - Configured *Bridged Adapter* networking for realistic LAN interaction.
  - Performed system updates (`apt update && apt upgrade`).
  - Verified core tools (Nmap, Hydra, Burp Suite).
- Installed **Debian Linux** as a vulnerable target machine.
  - Configured SSH, FTP, and Apache HTTP services for testing.
  - Verified service availability using `systemctl status`.

---

### Networking & Remote Access
- Established **SSH connectivity** between Kali and Debian.
- Configured **FTP (vsftpd)** with secure settings (anonymous login disabled).
- Performed **network reconnaissance**:
  - Scanned local devices with `arp-scan`.
  - Analyzed IP addressing & subnet masks.
- Verified running services and open ports with:
  - `netstat -tulnp`
  - `ss -tuln`

---

### Practical Lab Workflows
- Simulated penetration testing process:
  - Enumerated open services on Debian from Kali.
  - Tested SSH logins with valid credentials.
  - Transferred files via FTP.
  - Hosted test HTML pages on Apache for vulnerability scanning.
- Started **TryHackMe** beginner penetration testing rooms to apply networking and Linux skills.

---

## 📌 Skills Strengthened
- Virtual machine deployment & configuration.
- Service setup & security hardening (SSH, FTP, HTTP).
- Remote access in controlled lab environments.
- Network scanning & enumeration.
- Hands-on penetration testing workflows.

---

_This log is continuously updated as part of my training at **Red Team Hacker Academy** and personal self-directed lab work._
