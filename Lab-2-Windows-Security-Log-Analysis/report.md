# Lab 2: Windows Security Log Analysis

## 1. Objective

The objective of this lab was to practice reviewing Windows Security event logs, identifying successful and failed logon events, and interpreting authentication-related activity using Windows Event Viewer.

## 2. Tools Used

- Windows Event Viewer
- Windows Security Logs
- Windows 11

## 3. Methodology

1. Opened Windows Event Viewer.
2. Navigated to **Windows Logs → Security**.
3. Reviewed authentication-related events, focusing on Event IDs 4624 and 4625.
4. Examined the General tab of selected events to identify the event timestamp, logon type, account category, failure reason, process name, and source network address.
5. Compared the timestamps and characteristics of the selected events.
6. Captured screenshots of both events for documentation.

## 4. Findings

### 4.1 Successful Logon — Event ID 4624

**Observed details:**

- Event ID: 4624
- Date: October 16, 2026
- Time: 4:35:13 PM
- Logon Type: 5
- Process Name: `C:\Windows\System32\services.exe`
- Source Network Address: Displayed as a dash (`-`)

**Analysis:**

Event ID 4624 records a successful logon. Logon Type 5 refers to a service logon, which is commonly associated with a service starting or logging on under an account.

The observed process path was `C:\Windows\System32\services.exe`, the standard location of the Windows Service Control Manager executable. The source network address was displayed as a dash, meaning that no source address was recorded in the field.

Although these details are consistent with service-related activity, the process path alone does not establish that the event was legitimate. Further validation would require examining the account context, service activity, and surrounding events.

### 4.2 Failed Logon — Event ID 4625

**Observed details:**

- Event ID: 4625
- Date: October 16, 2026
- Time: 3:36:05 PM
- Logon Type: 2
- Account Category: Another regular Windows account
- Failure Reason: Unknown username or bad password
- Source Network Address: Displayed as a dash (`-`)
- Observed Frequency: One event identified during the review
- User Recognition: Uncertain

**Analysis:**

Event ID 4625 records a failed logon. Logon Type 2 refers to an interactive logon, typically associated with a user signing in locally.

The failure reason indicates that Windows could not authenticate the supplied credentials because the username may not have been recognized or the password may have been incorrect.

Only one matching event was identified during this review. However, the exact circumstances of the attempt could not be confirmed, and it was uncertain whether it corresponded to a sign-in attempt recognized by the user.

A single failed logon does not establish malicious activity. Possible explanations include an incorrect username, a mistyped password, or another ordinary sign-in issue. Further investigation would be necessary to determine whether the event warranted additional attention.

## 5. Event Timeline and Correlation

The selected events occurred in the following order:

| Date | Time | Event | Description |
|---|---|---|---|
| October 16, 2026 | 3:36:05 PM | 4625 | Failed interactive logon |
| October 16, 2026 | 4:35:13 PM | 4624 | Successful service-type logon |

The failed logon occurred **59 minutes and 8 seconds before** the successful service-type logon.

Although both events were recorded in the Windows Security log, their different logon types indicate different authentication contexts. The available evidence does not establish a direct relationship between the two events.

For this reason, the events were analyzed independently rather than treating the successful logon as a consequence of the earlier failed attempt.

## 6. Security Assessment

This investigation demonstrated how Windows Security logs can provide visibility into authentication-related activity.

The review identified one failed interactive logon and one successful service-type logon. The failed event recorded an authentication failure, while the successful event recorded a service logon.

The observed events did not provide sufficient evidence to determine whether malicious activity occurred. The failed attempt could have resulted from an ordinary sign-in error, and the successful service logon would require additional context to verify whether it was expected.

In a security operations workflow, relevant next steps could include:

- Reviewing nearby authentication events for additional context.
- Checking whether other failed logon attempts occurred for the same account.
- Examining the account and service associated with the successful logon.
- Reviewing relevant timestamps, source information, and related system activity.
- Escalating the event only if additional evidence indicates suspicious behavior.

These steps help ensure that security decisions are based on context rather than isolated event IDs.

## 7. Limitations

- The review focused on selected Windows Security events rather than the complete security log.
- The reason and circumstances behind the failed logon could not be independently confirmed.
- The source network address was not recorded in the inspected events.
- The successful service logon was not independently validated against service configuration or related activity.
- No additional evidence established a relationship between the failed and successful logons.
- The analysis was limited to the information available in Event Viewer and the captured screenshots.

## 8. Conclusion

This lab provided practical experience navigating Windows Event Viewer and interpreting successful and failed logon events.

It reinforced the importance of understanding event IDs, logon types, timestamps, and authentication failure reasons when reviewing system activity. Comparing the timestamps helped establish the order of events, while examining the different logon types prevented an unsupported assumption that the events were directly related.

The exercise demonstrated a foundational security-monitoring principle: logs can help identify activity that warrants review, but reliable conclusions require sufficient evidence, context, and careful correlation.

## 9. Evidence

The following screenshots were captured during the lab:

- `event-4624-successful-logon.png` — Selected successful logon event, including its timestamp and service-related details.
- `event-4625-failed-logon.png` — Selected failed logon event, including its timestamp, logon type, and authentication failure reason.

These screenshots support the observations documented in this report.
