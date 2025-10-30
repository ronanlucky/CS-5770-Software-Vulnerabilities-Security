\# Assignment 1: Network Forensics \& Packet Analysis



\*\*Category:\*\* Network Security | Digital Forensics  

\*\*Status:\*\* ✅ Completed  

\*\*Date:\*\* October 2025



---



\## Challenge Overview



Investigated a security incident where an attacker compromised a web application and deployed network sniffers to capture traffic. Conducted forensic analysis on approximately 22MB of captured network traffic (pcap file) to identify compromised credentials, sensitive data, and security vulnerabilities.



\*\*Objectives:\*\*

\- Perform network reconnaissance using Nmap

\- Analyze packet captures to extract sensitive information

\- Identify cleartext protocol vulnerabilities

\- Extract media files from network streams

\- Discover compromised credentials and passwords



---



\## Vulnerabilities Discovered



\- Cleartext Protocol Exposure - HTTP, IMAP, POP3 transmitting data without encryption

\- Credential Leakage - Passwords transmitted in plaintext over network

\- Wireless Security Weaknesses - WiFi passwords exposed in network traffic

\- Information Disclosure - Sensitive data visible to passive network monitoring

\- Authentication Bypass - Credential sniffing enabling unauthorized access



---



\## Tools Used



\*\*Wireshark\*\* - Primary packet analysis tool

\- Display filters for protocol isolation (http, dns, arp)

\- Follow TCP Stream for conversation reconstruction

\- Export Objects → HTTP for media file carving

\- Packet content search for keywords and patterns



\*\*Nmap\*\* - Network reconnaissance

\- Port scanning and service detection

\- Service version enumeration

\- Host discovery and network mapping



\*\*grep\*\* - Command-line pattern matching

\- Credential extraction from exported packet data

\- Keyword searching in large text datasets



---



\## Analysis Process



\### Network Reconnaissance



Used Nmap to map the network environment, identify active services, locate HTTPS/SSH servers, and enumerate running services across hosts.



\### Packet Analysis with Wireshark



Opened 22MB pcap file despite corruption warnings, used Protocol Hierarchy Statistics to understand traffic composition, and applied display filters to systematically analyze protocols.



!\[Wireshark Analysis](screenshots/wireshark-analysis.png)



\### Layer 2 Forensics



Applied arp filter to correlate IP addresses with MAC addresses, enabling device identification and tracking throughout the capture.



\### DNS Traffic Analysis



Isolated DNS queries and responses using dns filter. Identified authoritative DNS server and tracked domain name resolutions, understanding DNS as a reconnaissance vector.



\### HTTP Stream Analysis



\- Applied http filter to isolate web traffic

\- Used Follow TCP Stream to reconstruct complete conversations

\- Located POST requests containing authentication data

\- Extracted credentials from form submissions

\- Identified failed vs. successful login attempts



\### Media File Extraction



Used File → Export Objects → HTTP to carve audio and video files from traffic streams. Analyzed extracted media for embedded secret codes and hidden information.



\### Command-Line Validation



Combined Wireshark GUI analysis with grep pattern matching to identify and extract multiple compromised credentials from cleartext transmissions.



---



\## Key Learnings



\*\*Technical Skills:\*\*

\- Wireshark display filters are essential for isolating relevant traffic in large captures

\- Follow TCP Stream reveals complete conversation context

\- Export Objects feature enables efficient file carving

\- Multi-tool approach combining GUI and CLI provides comprehensive analysis



\*\*Security Insights:\*\*

\- Cleartext protocols expose all transmitted data to network sniffers

\- Even strong application security fails without network-level encryption

\- Passive monitoring requires no active exploitation

\- Single compromised credential enables lateral movement

\- Legacy protocols remain common in production environments



---



\## Defensive Countermeasures



\*\*Network-Level Protections:\*\*

\- Enforce TLS/SSL for all protocols (HTTPS, IMAPS, POP3S, SSH)

\- Implement HSTS (HTTP Strict Transport Security)

\- Use DNS over HTTPS (DoH) to encrypt DNS queries

\- Deploy network segmentation to isolate sensitive systems

\- Implement 802.1X for port-based network access control



\*\*Monitoring \& Detection:\*\*

\- Deploy network IDS/IPS (Snort, Suricata, Zeek)

\- Implement SIEM for centralized log analysis

\- Alert on cleartext credential transmission

\- Monitor for anomalous authentication patterns

\- Conduct regular packet capture audits



\*\*Application Security:\*\*

\- Implement multi-factor authentication (MFA)

\- Apply rate limiting on authentication endpoints

\- Enforce account lockout policies after failed attempts

\- Use secure session management with httpOnly cookies

\- Never log or transmit passwords in cleartext



---



\## Results



\- Questions Solved: 8/8 (100%)

\- Protocols Analyzed: HTTP, HTTPS, SSH, DNS, ARP

\- Files Extracted: Multiple audio/video files

\- Credentials Found: Multiple accounts compromised

\- Time Investment: ~6 hours



---



\## Professional Impact



This assignment developed critical skills for:

\- SOC Analyst: Incident investigation and traffic analysis

\- Penetration Testing: Network reconnaissance techniques

\- Security Engineering: Understanding protocol vulnerabilities

\- Incident Response: Forensic evidence collection



---



\[Back to Course Overview](../README.md)

