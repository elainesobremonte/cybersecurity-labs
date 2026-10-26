# Lab 7: Suricata IDS — Offline PCAP Analysis

## Objective

Use Suricata, an open-source Network Intrusion Detection System (IDS), to analyze a packet capture offline, inspect DNS activity, and review network event logs for potential security indicators.

## Tools and Environment

- Suricata 8.0.7
- Npcap 1.90
- Windows 11
- Wireshark sample capture: `dns.cap`
- Suricata EVE JSON and statistics logs

## Methodology

1. Installed Suricata and Npcap.
2. Created a separate Suricata configuration for the lab.
3. Enabled the available decoder, stream, HTTP, DNS, and TLS event rule files.
4. Validated the configuration.
5. Processed the sample PCAP in offline mode.
6. Examined the EVE JSON event records, fast log, and statistics log.

## Results

The offline analysis produced the following results:

- **Packets processed:** 38
- **Bytes processed:** 3,706
- **UDP flows:** 8
- **DNS transactions:** 38
- **Alert events found in `eve.json`:** 0
- **`fast.log`:** Empty

The DNS event records included queries for:

- `google.com` — TXT record query
- `isc.org` — NS record query
- `_ldap._tcp.dc._msdcs.utelsystems.local` — SRV record query

The sample capture contained historical timestamps from March 30, 2005.

## Analysis

Suricata successfully processed the offline packet capture and generated structured DNS event records in `eve.json`. The statistics log reported 38 decoded packets, 38 DNS transactions, and 8 UDP flows.

No alert events were found in `eve.json`, and `fast.log` remained empty. This indicates that the current run produced no matching alert records under the lab's configuration. It does not establish that the traffic was safe or that Suricata would detect every type of malicious activity.

## Limitations

- The analysis used a historical offline sample rather than live network traffic.
- The configured rule files were limited and did not constitute a comprehensive threat-detection ruleset.
- Suricata reported a missing `threshold.config` file and that `setrlimit` was unavailable. Despite these warnings, it processed the capture and generated event and statistics logs.
- No malicious activity was confirmed during this exercise.

## Conclusion

This lab provided practical experience with Suricata configuration, offline packet capture analysis, DNS event inspection, and log-based investigation. It reinforced the importance of validating security findings against available evidence and recognizing that the absence of alerts does not prove network traffic is benign.

## Evidence

Supporting screenshots are available in the [`Evidence`](Evidence/) folder:

- Suricata version and build information
- Offline PCAP processing results
- DNS event records
- Suricata statistics

Refer to `Evidence/README.md` for a description of each screenshot.
