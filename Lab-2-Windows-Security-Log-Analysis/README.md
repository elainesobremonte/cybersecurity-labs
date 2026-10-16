# Lab 2: Windows Security Log Analysis

## Overview

This lab involved reviewing Windows Security logs using Windows Event Viewer to identify and analyze successful and failed logon events. The exercise focused on understanding Windows event IDs, logon types, authentication failure reasons, and event timestamps.

**Objective:** Practice basic Windows log analysis and develop an evidence-based approach to reviewing authentication activity.

## Tools Used

- Windows 11
- Windows Event Viewer
- Windows Security Logs

## Key Findings

| Event ID | Event Type | Key Observation |
|---|---|---|
| 4624 | Successful Logon | A service-type logon (Logon Type 5) was recorded at 4:35:13 PM. |
| 4625 | Failed Logon | An interactive logon (Logon Type 2) failed at 3:36:05 PM because of an unknown username or incorrect password. |

**Event timeline:** The failed logon occurred 59 minutes and 8 seconds before the successful service-type logon.

The events were analyzed independently because their different logon types and the available evidence did not establish a direct relationship between them.

## Security Assessment

One failed interactive logon and one successful service-type logon were identified during the review. The available evidence was insufficient to determine whether malicious activity occurred.

The exercise emphasized the importance of reviewing event context, timestamps, account information, and related activity before classifying an event as suspicious.

## Skills Practiced

- Navigating Windows Event Viewer
- Identifying Windows Security Event IDs 4624 and 4625
- Interpreting logon types and authentication failure reasons
- Comparing event timestamps
- Documenting findings and investigation limitations
- Applying evidence-based security analysis

## Repository Contents

- [`report.md`](report.md) — Full lab report, methodology, event analysis, security assessment, and conclusion.
- [`evidence/`](evidence/) — Screenshots of the selected Windows Security events.

## Limitations

This was a basic log-analysis exercise using selected events from a personal Windows system. The events were not independently validated against additional logs or system activity, and no conclusion of malicious activity was made.

## Conclusion

This lab provided practical experience reviewing Windows authentication events and interpreting system logs. It reinforced the importance of understanding event details and correlating evidence carefully before drawing security conclusions.
