# Cybersecurity Labs Portfolio

Welcome to my cybersecurity learning portfolio. This repository documents hands-on exercises and simulated investigations as I develop foundational skills in network traffic analysis, Windows security monitoring, authentication analysis, phishing investigation, and endpoint process investigation.

## Hands-on Labs

### Lab 1: Network Traffic Analysis with Wireshark

**Objective:** Analyze network traffic to identify DNS activity and examine TCP connection establishment.

**Tools:** Wireshark

**Skills demonstrated:**
- DNS query inspection
- TCP ports and packet flags
- TCP three-way handshake analysis
- Evidence-based network traffic assessment

[View Lab 1 Report](Lab-1-Network-Traffic-Analysis/report.md) | [View Lab 1 Evidence](Lab-1-Network-Traffic-Analysis/evidence/)

### Lab 2: Windows Security Log Analysis

**Objective:** Review Windows Security events to understand successful and failed logon activity.

**Tools:** Windows Event Viewer

**Skills demonstrated:**
- Windows Security Event IDs 4624 and 4625
- Windows logon types
- Authentication failure analysis
- Event timeline review
- Security event documentation

[View Lab 2 Report](Lab-2-Windows-Security-Log-Analysis/report.md) | [View Lab 2 Evidence](Lab-2-Windows-Security-Log-Analysis/evidence/)

### Lab 3: Suspicious Authentication Activity Analysis

**Objective:** Identify and assess potentially suspicious authentication patterns using simulated log data.

**Tools:** Simulated authentication logs and manual analysis

**Skills demonstrated:**
- Authentication log review
- Identification of repeated failed logins followed by a successful login
- Preliminary alert triage
- Evidence-based assessment and reporting

[View Lab 3 Report](Lab-3-Suspicious-Authentication-Activity-Analysis/report.md)

### Lab 4: Phishing Email Analysis

**Objective:** Assess a simulated email for potential phishing indicators and identify safe investigation steps.

**Tools:** Simulated email data and manual analysis

**Skills demonstrated:**
- Sender and email content analysis
- Identification of urgency and account-threat indicators
- Safe URL inspection practices
- Phishing triage and evidence-based reporting

[View Lab 4 Report](Lab-4-Phishing-Email-Analysis/report.md)

### Lab 5: Windows Process Investigation

**Objective:** Inspect Windows processes, review application file locations and digital signatures, and examine startup applications.

**Tools:** Windows 11 Task Manager and File Properties

**Skills demonstrated:**
- Process identification and resource monitoring
- Executable file location inspection
- Digital signature verification
- Startup application review
- Evidence-based endpoint investigation

[View Lab 5 Report](Lab-5-Windows-Process-Investigation/report.md) | [View Lab 5 Evidence](Lab-5-Windows-Process-Investigation/evidence/)

## About This Portfolio

These labs are personal learning exercises designed to strengthen my foundational cybersecurity knowledge and practical investigation skills. Some exercises use simulated data. Findings and conclusions are limited to the evidence collected, and suspicious activity is not treated as confirmed malicious activity without sufficient supporting evidence.

### Lab 6: Security Alert Communication and Triage

**Objective:** Assess simulated suspicious authentication activity and communicate the findings through a structured security alert.

**Skills demonstrated:**
- Authentication alert triage
- Preliminary priority assessment
- Security notification writing
- Risk communication and recommended actions
- Evidence-based reporting

[View Lab 6 Report](Lab-6-Client-Security-Alert/report.md)

### Lab 7: Suricata IDS — Offline PCAP Analysis

**Objective:** Analyze a sample network packet capture using Suricata to inspect DNS activity and review IDS event logs.

**Tools:** Suricata 8.0.7, Npcap 1.90, Windows 11

**Topics Covered:**
- Suricata IDS configuration and validation
- Offline PCAP analysis
- DNS event inspection using EVE JSON logs
- Packet, UDP flow, and DNS transaction statistics
- Alert review and interpretation of IDS findings

**Key Findings:**
- Processed 38 packets totaling 3,706 bytes.
- Observed 8 UDP flows and 38 DNS transactions.
- Examined DNS queries for `google.com`, `isc.org`, and `_ldap._tcp.dc._msdcs.utelsystems.local`.
- No alert events were found in `eve.json`; `fast.log` remained empty.

**Report:** [Lab 7 — Suricata IDS Analysis](Lab-7-Suricata-IDS-Analysis/)

**Evidence:** [View Lab 7 Evidence](Lab-7-Suricata-IDS-Analysis/Evidence/)
