LAB 4 – ICMP / PING ANALYSIS

Date: 16-01-2026  
Environment: Kali Linux on VMware  
Tool Used: Wireshark, ping  
Interface: eth0  
Command Used: ping -c 4 8.8.8.8

Objective:
To observe ICMP echo request and reply packets and understand basic network connectivity.

Observations:

- 4 ICMP Echo Request packets were sent from my machine to 8.8.8.8.
- 4 ICMP Echo Reply packets were received from the server.
- Source and destination IPs are correct.
- Round-trip times (RTT) observed in Wireshark ranged ~15-30 ms.

Interpretation:

- ICMP Echo Request / Reply is used to test connectivity between hosts.
- Successful replies indicate the host is reachable.
- No packet loss observed.

SOC Analyst Relevance:

- Monitoring ICMP traffic helps detect:
  - Host availability  
  - Network issues  
  - ICMP-based scanning or reconnaissance attempts  



