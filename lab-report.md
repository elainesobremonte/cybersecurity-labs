# Lab 1: Network Traffic Analysis with Wireshark

**Lab Type:** Beginner SOC Analyst Training  
**Tool:** Wireshark 4.6.9  
**Operating System:** Windows 11  
**Network Interface:** Wi-Fi  
**Activity:** Live network traffic capture and protocol analysis

## 1. Objective

The objective of this lab was to practice basic network traffic analysis using Wireshark. The exercise focused on capturing live network packets, examining DNS queries and TCP communication, interpreting port numbers and TCP flags, and documenting findings using an evidence-based approach.

## 2. Tools and Environment

- **Wireshark 4.6.9:** Used to capture and inspect network packets.
- **Windows 11:** Operating system used for the exercise.
- **Wi-Fi interface:** Network interface selected for packet capture.
- **Web browser:** Used to generate ordinary web traffic by visiting `https://example.com`.
- **PCAPNG file:** Saved packet capture for review.

## 3. Methodology

The following steps were performed:

1. Opened Wireshark and selected the active Wi-Fi interface.
2. Started a live packet capture.
3. Generated web traffic by visiting `https://example.com` and allowed the capture to collect packets.
4. Stopped the capture and saved the captured traffic as a PCAPNG file.
5. Applied the `dns` display filter to examine DNS-related packets.
6. Inspected a DNS query associated with `www.facebook.com` and identified its query type.
7. Applied the `tcp` display filter to examine TCP packets.
8. Inspected TCP source and destination ports and reviewed the TCP flags.
9. Used additional display filters to identify the SYN, SYN-ACK, and ACK packets associated with a TCP connection.
10. Documented the observations and assessed their significance without assuming that the observed traffic was automatically safe or malicious.

## 4. Findings and Observations

### 4.1 DNS Analysis

**Observed values:**

- **DNS query name:** `www.facebook.com`
- **Query type:** A
- **Response observed:** Yes

**Analysis:**

An A record query requests the IPv4 address associated with a domain name. The observed query for `www.facebook.com` is consistent with a request to resolve a hostname.

A DNS response was also observed. However, the response status and returned address were not verified as part of this exercise.

**Assessment:**

The DNS activity is consistent with ordinary hostname resolution. A domain name alone does not establish which application generated the request or whether all related activity is benign.

### 4.2 TCP Port Analysis

**Observed values:**

- **Client-side port:** 64541
- **Remote-side port:** 443
- **Protocol:** TCP

**Analysis:**

Port 443 is commonly associated with HTTPS traffic. Port 64541 falls within the dynamic/private port range of 49152–65535 and can be used as a temporary client-side port.

The source and destination ports were checked against the packet direction to distinguish the client-to-server traffic from the server-to-client response.

**Assessment:**

The observed port arrangement is consistent with a client establishing a TCP connection to an endpoint using port 443. Port numbers alone do not establish whether a connection is legitimate or suspicious.

### 4.3 TCP Three-Way Handshake Analysis

The following three packet types were identified in the capture:

| Stage | Source Port | Destination Port | TCP Flags |
|---|---:|---:|---|
| 1. Connection initiation | 64541 | 443 | SYN |
| 2. Server response | 443 | 64541 | SYN, ACK |
| 3. Client acknowledgment | 64541 | 443 | ACK |

**Analysis:**

The initial SYN packet indicated a connection request from the client-side port to port 443. The SYN-ACK packet represented the remote endpoint's response. The final ACK packet acknowledged that response.

The source ports, destination ports, and TCP flags were inspected to verify the expected packet directions and sequence of events.

**Assessment:**

The three observed packet types and their directions are consistent with the TCP three-way handshake used to establish a TCP connection. This supports the conclusion that the connection-establishment sequence was observed in the capture.

A normal TCP handshake does not guarantee that subsequent application traffic is safe. Further investigation would be necessary if other indicators of suspicious activity were present.

## 5. Overall Security Assessment

Based on the packets examined in this lab, the observed DNS activity and TCP connection-establishment sequence were consistent with routine network communication.

No specific security incident was established from the inspected evidence. However, this was a limited beginner exercise and was not designed to detect every possible threat.

The assessment is limited to the packets and fields examined. It should not be interpreted as confirmation that all captured traffic was benign or that the endpoint was free of compromise.

## 6. Limitations

- The analysis covered a limited live packet capture rather than a comprehensive network investigation.
- The DNS response status and returned IPv4 address were not fully verified.
- The exercise did not involve a controlled malicious-traffic sample.
- No endpoint telemetry, firewall logs, or centralized SIEM data were correlated with the packet capture.
- A successful TCP handshake alone cannot establish the legitimacy of the remote endpoint or application activity.
- The findings apply only to the captured and inspected evidence.

## 7. Conclusion

This lab provided practical experience with Wireshark and fundamental network traffic analysis. The exercise involved capturing live traffic, filtering DNS and TCP packets, examining port numbers and TCP flags, and identifying a sequence consistent with the TCP three-way handshake.

It also reinforced the importance of evidence-based analysis. Rather than labeling traffic as safe or malicious based on a single field, network activity should be interpreted using packet direction, protocol behavior, and relevant context.

These skills provide a foundation for further SOC analyst training in network monitoring, alert investigation, log correlation, and incident documentation.
