# Wireshark Network Traffic Analysis

## Overview

This project documents a beginner cybersecurity lab focused on network traffic analysis using Wireshark. The exercise involved capturing live network traffic, examining DNS queries, inspecting TCP ports and flags, and verifying a TCP three-way handshake.

## Objectives

- Capture and inspect network packets using Wireshark.
- Identify DNS query types and interpret DNS activity.
- Examine TCP source ports, destination ports, and flags.
- Verify the sequence of a TCP three-way handshake.
- Document findings using evidence-based security analysis.

## Tools and Environment

- **Wireshark:** Version 4.6.9
- **Operating system:** Windows 11
- **Network interface:** Wi-Fi
- **Capture format:** PCAPNG

## Key Findings

- Observed a DNS A-record query for `www.facebook.com`.
- Identified TCP communication involving ports 64541 and 443.
- Verified packets consistent with the TCP three-way handshake: SYN, SYN-ACK, and ACK.
- Practiced distinguishing observed evidence from conclusions that require further investigation.

## Security Assessment

The inspected DNS and TCP packets were consistent with routine network communication. No specific security incident was established from the examined evidence. This limited exercise does not establish that all captured traffic was benign.

## Repository Contents

- `README.md` — Project overview and key findings.
- `lab-report.md` — Full methodology, observations, analysis, limitations, and conclusion.
- `evidence/` — Sanitized screenshots supporting the analysis.

## Skills Practiced

- Network traffic capture and filtering
- DNS packet inspection
- TCP port and flag analysis
- TCP handshake verification
- Technical documentation
- Evidence-based security assessment

## Limitations

This was a beginner lab using a limited packet capture. It did not involve a full incident investigation, endpoint telemetry correlation, or SIEM alert analysis.

## Disclaimer

This project was conducted for educational purposes using ordinary network activity. Findings are limited to the evidence examined in the lab.
