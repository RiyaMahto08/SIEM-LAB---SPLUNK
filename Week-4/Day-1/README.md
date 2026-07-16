# Week 4 - Day 1: Splunk Alert Management

## Objective

Create and manage authentication-based security alerts in Splunk Enterprise to automatically detect suspicious Windows authentication events.

---

## Overview

In this lab, multiple scheduled alerts were created to monitor Windows authentication activity. These alerts help identify suspicious login behavior without requiring analysts to manually execute searches.

The alerts continuously monitor Windows Security Event Logs and trigger whenever the configured conditions are met.

---

## Alerts Created

| Alert Name | Purpose | Event ID |
|------------|---------|---------:|
| Multiple Failed Login | Detect repeated failed login attempts | 4625 |
| Brute Force Detection | Detect possible brute-force attacks | 4625 |
| Successful Login After Failed Logins | Detect successful authentication following multiple failed attempts | 4624 & 4625 |
| Account Lockout Detection | Detect Windows account lockout events | 4740 |

---

## Alert Configuration

The alerts were configured as **Scheduled Alerts** with automatic execution.

Typical configuration included:

- Alert Type: Scheduled
- Trigger Condition: Number of Results > 0
- Action: Add to Triggered Alerts
- Application: Search & Reporting

---

## Alert Details

### Multiple Failed Login

**Objective**

Detect repeated failed login attempts that may indicate brute-force activity.

**Severity**

Medium

**Windows Event ID**

4625

---

### Brute Force Detection

**Objective**

Detect multiple failed authentication attempts within a short period.

**Severity**

High

**Windows Event ID**

4625

---

### Successful Login After Failed Logins

**Objective**

Detect a successful login immediately following multiple failed login attempts.

**Severity**

High

**Windows Event IDs**

4624, 4625

---

### Account Lockout Detection

**Objective**

Detect Windows account lockout events.

**Severity**

High

**Windows Event ID**

4740

---

## Lab Demonstration

### Alert Configuration

<img width="1920" height="1020" alt="week4(1)" src="https://github.com/user-attachments/assets/2256a40b-d17b-4d32-812d-8ac9b18889ba" />


---

### Alerts Dashboard

<img width="1920" height="1020" alt="week4(1)-2" src="https://github.com/user-attachments/assets/35c5e273-d965-4b90-87ea-a36a8a2e5dd3" />


---

## Skills Learned

- Splunk Alert Management
- Scheduled Searches
- Alert Configuration
- Authentication Monitoring
- Windows Security Event Analysis
- Detection Engineering
- SOC Automation

---

## SOC Analyst Insight

Security alerts allow analysts to receive immediate notifications when suspicious authentication activity occurs. Properly configured alerts reduce manual monitoring, improve detection speed, and help prioritize security investigations.

---

## Deliverables

- Created multiple scheduled alerts
- Configured trigger conditions
- Verified alert settings
- Documented authentication detections
- Reviewed all configured alerts

---

## Status

✅ Completed
