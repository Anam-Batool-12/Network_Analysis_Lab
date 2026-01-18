LAB 6 – SUSPICIOUS TRAFFIC ANALYSIS REPORT

Date: 16-01-2026  
Environment: Kali Linux  
Tools Used: tcpdump, Wireshark, Nmap  
Capture File: lab6_traffic.pcap  

Objective:
To capture live network traffic, analyze multiple types of activities, and identify potentially suspicious behavior.

Activities Performed During Capture:

1. DNS lookup to example.com  
2. ICMP ping to google.com  
3. Nmap SYN scan against scanme.nmap.org  
4. Manual TCP connection using telnet  

Analysis Summary:

DNS Analysis:
- Multiple DNS query packets observed.
- Legitimate domain resolution traffic was identified.
- No abnormal DNS behavior detected.

ICMP Traffic:
- ICMP echo requests and replies detected.
- Normal ping activity confirmed.

Suspicious Activity Detected:

Using the filter:

tcp.flags.syn == 1 && tcp.flags.ack == 0

A large number of SYN packets were identified with the following pattern:

- Single source IP  
- Single destination IP  
- Multiple different destination ports  
- High frequency in short time  

This pattern is strongly indicative of a port scanning attempt.

Findings:

The captured traffic contains both normal and suspicious activity:

Normal:
- DNS lookups  
- ICMP pings  
- Standard TCP connection  

Suspicious:
- Nmap SYN scan behavior
- Reconnaissance style traffic pattern

SOC Conclusion:

The analysis confirms that:

- Network monitoring tools like Wireshark can clearly identify reconnaissance attempts.
- SYN scan activity is easily distinguishable from legitimate traffic.
- Such behavior should trigger alerts in SIEM or IDS systems.

Recommendations:

- Implement IDS rules to detect high-volume SYN packets.
- Monitor repeated connection attempts to multiple ports.
- Enable logging for early reconnaissance detection.

Learning Outcome:

- Gained hands-on experience analyzing real network captures.
- Learned to differentiate normal vs malicious traffic.
- Practiced professional SOC reporting skills.
