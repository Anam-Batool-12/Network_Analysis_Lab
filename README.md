# Network Traffic Analysis Labs

Author: Anam Batool'
Environment: Kali Linux (VMware)  
Tools: tcpdump, Wireshark, Nmap, nslookup, ping  
Focus: SOC / Blue Team Skills  

---

## Overview

This repository contains practical labs focused on capturing and analyzing network traffic to build real-world SOC analyst skills.

---

## Labs Completed

### Lab 1 – TCPDump Basics
- Captured live packets using tcpdump  
- Saved PCAP files for analysis  
- Learned CLI packet filtering  

### Lab 2 – Wireshark Introduction
- Captured traffic on eth0  
- Used filters: tcp, udp, http  
- Analyzed packet details  

### Lab 3 – DNS Analysis
- Captured DNS queries using `nslookup`  
- Filtered traffic with `dns`  
- Observed request/response behavior  

### Lab 4 – ICMP Analysis
- Analyzed ping traffic  
- Used `icmp` filter  
- Observed echo request and reply packets  

### Lab 5 – Nmap Scan Detection
- Performed SYN scan using Nmap  
- Detected scan with filter:  
  `tcp.flags.syn == 1 && tcp.flags.ack == 0`  
- Identified reconnaissance activity  

### Lab 6 – Incident Report
- Combined captured traffic  
- Differentiated normal vs suspicious behavior  
- Created SOC-style analysis report  

---

## Skills Gained

- Packet capture and filtering  
- Protocol analysis (TCP, UDP, ICMP, DNS)  
- Detecting network reconnaissance  
- Writing SOC investigation reports  

---

## Repository Structure

network-analysis-labs/  
├── lab1_tcpdump_basics/  
├── lab2_wireshark_intro/  
├── lab3_dns_analysis/  
├── lab4_icmp_analysis/  
├── lab5_nmap_scan_detection/  
└── lab6_incident_report/  

---

Practical portfolio demonstrating foundational SOC analyst capabilities.
