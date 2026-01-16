LAB 2 – TCP HANDSHAKE ANALYSIS

Date: 16-01-2026  
Environment: Kali Linux on VMware  
Tool Used: tcpdump  
Interface: eth0  

Command Executed:
sudo tcpdump -i eth0 tcp -c 20

Objective:
To capture and analyze TCP handshake process and observe real network connection behavior.

Findings:

The capture contained two types of behavior:

1. Failed Connection Attempts

Initial packets showed repeated SYN packets such as:

Flags [S]

This indicates:

- Client attempted to connect to a remote HTTP server.
- No SYN-ACK response was received.
- TCP kept retransmitting SYN packets.
- Connection was not established.

This demonstrates how failed or blocked connections appear in packet captures.

2. Successful TCP Handshake

Later in the capture, a complete handshake was observed:

Step 1:
Flags [S]  
Client → Server (SYN)

Step 2:
Flags [S.]  
Server → Client (SYN-ACK)

Step 3:
Flags [.]  
Client → Server (ACK)

This confirms that a proper TCP session was established with a Google HTTPS server.

Post Handshake Activity:

Packets with Flags [P.] were observed, which represent PUSH packets containing actual data transfer over the established connection.

Key Learning Points:

- TCP handshake consists of SYN, SYN-ACK, ACK.
- Multiple SYN packets without SYN-ACK indicate failed connections.
- Successful connections are followed by data packets with PUSH and ACK flags.
- tcpdump is a powerful tool for low-level network troubleshooting.

SOC Analyst Relevance:

- Ability to recognize incomplete handshakes helps detect:
  - Network misconfigurations  
  - Firewall blocking  
  - Possible scanning activity  
  - Denial of Service attempts  

This lab demonstrates practical understanding of TCP behavior from a security monitoring perspective.
