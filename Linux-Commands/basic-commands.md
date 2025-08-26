# Linux Essentials – Core Commands for Daily Use

These are foundational Linux commands I've learned and practiced. Designed for navigation, file handling, system insights, permissions, and networking.

---

##  Navigation & Listing
- **`ls`** – List files and directories  
- **`ls -l`** – Detailed list (permissions, size, owner, etc.)  
- **`ls -lh`** – Human-readable sizes (KB, MB, GB)  
- **`ls -a`** – Show hidden files  
- **`ls -R`** – Recursive listing  
- **`cd`** – Change directory  
- **`cd ..`** – Go up one level  
- **`pwd`** – Show current directory path  

---

##  File & Directory Management
- **`touch`** – Create empty file  
- **`cat`** – Display file contents  
- **`mkdir`** – Make directory  
- **`rmdir`** – Remove empty directory  
- **`rm`** – Remove file  
- **`rm -r`** – Recursively remove directory  
- **`rm *`** – Delete all files (⚠ Dangerous!)  
- **`cp`** – Copy file/directory  
- **`mv`** – Move or rename  
- **`nano`** – Open file in Nano editor  

---

##  Searching & Viewing
- **`grep`** – Search for a term in a file  
- **`grep -i`** – Case-insensitive search  
- **`head`** – View first lines of file  
- **`tail`** – View last lines of file  

---

##  System Info & Networking
- **`ifconfig`** – Old network configuration tool (deprecated)  
- **`ip a`** – Display IPs and network interfaces  
- **`whoami`** – Show logged-in user  
- **`id`** – Show user/group information  
- **`echo`** – Print text or variables  
- **`echo $SHELL`** – Display current shell  

---

##  Permissions & Admin
- **`chmod`** – Modify file permissions  
- **`su`** – Switch user  
- **`sudo`** – Execute with superuser permissions  
- **`sudo su`** – Become root user  
- **`root`** – Highest privilege user (use with caution)  
- **`alias`** – Create command shortcuts  

---

# 🔍 Nmap – Scanning Essentials

These are the Nmap scanning commands I learned and practiced today, covering different scan types, output formats, and scripting.

---

## 🛠 Scan Types
- `nmap -sS` – TCP SYN (Stealth) Scan  
- `nmap -sT` – TCP Connect Scan  
- `nmap -sU` – UDP Scan  
- `nmap -sN` – TCP Null Scan  
- `nmap -sX` – Xmas Scan  
- `nmap -sF` – FIN Scan  

---

## 🎯 Target & Port Scans
- `nmap -p <ports>` – Scan specific ports  
- `nmap -p- <target>` – Scan all 65,535 ports  
- `nmap scanme.nmap.org` – Example scan on Nmap test host  
- `nmap -sn` – Host discovery (ping scan only)  
- `nmap -Pn` – Skip host discovery (treat all hosts as online)  

---

## 🚀 Speed & Service Detection
- `nmap -F` – Fast scan (common ports only)  
- `nmap -sV` – Detect service versions  
- `nmap --traceroute` – Trace the route to target  

---

## 📜 Scripts & Automation
- `nmap -sC` – Default script scan  
- `nmap --script <script>` – Run a specific NSE script  
- `nmap -A` – Aggressive scan (OS detect, version, scripts, traceroute)  
- `nmap -A --script <script>` – Aggressive scan with chosen script  
- `nmap --script vuln` – Run vulnerability detection scripts  

---

## 💾 Output & Saving
- `nmap > filename` – Save output to file (overwrite)  
- `nmap -oN <file>` – Normal output  
- `nmap -oA <basename>` – Save in all formats (`.nmap`, `.xml`, `.gnmap`)  
- `nmap -oX <file>` – XML output  
- `nmap -oS <file>` – Script kiddie output  
- `nmap -oG <file>` – Grepable output  

---

## 🔊 Verbosity
- `nmap -v` – Increase verbosity  
- `nmap -vv` – Very verbose output  


###  Personal Note
This document is based on my own learning journey, structured and refined with AI for clarity. It’s both a study reference and a showcase-ready asset for my GitHub portfolio.
Added Linux basic commands list
