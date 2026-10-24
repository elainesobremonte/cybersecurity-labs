# Lab 5: Windows Process Investigation

## Objective
To practice basic Windows process investigation by reviewing running processes, checking a program's file location and digital signature, and inspecting startup applications for potentially suspicious activity.

## Tools Used
- Windows 11 Task Manager
- Windows File Properties
- Digital Signatures tab

## Investigation Steps and Observations

### 1. Review System Resource Usage
I opened Task Manager and observed Microsoft Edge using approximately 40% CPU and 85% memory at the time of inspection. Both values changed over time.

**Finding:** Memory usage was relatively high, indicating possible memory pressure on the system. Resource usage can fluctuate depending on open applications and background tasks. These readings alone do not establish malicious activity.

### 2. Identify the Edge Process
I located `msedge.exe` in Task Manager's Details tab and observed multiple entries.

**Finding:** Microsoft Edge commonly uses multiple processes for tabs, extensions, and other browser components. Multiple `msedge.exe` entries are not inherently suspicious.

### 3. Inspect the File Location
I used the Open file location option for `msedge.exe`. The file was located in a Microsoft Edge installation folder under Program Files or Program Files (x86).

**Finding:** This location is consistent with a typical Windows application installation. File location is useful evidence, but it does not independently prove that a process is safe.

### 4. Verify the Digital Signature
I opened the file's Properties window and reviewed its Digital Signatures tab.

- **Signer:** Microsoft Corporation
- **Signature status:** This digital signature is OK

**Finding:** Windows reported that the digital signature was valid and identified Microsoft Corporation as the signer. This supports the file's authenticity, although it does not independently establish that every process or activity involving the application is harmless.

### 5. Review Startup Applications
I inspected startup applications in Task Manager and recorded the following:

- **Application:** Microsoft Teams (`ms teams`)
- **Status:** Enabled
- **Startup impact:** Not measured or None

**Finding:** Microsoft Teams is configured to start automatically when the user signs in. The application name and enabled status do not, by themselves, indicate suspicious persistence. The startup impact reading does not determine whether an application is safe or unsafe.

## Initial Assessment
The observations collected during this exercise did not confirm a malicious process.

The multiple Microsoft Edge processes, typical installation location, and valid digital signature were consistent with normal application behavior. The high memory usage warrants monitoring, particularly on a system with limited RAM, but additional evidence would be needed to identify its cause.

The Microsoft Teams startup entry also appeared consistent with a normal startup configuration. No application was classified as malicious based solely on the observations in this lab.

## Recommended Investigation Steps
If further investigation were necessary, I would:

1. Review resource usage over time and identify which processes consume the most CPU and memory.
2. Investigate unfamiliar processes by checking their file paths, publisher information, and digital signatures.
3. Review unfamiliar startup entries before making any changes.
4. Correlate suspicious process activity with relevant Windows security events and other available evidence.
5. Avoid terminating processes or disabling startup applications until their purpose and potential impact are understood.

## Limitations
This was a basic manual inspection using built-in Windows tools. No dedicated endpoint detection tool, malware scanner, or forensic analysis was used as part of this exercise. The findings are limited to the observations collected and do not prove that the system is completely free of malware.

## Conclusion
This lab provided practical experience in reviewing Windows processes, checking application locations and digital signatures, and examining startup applications. It reinforced the importance of validating multiple pieces of evidence before classifying activity as suspicious or malicious.
