# Lab 4: Phishing Email Analysis

## 1. Objective

Analyze a simulated email for potential phishing indicators, assess the available evidence, and recommend safe investigation and reporting actions.

## 2. Tools and Environment

- **Tools:** Web browser and text editor
- **Environment:** Simulated email scenario
- **Data source:** Fictional email created for cybersecurity training
- **Additional software:** None required

## 3. Simulated Email Overview

**Subject:** Urgent — Account Suspension Notice  
**Sender display name:** IT Support  
**Sender address:** security@accounts-example.net

The email claims that the recipient's account will be suspended due to a security issue. It requests account verification within two hours and includes a verification link.

The email and its indicators are fictional. The domain and URL are examples, not verified malicious infrastructure.

## 4. Potential Phishing Indicators

### Urgent deadline

The two-hour deadline creates pressure to act quickly. Urgency can be used in phishing to discourage careful verification.

### Potential sender-domain mismatch

The sender's domain has not been verified against an organization's legitimate domain. The display name alone does not establish the sender's identity.

### Threat of account suspension

The threat of losing account access may pressure the recipient into following the request without verifying its legitimacy.

### Account-verification link

The email asks the recipient to verify an account through a link. The actual destination and legitimacy of the link have not been established.

### Generic greeting

The email uses “Dear Employee.” This can be a warning sign in context, but generic greetings also appear in legitimate emails.

## 5. Initial Assessment

- **Classification:** Suspicious — further investigation required
- **Confidence:** Moderate
- **Preliminary priority:** Medium for this training scenario
- **Confirmed phishing:** Not established
- **Confirmed account compromise:** Not established

The email contains multiple warning signs. However, the sender's identity, email authentication results, and actual link destination have not been independently verified.

## 6. Recommended Investigation Steps

1. Compare the sender's full address and domain with the organization's verified contact information.
2. If available and authorized, review the email headers and SPF, DKIM, and DMARC authentication results.
3. Inspect the URL as text and examine its destination using approved security tools without directly opening the suspicious link.
4. Check whether the same message was received by other employees.
5. Ask whether the recipient clicked the link or submitted credentials, following the organization's incident-handling procedures.
6. Preserve relevant email details and report the message through the approved security reporting process.

## 7. Recommended User Response

The recipient should not click the link, provide credentials, or reply to the suspicious message. They should report it through the organization's approved process.

If credentials have already been submitted, the recipient should notify the security team immediately and follow the organization's account-protection procedures.

## 8. Limitations

This exercise uses a fictional email. No real email headers, sender reputation data, URL analysis results, or recipient activity were available. Therefore, the findings indicate suspicion rather than confirmed malicious activity.

## 9. Conclusion

The simulated email contains several potential phishing indicators, including urgency, a possible sender-domain mismatch, and a threat of account suspension. These indicators justify further investigation and reporting.

This exercise demonstrates basic phishing triage, evidence-based assessment, safe handling of suspicious links, and security reporting.
