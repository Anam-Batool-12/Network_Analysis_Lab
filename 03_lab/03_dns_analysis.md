LAB 3 – DNS ANALYSIS

Date: 16-01-2026  
Environment: Kali Linux on VMware  
Tool Used: Wireshark  
Interface: eth0  
Command Used: nslookup google.com

Objective:
To capture DNS query and response packets and understand how domain names are resolved to IP addresses.

Observations:

- DNS query packet was sent from 192.168.x.x to the configured DNS server.
- The query requested the A record for google.com.
- The DNS server responded with the IP address (e.g., 142.250.190.14).
- Flags observed:
  - QR = 0 (query), QR = 1 (response)
  - RD = 1 (recursion desired)
  - RA = 1 (recursion available)

Interpretation:

- DNS translates domain names into IP addresses.
- This process allows clients to access websites without knowing IP addresses.
- Analysts can monitor DNS traffic to detect suspicious activity such as:
  - Domain generation algorithms (malware)
  - Data exfiltration via DNS
  - Unusual queries to unknown domains
