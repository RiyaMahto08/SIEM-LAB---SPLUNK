# Week 3 - Day 3: Windows Authentication Dashboard

## Objective

Build a Windows Authentication Dashboard in Splunk Enterprise to monitor authentication activity, identify suspicious login behavior, and visualize failed and successful logins.


## Overview

The dashboard combines multiple SPL searches into a single monitoring interface, providing visibility into Windows authentication events.

It enables analysts to quickly identify:

- Failed login attempts
- Successful logins
- Frequently targeted user accounts
- Failed logins categorized by Logon Type


## Dashboard Panels

### 1. Failed Logins Over Time

Displays the number of failed authentication attempts over time.

**Event ID:** 4625


### 2. Successful Logins Over Time

Displays successful user logins.

**Event ID:** 4624


### 3. Top Users with Failed Logins

Shows the user accounts experiencing the highest number of failed login attempts.

Useful for detecting targeted accounts.


### 4. Failed Logins by Logon Type

Categorizes failed login attempts according to Windows Logon Type.

Useful for understanding how authentication failures occurred.


## Skills Learned

- Dashboard Creation
- Authentication Monitoring
- Data Visualization
- SPL Panel Design
- Security Analytics
- Windows Event Analysis


## SOC Analyst Insight

A centralized authentication dashboard enables SOC analysts to monitor login activity in real time, identify brute-force attempts, detect unusual authentication behavior, and prioritize investigations without running multiple individual searches.


## Dashboard Screenshot

<img width="1920" height="1080" alt="week3-d(3)" src="https://github.com/user-attachments/assets/08c7d5ed-0649-4952-b509-0bdbfb356386" />


## Status

✅ Completed
