# Week 3 - Day 4: Detection Documentation

## Objective

Document the authentication detections created during Week 3 using a standard SOC detection template. This documentation helps analysts understand the purpose of each detection, its severity, investigation process, and expected behavior.

---

# Detection 1 – Multiple Failed Logins

| Section | Description |
|---------|-------------|
| **Detection Name** | Multiple Failed Logins |
| **Objective** | Detect repeated Windows authentication failures that may indicate brute-force attacks. |
| **Windows Event ID** | 4625 |
| **SPL Query** | `index=* EventCode=4625 \| bucket span=5m _time \| stats count by _time Account_Name \| where count>=5` |
| **MITRE ATT&CK** | Credential Access – Brute Force (T1110) |
| **Severity** | Medium |
| **Possible False Positives** | User repeatedly entering an incorrect password, expired passwords, login script failures |
| **Analyst Response** | Verify user activity, review source IP, check login timing, and investigate related authentication events. |

---

# Detection 2 – Successful Windows Logins

| Section | Description |
|---------|-------------|
| **Detection Name** | Successful Windows Logins |
| **Objective** | Monitor successful user authentication events across Windows systems. |
| **Windows Event ID** | 4624 |
| **SPL Query** | `index=* EventCode=4624` |
| **MITRE ATT&CK** | Valid Accounts (T1078) |
| **Severity** | Low |
| **Possible False Positives** | Normal user logins during business hours |
| **Analyst Response** | Verify unusual login times, new devices, remote logins, and compare with normal user activity. |

---

# Detection 3 – Top Users with Failed Logins

| Section | Description |
|---------|-------------|
| **Detection Name** | Top Users with Failed Logins |
| **Objective** | Identify user accounts with the highest number of failed login attempts. |
| **Windows Event ID** | 4625 |
| **SPL Query** | `index=* EventCode=4625 \| stats count by Account_Name \| sort -count` |
| **MITRE ATT&CK** | Credential Access – Brute Force (T1110) |
| **Severity** | Medium |
| **Possible False Positives** | Forgotten passwords, inactive accounts, service account authentication failures |
| **Analyst Response** | Determine whether the account is being targeted, review authentication history, and correlate with successful logins. |

---

# Detection 4 – Failed Logins by Logon Type

| Section | Description |
|---------|-------------|
| **Detection Name** | Failed Logins by Logon Type |
| **Objective** | Analyze failed login attempts based on Windows Logon Type to understand how authentication failures occurred. |
| **Windows Event ID** | 4625 |
| **SPL Query** | `index=* EventCode=4625 \| stats count by Logon_Type` |
| **MITRE ATT&CK** | Credential Access – Brute Force (T1110) |
| **Severity** | Low |
| **Possible False Positives** | Legitimate local or remote authentication failures |
| **Analyst Response** | Review the logon type, identify whether the attempts are local, remote, service, or network logons, and investigate unusual patterns. |

---

# Skills Learned

- Detection Engineering
- Authentication Monitoring
- Windows Security Event Analysis
- MITRE ATT&CK Mapping
- SOC Investigation Workflow
- SPL Documentation
- Detection Tuning

---

# SOC Analyst Insight

Detection documentation is a critical part of SOC operations. Well-documented detections help analysts quickly understand the purpose of an alert, reduce investigation time, improve consistency during incident response, and simplify future maintenance of detection rules.

---

## Status

✅ Completed
