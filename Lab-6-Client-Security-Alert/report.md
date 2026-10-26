# Lab 6: Security Alert Communication and Triage

## Objective

Practice assessing a suspicious authentication pattern, assigning a preliminary alert priority, and writing a clear security notification with recommended investigation steps.

## Scenario

This exercise uses simulated authentication logs from Lab 3. The events show three consecutive failed login attempts against Maria's account, followed by a successful login.

| Time | Account | Event |
|---|---|---|
| 09:04 | Maria | Failed login |
| 09:05 | Maria | Failed login |
| 09:06 | Maria | Failed login |
| 09:07 | Maria | Successful login |

**Source IP:** `203.0.113.25` — reserved for documentation and examples.

## Initial Assessment

**Alert classification:** Suspicious authentication activity  
**Preliminary priority:** Medium  
**Status:** Requires investigation  
**Affected account:** Maria (simulated account)

### Reasoning

Repeated failed logins followed by a successful login may indicate password guessing or possible account compromise. However, this pattern does not prove that an attacker gained access.

Medium was selected as the preliminary priority because the activity warrants investigation, but the available simulated evidence does not establish unauthorized access, account privileges, or resulting impact. Priority may change as additional evidence becomes available.

## Simulated Security Alert Notification

**Alert ID:** LAB6-001  
**Priority:** Medium (Preliminary)  
**Status:** Requires Investigation  
**Affected Account:** Maria (simulated account)

### Summary

Three consecutive failed login attempts against Maria's account were followed by a successful login one minute later. This pattern may indicate repeated password guessing or another authentication issue that warrants further investigation.

### Potential Risk

If the successful login was unauthorized, the account may have been compromised. The available simulated events do not confirm unauthorized access.

### Recommended Actions

1. Verify with the account owner whether the successful login was legitimate.
2. Review related authentication logs, including timestamps, source information, and any unusual login patterns.
3. Check for additional suspicious activity following the successful login.
4. If unauthorized access is confirmed, follow the organization's incident response procedure, including appropriate account protection and escalation.

### Current Assessment

The activity is suspicious but unconfirmed. Further investigation is required before determining whether an account compromise occurred.

## Investigation and Communication Principles

This exercise reinforced the importance of:

- Communicating observable facts separately from assumptions.
- Assigning a preliminary priority based on available evidence and potential risk.
- Recommending clear, actionable investigation steps.
- Avoiding claims of confirmed compromise without sufficient evidence.
- Escalating findings according to the organization's procedures.

## Limitations

This was a simulated exercise using fictional authentication events. No real account, client, or production security system was investigated, and no notification was sent to a real client. The source IP address is reserved for documentation and examples. The alert priority is an exercise assessment, not a formal severity determination under an organization's policy.

## Conclusion

This exercise provided practice in converting suspicious authentication observations into a structured security alert. It demonstrated how to communicate the event, identify potential risk, assign a preliminary priority, and recommend next steps while clearly acknowledging uncertainty.
