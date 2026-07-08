# Week 3 - Day 1: Failed Login Detection (Event ID 4625)

## Objective

Detect failed Windows login attempts using Splunk Enterprise and validate the corresponding Windows Security Event Log.


## Theory

Windows records **Event ID 4625** whenever a logon attempt fails. Security teams monitor these events to identify:

- Brute-force attacks
- Password guessing
- Unauthorized login attempts
- Misconfigured authentication


## Event ID

| Event ID | Description |
|----------|-------------|
| 4625 | Failed Logon |


## SPL Query

```spl
index=* EventCode=4625
| table _time Account_Name Logon_Type Source_Network_Address Failure_Reason Status Sub_Status
```

## Query Explanation

This query searches all indexes for Windows Security Event ID **4625** and displays important fields such as:

- Time
- Account Name
- Logon Type
- Source Network Address
- Failure Reason
- Status
- Sub Status

These fields help analysts investigate failed authentication attempts.

## Lab Demonstration


### Windows Event Viewer Verification

The screenshot below confirms that the same failed login event exists in Windows Event Viewer.

<img width="585" height="513" alt="week 3(2)" src="https://github.com/user-attachments/assets/b6d12495-1b96-46da-871b-246f91ec718e" />


### Splunk Detection

The screenshot below shows Event ID 4625 successfully detected in Splunk.

<img width="1920" height="1020" alt="week 3(1)" src="https://github.com/user-attachments/assets/4225d250-cd4b-499b-a153-557d5f2748e5" />


## What I Learned

- Understanding Windows Security Event ID 4625
- Detecting failed login attempts using SPL
- Investigating authentication failures
- Validating SIEM alerts against Windows Event Viewer

## Status

✅ Completed
