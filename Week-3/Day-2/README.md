# Week 3 - Day 2: Brute Force Detection using Event ID 4625

## Objective

Detect multiple failed login attempts within a short time period using Splunk Enterprise. This helps identify possible brute-force attacks against Windows user accounts.


## Theory

A brute-force attack involves repeatedly attempting different passwords until the correct one is found.

Windows records every failed authentication attempt as **Event ID 4625**.

SOC analysts monitor the frequency of these events to identify suspicious login behavior.


## MITRE ATT&CK

| Technique | ID |
|-----------|----|
| Brute Force | T1110 |


## Event ID

| Event ID | Description |
|----------|-------------|
| 4625 | Failed Logon |


## SPL Query 1 - Detect Multiple Failed Logins

```spl
index=* EventCode=4625
| bucket span=5m _time
| stats count by _time Account_Name
| where count>=5
```

### Explanation

- Searches Windows failed logon events
- Groups events into 5-minute intervals
- Counts failed logins for each account
- Displays accounts with five or more failed attempts


## SPL Query 2 - Visualize Failed Logins

```spl
index=* EventCode=4625
| bucket span=1m _time
| stats count by _time
```

The results are displayed as a line chart to visualize authentication activity over time.


## Lab Demonstration

### Detection Results

<img width="1920" height="1020" alt="week3=d2" src="https://github.com/user-attachments/assets/bf6f30ce-5e1a-4bfa-9e59-f1035ebf20a0" />

### Visualization

<img width="1920" height="1020" alt="week3=day2" src="https://github.com/user-attachments/assets/e0268848-e5ed-4c4b-a551-0edd43c9698e" />

## What I Learned

- Detecting repeated failed login attempts
- Using the bucket command
- Using stats to aggregate events
- Identifying brute-force activity
- Visualizing security events


## SOC Analyst Insight

Multiple failed logon attempts within a short time window may indicate password guessing or brute-force attacks. Detecting this behavior early allows analysts to investigate compromised accounts before successful authentication occurs.


## Status

✅ Completed
