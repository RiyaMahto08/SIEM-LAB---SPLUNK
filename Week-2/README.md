# Week 2 - Windows Event Logs & Event ID Analysis

## Objective

Learn how Windows generates security logs and analyze them in Splunk.

## Topics Covered

- Windows Event Viewer
- Windows Security Logs
- Windows Event IDs
- Windows Log Sources
- Searching Windows logs in Splunk
- Basic Event Analysis
- 
## Important Event IDs

| Event ID | Description |
|----------|-------------|
| 4624 | Successful Logon |
| 4625 | Failed Logon |
| 4634 | Logoff |
| 4648 | Logon using Explicit Credentials |
| 4672 | Special Privileges Assigned |
| 4688 | Process Creation |
| 4720 | User Account Created |
| 4726 | User Account Deleted |
| 4740 | Account Locked |

## Basic SPL Queries

```spl
index=main

index=main EventCode=4624

index=main EventCode=4625

index=main
| stats count by EventCode

index=main
| top EventCode
```
## Skills Learned

- Understanding Windows Security Logs
- Identifying important Event IDs
- Searching logs with SPL
- Reading event details
- Basic event analysis
  
## Lab Demonstration

The screenshot below shows Windows Security events successfully indexed into Splunk and demonstrates the analysis of Windows Event Logs.
<img width="1920" height="1020" alt="Screenshot 2026-07-07 113142" src="https://github.com/user-attachments/assets/d84a53ee-627b-4f41-b26f-8c71118dd0d5" />

## Status

✅ Week 2 Completed
