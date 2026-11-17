# Penetration Testing Report — Footprinting & Network Scanning (`W2-PM-FINAL`)

![Program](https://img.shields.io/badge/Program-Networkwalks_Cybersecurity-0F2747)
![Batch](https://img.shields.io/badge/Batch-B082-1E6BB8)
![Modules](https://img.shields.io/badge/Modules-W2--PM1_%7C_W2--PM5-2EA043)
![Status](https://img.shields.io/badge/Phase_1_&_2-Completed-success)

**Author:** Fahad Bin Islam  
**Date:** 17 November 2026  
**Scope:** `networkwalks.com` (Authorized) & Local LAN (`192.168.68.0/24`)

---

## Disclaimer
All reconnaissance and network scanning activities documented in this repository were performed strictly on systems with explicit written authorization (`networkwalks.com`) or personally owned local network infrastructure (`192.168.68.0/24`) for educational and research purposes.

---

## Project Overview
This repository contains the Week 2 practical deliverables for the Networkwalks Cybersecurity program, covering **Phase 1 (Reconnaissance & Footprinting)** and **Phase 2 (Scanning & Network Discovery)**:

* **`W2-PM1` — External Footprinting & Reconnaissance:** Conducted passive and active information gathering against `networkwalks.com` using six Kali Linux utilities (`whois`, `whatweb`, `nslookup`, `curl -I`, `wafw00f`, and `dnsrecon`).
* **`W2-PM5` — Internal Network Discovery:** Performed a Quick Scan (`nmap -T4 -F 192.168.68.110/24`) using Zenmap to map live hosts, MAC addresses, hardware vendors, and open TCP ports across a local `/24` subnet.

---

## Key Findings Summary

| Target / Tool | Key Observation | Risk Level |
| :--- | :--- | :---: |
| **`whatweb`** | Identified Apache server, WordPress `7.1.4`, WP Download Manager `3.3.77`, Bootstrap `7.1.4`, and jQuery `3.7.1` | Medium |
| **`Zenmap` (`192.168.68.110`)** | Detected open Windows RPC/SMB ports: `135/tcp` (`msrpc`), `139/tcp` (`netbios-ssn`), `445/tcp` (`microsoft-ds`) | Medium |
| **`Zenmap` (`192.168.68.1`)** | Detected gateway services `443/tcp` (`https`) and `1900/tcp` (`upnp`) | Medium |
| **`dnsrecon` & `whois`** | DNSSEC is unsigned; recursion enabled on authoritative name servers `ns6135.hostgator.com` & `ns6136.hostgator.com` | Medium |
| **`curl -I`** | Exposed WordPress REST API link headers (`/wp-json/`) and cache headers (`X-nginx-cache`, `X-Endurance-Cache-Level`) | Low |
| **`nslookup` & `wafw00f`** | Resolved domain to `192.232.216.135`; confirmed protection by **ModSecurity (SpiderLabs)** WAF | Low |

---

## Repository Contents
* [`report/`](./report) — Final formatted `.docx` Penetration Testing Report.
* [`evidence/logs/`](./evidence/logs) — Raw terminal outputs from Kali Linux reconnaissance commands.
* [`evidence/screenshots/`](./evidence/screenshots) — Captured terminal and Zenmap GUI evidence.
