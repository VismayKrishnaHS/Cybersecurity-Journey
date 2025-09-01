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

## 🔍 Nmap Scanning & Enumeration

### Overview
- Practiced host discovery, port scanning, and service enumeration.
- Learned differences between TCP, UDP, and stealth-based scans.
- Covered multiple scanning options for detection evasion and in-depth analysis.

### Commands Practiced
- `nmap -p <port>` — Scan specific port  
- `nmap -p- <target>` — Scan all ports (1–65535)  
- `nmap scanme.nmap.org` — Public test scan  
- `nmap -sn <target>` — Ping scan (host discovery)  
- `nmap -Pn <target>` — Skip host discovery  
- `nmap -sS <target>` — SYN (stealth) scan  
- `nmap -sT <target>` — TCP connect scan  
- `nmap -sU <target>` — UDP scan  
- `nmap -sN <target>` — Null scan  
- `nmap -sX <target>` — Xmas scan  
- `nmap -sF <target>` — FIN scan  
- `nmap -F <target>` — Fast scan (common ports)  
- `nmap -sV <target>` — Service/version detection  
- `nmap --traceroute <target>` — Trace route  
- `nmap -o <file>` — Output to file  
- `nmap -sC <target>` — Default scripts  
- `nmap --script <script>` — Specific NSE script  
- `nmap -A <target>` — Aggressive scan  
- `nmap -A --script <script>` — Aggressive + script  
- `nmap --script vuln <target>` — Vulnerability scan  
- `nmap > <file>` — Save output  
- `nmap -oN <file>` — Normal output  
- `nmap -oA <basename>` — All output formats  
- `nmap -oX <file>` — XML output  
- `nmap -oS <file>` — Script kiddie output  
- `nmap -oG <file>` — Grepable output  
- `nmap -v <target>` — Verbose mode  
- `nmap -vv <target>` — Extra verbose mode  

### Key Learnings
- SYN scan is faster and stealthier than TCP connect.
- Null, Xmas, and FIN scans can bypass some firewalls.
- Version detection and NSE scripts help deeper enumeration.
- Aggressive mode gives full detail but increases detection risk.
- Output formats are important for saving results for reporting.

---
## Progress Update

### Linux Command Learning – Continued

Today, I learned and practiced additional Linux networking, scanning, and exploitation commands to expand my penetration testing skills.

- Learned `sudo arp-scan -l` to detect devices on the local network using ARP requests.
- Practiced multiple Nmap output formats:
  - `nmap -oN` (Normal output)
  - `nmap -oA` (All formats: Normal, XML, Grepable)
  - `nmap -oX` (XML output)
  - `nmap -oS` (Script kiddie style output)
  - `nmap -oG` (Grepable output)
- Used verbosity flags:
  - `-v` for verbose output
  - `-vv` for very verbose output
- Reviewed `wc -` for counting words, lines, and characters in output.
- Practiced Nmap options:
  - `-p` to specify ports
  - `-P` for ping scan
  - `-t4` for faster timing
  - `-s` to define scan type
- Tested remote access using `ssh`.
- Learned web and directory scanning tools:
  - `dirb` for discovering hidden web directories
  - `gobuster` for brute forcing directories, files, and DNS subdomains
  - `ffuf` for web fuzzing
- Used `sudo apt-get` for package management.
- Explored exploitation tools:
  - `msfconsole` for launching the Metasploit Framework
  - `wp-info` to gather WordPress site information
  - `getuid` in Metasploit to identify current user privileges.




_This log is continuously updated as part of my training at **Red Team Hacker Academy** and personal self-directed lab work._
