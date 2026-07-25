# Week 5 - Day 2: Threat Hunting

## Objective

Perform proactive threat hunting in Splunk by searching Windows Security logs for suspicious authentication and account management activities instead of relying only on alerts.

---

# Overview

Threat hunting is the process of proactively searching historical logs to identify suspicious behavior that may not have triggered automated alerts.

During this lab, four threat hunting queries were created and executed against Windows Security Event Logs.

---

# Threat Hunt 1 – Brute Force Detection

### Objective

Identify user accounts experiencing multiple failed login attempts that may indicate a brute-force attack.

### SPL Query

```spl
index=main EventCode=4625
| stats count by Account_Name
| where count > 5
```

### Expected Result

Display accounts with more than five failed login attempts.

### Analyst Notes

- Multiple failed authentication attempts were observed.
- This activity may indicate password guessing or repeated incorrect password entries.
- Further investigation should include login source, timestamps, and user validation.

### Screenshot

<img width="1920" height="1020" alt="day2-1" src="https://github.com/user-attachments/assets/2deaa100-c063-4583-9288-d808b447312d" />


---

# Threat Hunt 2 – Recently Created User Accounts

### Objective

Identify newly created local user accounts.

### SPL Query

```spl
index=main EventCode=4720
```

### Expected Result

Display all user account creation events.

### Analyst Notes

- User account creation events were successfully detected.
- Verify whether newly created accounts were authorized by administrators.
- Unexpected account creation should be investigated immediately.

### Screenshot

<img width="1920" height="1020" alt="day2-2" src="https://github.com/user-attachments/assets/6524265e-0b7a-4ec5-843d-7d3b99e1b92f" />


---

# Threat Hunt 3 – Administrator Group Changes

### Objective

Detect users added to privileged local groups.

### SPL Query

```spl
index=main EventCode=4732
```

### Expected Result

Display security group membership changes.

### Analyst Notes

- Administrator group modification events were successfully identified.
- Privilege changes should always be validated against approved administrative activities.
- Unauthorized privilege escalation may indicate malicious behavior.

### Screenshot

<img width="1920" height="1020" alt="day2-3" src="https://github.com/user-attachments/assets/6e988053-bacf-4d28-8cfe-4ee72a77911d" />


---

# Threat Hunt 4 – Privileged Logons

### Objective

Identify logons that received special administrative privileges.

### SPL Query

```spl
index=main EventCode=4672
```

### Expected Result

Display privileged logon events.

### Analyst Notes

- Privileged logon events were successfully collected.
- These events are common for administrator accounts but should still be monitored.
- Unexpected privileged logons outside business hours may require investigation.

### Screenshot

<img width="1920" height="1020" alt="day2-4" src="https://github.com/user-attachments/assets/6fdef896-c214-45c8-a7db-0f52824e9896" />


---

# Deliverables

- ✅ Threat Hunting Guide
- ✅ Four Threat Hunting Queries
- ✅ Screenshots
- ✅ Threat Hunting Documentation

---

# Skills Learned

- Threat Hunting Methodology
- Windows Security Event Analysis
- SPL Query Development
- Windows Authentication Monitoring
- Windows Account Management Monitoring
- Detection Engineering

## Completed ✅
