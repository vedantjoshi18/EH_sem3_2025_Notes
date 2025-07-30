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
