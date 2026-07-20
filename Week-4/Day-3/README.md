
# Week 4 - Day 3: Alert Testing & Investigation

## Objective

Validate that the Splunk detection rules trigger correctly by generating Windows authentication events and investigating them like a SOC analyst.

---

# Lab Activities Performed

The following authentication events were generated on the Windows machine:

- Entered an incorrect password multiple times.
- Logged in successfully.
- Allowed scheduled alerts to execute.
- Verified triggered alerts.

---

# Investigation

## Which alert fired?

The following alerts were successfully triggered:

- ✅ Multiple Failed Login
- ✅ Successful Login After Failed Logins

---

### Multiple Failed Login Alert

<img width="1920" height="1020" alt="week4(5)" src="https://github.com/user-attachments/assets/829ec52e-115d-42c4-a7b6-54c5bfd047f7" />

---

### Successful Login After Failed Logins Alert

<img width="1920" height="1020" alt="week4(day5)" src="https://github.com/user-attachments/assets/bf1d09b5-773b-4f4d-96ab-6816b8a76c17" />


---

## What events were generated?

| Event ID | Description |
|----------|-------------|
| 4625 | Failed Login |
| 4624 | Successful Login |

---

## Which user was involved?

```
RIYAACER$
```

---

## Timeline

| Step | Activity |
|------|----------|
| 1 | Multiple failed login attempts generated |
| 2 | Windows Event ID 4625 created |
| 3 | Splunk indexed the failed login events |
| 4 | Multiple Failed Login alert triggered |
| 5 | Successful login performed |
| 6 | Windows Event ID 4624 generated |
| 7 | Successful Login After Failed Logins alert triggered |

---

## Is it suspicious or a false positive?

This activity is **not malicious**.

Since the events were intentionally generated in a controlled lab environment, this is classified as a **False Positive (Lab Testing)**.

---

# Incident Report

## Incident Summary

Multiple failed Windows authentication attempts followed by a successful login were detected. Splunk successfully generated alerts based on the configured detection rules.

---

## Timeline

- Failed login attempts generated
- Event ID 4625 recorded
- Multiple Failed Login alert triggered
- Successful login recorded
- Event ID 4624 generated
- Successful Login After Failed Logins alert triggered

---

## Evidence

- Screenshot of Multiple Failed Login alert
- Screenshot of Successful Login After Failed Logins alert
- Splunk Alert History
- Windows Security Events

---

## Risk Assessment

**Severity:** Medium

Repeated authentication failures may indicate:

- Brute-force attack
- Password guessing
- Unauthorized access attempt

In this lab, the activity was intentionally generated for testing purposes.

---

## Recommendation

- Verify the user account.
- Review authentication logs.
- Correlate Event IDs 4624 and 4625.
- Monitor repeated authentication failures.
- Investigate source IP if observed in a production environment.

---

# Deliverables Completed

- ✅ Wrong password attempts generated
- ✅ Successful login generated
- ✅ Alerts triggered
- ✅ Alert investigation completed
- ✅ Incident report created

---

## Status

✅ Completed
