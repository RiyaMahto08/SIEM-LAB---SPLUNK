# Week 5 - Day 1: Advanced Windows Detections

## Objective

Learn how to detect advanced Windows security events using Splunk Enterprise by monitoring privileged account activities and administrator group changes.

---

# Overview

During this lab, advanced Windows Event IDs were investigated to improve visibility into privileged user activity. The detections were validated using both Splunk Enterprise and Windows Event Viewer.

---

# Detection 1 – Administrator Group Changes

## Event ID

4732

### Objective

Detect when a user is added to a privileged local group.

### Practical

```cmd
net localgroup Administrators TestUser123 /add
```

### SPL Query

```spl
index=main EventCode=4732
```

### Detection Documentation

| Field | Value |
|-------|-------|
| Detection Name | Administrator Group Changes |
| Event ID | 4732 |
| Severity | High |
| MITRE ATT&CK | T1098 – Account Manipulation |
| Possible False Positives | Legitimate administrator activity |
| Analyst Response | Verify whether the privilege assignment was authorized. |

---

### Evidence

#### Splunk Detection

<img width="1920" height="1020" alt="day1-2" src="https://github.com/user-attachments/assets/e596398e-235f-48fb-a18c-f162681d3fc0" />


#### Windows Event Viewer Verification

<img width="1920" height="1020" alt="day1" src="https://github.com/user-attachments/assets/6f41c66e-4129-4d05-aafe-4b0f968fc573" />


---

# Detection 2 – Privileged Logon

## Event ID

4672

### Objective

Detect logons that receive special administrator privileges.

### SPL Query

```spl
index=main EventCode=4672
```

### Detection Documentation

| Field | Value |
|-------|-------|
| Detection Name | Privileged Logon |
| Event ID | 4672 |
| Severity | High |
| MITRE ATT&CK | Privilege Escalation |
| Possible False Positives | Normal administrator login |
| Analyst Response | Review privileged activity and verify the user. |

---

### Evidence

#### Splunk Detection

<img width="1920" height="1020" alt="day1-3" src="https://github.com/user-attachments/assets/b5e2631e-f862-433d-9e40-9449debdc876" />


---

# Detection 3 – Remote Desktop Logon

## Event ID

4624 (Logon Type 10)

### SPL Query

```spl
index=main EventCode=4624 Logon_Type=10
```

### Testing Status

Remote Desktop was **not available** in this home lab environment.

In an enterprise environment, this detection would monitor successful Remote Desktop logins and help identify unauthorized remote access attempts.

---

# Skills Practiced

- Windows Security Monitoring
- Splunk SPL
- Detection Engineering
- Windows Event Analysis
- Privileged Access Monitoring
- MITRE ATT&CK Mapping

---

# Deliverables Completed

- ✅ Advanced Windows detections created
- ✅ SPL queries documented
- ✅ Splunk screenshots attached
- ✅ Windows Event Viewer verification
- ✅ Detection documentation completed

---

## Limitations

The New User Account Creation (Event ID 4720) and Remote Desktop Logon (Event ID 4624 Logon Type 10) detections could not be fully demonstrated due to home lab limitations. Their detection logic and SPL queries have been documented for reference.

---

## Status

✅ Completed
