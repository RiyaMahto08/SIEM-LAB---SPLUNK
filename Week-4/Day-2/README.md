# Week 4 - Day 2: Windows Authentication Monitoring Dashboard

## Objective

Design and develop an interactive Splunk dashboard to monitor Windows authentication events. The dashboard provides real-time visibility into failed logins, successful logins, and targeted user accounts, helping security analysts quickly identify suspicious authentication activity.

---

## Overview

In this lab, a centralized Windows Authentication Monitoring Dashboard was created using Splunk Dashboard Studio. The dashboard visualizes important Windows Security Event Logs to simplify monitoring and investigation.

The dashboard allows SOC analysts to monitor authentication trends, identify targeted user accounts, and detect suspicious login activity from a single interface.

---

## Dashboard Features

### Failed Logins Over Time

- Monitors Windows Event ID **4625**
- Displays authentication failures over time
- Helps identify brute-force attack patterns

---

### Successful Logins Over Time

- Monitors Windows Event ID **4624**
- Displays successful authentication activity
- Helps compare successful logins with failed attempts

---

### Top Targeted User Accounts

- Displays users receiving the highest number of failed login attempts
- Helps identify accounts targeted by attackers

---

## Technologies Used

- Splunk Enterprise
- SPL (Search Processing Language)
- Windows Security Event Logs
- Dashboard Studio

---

## Dashboard Screenshot

<img width="1920" height="1020" alt="week4(3)" src="https://github.com/user-attachments/assets/d7f45b9f-ddb8-47ea-a460-9a089991dca6" />


---

## Skills Learned

- Splunk Dashboard Development
- Dashboard Studio
- Authentication Monitoring
- Data Visualization
- Windows Event Analysis
- SOC Monitoring
- Detection Engineering

---

## SOC Analyst Insight

Dashboards provide analysts with a centralized view of security events. Instead of manually running multiple searches, analysts can quickly identify authentication anomalies, monitor attack trends, and prioritize investigations using visualizations.

---

## Deliverables

- Created Windows Authentication Monitoring Dashboard
- Visualized failed login activity
- Visualized successful login activity
- Displayed top targeted user accounts
- Implemented interactive dashboard with time-range filtering

---

## Status

✅ Completed
