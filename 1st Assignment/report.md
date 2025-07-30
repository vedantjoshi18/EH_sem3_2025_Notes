# 📄 TCP and UDP Port Discovery on scanme.nmap.org

---

## Assignment 1 – Ethical Hacking Semester 3, 2025

**Student Name :** Vedant Joshi  
**Date :** 30/07/2025

---

## 1. Introduction

> The goal of this assignment is to perform **TCP and UDP port discovery** on `scanme.nmap.org` using Nmap, document the steps, findings, and lessons learned. This reinforces skills in network reconnaissance and ethical hacking.

---

## 2. Tools and Environment

| Tool        | Version | Purpose            |
|-------------|---------|--------------------|
| Nmap        | 7.95    | Network scanning   |
| Kali Linux  | 2025    | Running scans      |
| Terminal    | –       | Command execution  |

---

## 3. Methodology

### **A. TCP SYN Scan**
- **Command :** `nmap -sS scanme.nmap.org -oN tcp_results.txt`
- **Purpose :** Stealthy scan to detect open TCP ports.

### **B. UDP Top 100 Scan**
- **Command :** `sudo nmap -sU --top-ports 100 scanme.nmap.org -oN udp_results.txt`
- **Purpose :** Find open UDP services among the 100 most common UDP ports.

---

## 4. Scan Results

### **A. TCP Scan Output**

| Port | State | Service |
|------|-------|---------|
| 22   | open  | ssh     |
| 80   | open  | http    |

### **B. UDP Scan Output**

All 100 scanned ports showed as:  
> `open|filtered` – No response received; Nmap cannot distinguish between open and filtered due to the nature of UDP scanning.

---

## 5. Visual Evidence

**Screenshots:**

| Description              | File Name      |
|--------------------------|---------------|
| TCP Scan Terminal Output | tcp_scan.png  |
| UDP Scan Terminal Output | udp_scan.png  |

---

## 6. TCP VS UDP

### TCP (Transmission Control Protocol):

- Connection-oriented protocol; establishes a handshake before transmitting data.
- Ensures reliable delivery: packets arrive in order and are re-transmitted if lost.
- Commonly used for services like web (HTTP), email (SMTP), and file transfers (FTP).
- Easier to scan for open ports, as TCP responds reliably.

### UDP (User Datagram Protocol):

- Connectionless protocol; sends packets without checking if the receiver is ready or even present.
- No guarantees for order or delivery—packets may arrive out of order or get lost without notice.
- Used for services requiring speed and low overhead, like DNS, VoIP, and streaming.
- Harder to scan: many UDP ports don’t respond to probes, and firewall rules often block or silently drop UDP traffic, resulting in ambiguous scan results (open|filtered).

| Aspect            | TCP                            | UDP                          |
|-------------------|--------------------------------|------------------------------|
| Connection        | Yes (handshake required)        | No (connectionless)          |
| Reliability       | Reliable, order ensured         | Unreliable, no guarantee     |
| Speed             | Slower (more overhead)          | Faster, less overhead        |
| Typical Use Cases | HTTP, SSH, FTP, SMTP, etc.      | DNS, NTP, SNMP, streaming   |
| Scan Detection    | Easier and more accurate        | Difficult, more ambiguous    |
