LAB 5 – DETECTING NMAP PORT SCAN

Date: 16-01-2026  
Environment: Kali Linux on VMware  
Tools Used: Nmap, Wireshark  
Interface: eth0  

Command Executed:
sudo nmap -sS scanme.nmap.org

Objective:
To simulate a port scan and analyze how such activity appears at packet level for SOC detection.

Procedure:

- Wireshark capture was started on interface eth0.
- An Nmap SYN scan was launched against scanme.nmap.org.
- Traffic was captured and analyzed using filters.

Wireshark Filter Used:

tcp.flags.syn == 1 && tcp.flags.ack == 0

Observations:

- Large number of TCP SYN packets were generated.
- All packets originated from the same source IP (my machine).
- Destination IP remained constant.
- Destination ports were continuously changing.
- No completed handshakes for most ports.

Indicators of Scanning Behavior:

- Rapid sequence of SYN packets  
- Multiple different destination ports  
- Lack of normal traffic patterns  
- Repetitive connection attempts  

SOC Analyst Insight:

This traffic pattern is a classic indicator of reconnaissance activity such as:

- Port scanning  
- Service enumeration  
- Pre-attack information gathering  

In a real SOC environment, this type of activity would trigger alerts in SIEM tools.

Learning Outcome:

- Learned how Nmap scans operate at packet level.
- Practiced detecting suspicious network behavior.
- Understood how to recognize reconnaissance attempts using Wireshark.
