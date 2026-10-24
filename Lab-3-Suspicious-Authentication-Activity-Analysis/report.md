# Lab 3: Suspicious Authentication Activity Analysis

## 1. Objective

Analyze a simulated authentication log sequence to identify suspicious login behavior, assess its potential security implications, and recommend appropriate investigation steps.

## 2. Tools and Data

- **Tools:** Simulated authentication log dataset; manual log review
- **Environment:** Training scenario
- **Data source:** Artificially created events for cybersecurity practice

## 3. Observed Events

| Time | Account | Source IP | Event |
|---|---|---|---|
| 09:04 | maria | 203.0.113.25 | Failed login |
| 09:05 | maria | 203.0.113.25 | Failed login |
| 09:06 | maria | 203.0.113.25 | Failed login |
| 09:07 | maria | 203.0.113.25 | Successful login |

The source address belongs to an IP range reserved for documentation and examples. It is not a real attacker address.

## 4. Findings

Three consecutive failed login attempts were followed by a successful login for the same account, from the same simulated source address.

This sequence is suspicious because repeated authentication failures followed by a success may be consistent with password guessing or unauthorized access. However, the same pattern could also result from a legitimate user entering an incorrect password several times.

## 5. Initial Assessment

- **Finding:** Suspicious authentication pattern
- **Preliminary priority:** Medium, for this training scenario
- **Status:** Requires further investigation
- **Confirmed compromise:** No

The available events are insufficient to determine whether the successful login was authorized.

## 6. Recommended Investigation Steps

1. Verify whether the account owner recognizes the successful login.
2. Review the source IP address, device details, and usual login patterns.
3. Examine surrounding authentication events for additional failed attempts or other affected accounts.
4. Check for related suspicious activity after the successful login.
5. Escalate according to the organization's incident response procedures if unauthorized access remains a concern.

## 7. Limitations

This exercise uses simulated data rather than actual system logs. It does not include device identity, geographic context, account-owner confirmation, or post-login activity. The source IP address is reserved for documentation, so it cannot establish a real-world source or threat actor.

## 8. Conclusion

The repeated failed logins followed by a successful login warrant further investigation. The appropriate response is to validate the activity and gather additional evidence rather than immediately declaring an account compromise.

This exercise demonstrates basic authentication-log analysis, suspicious-pattern identification, preliminary alert triage, and evidence-based reporting.
