# Week 4 - Day 4: Detection Tuning

## Objective

Learn how to reduce false positives and improve the quality of Splunk detections by tuning alert rules. Proper tuning helps SOC analysts focus on real threats while minimizing unnecessary alerts.

---

# Overview

Security alerts often generate false positives due to normal user behavior. During this lab, each authentication detection was analyzed to identify:

- Common false positives
- Noise reduction techniques
- Improved detection thresholds
- Accounts that may be excluded
- SOC analyst recommendations

---

# Detection 1: Multiple Failed Login

## Detection Objective

Detect repeated failed Windows authentication attempts.

### Event ID

4625

### Severity

Medium

### Common False Positives

- User mistypes password multiple times.
- Forgotten passwords.
- Keyboard layout or Caps Lock issues.
- Expired passwords.

### Ways to Reduce Noise

- Ignore single failed logins.
- Alert only when multiple failures occur within a short time.
- Correlate with successful login events.

### Better Threshold

- Trigger only when:
  - 5 or more failed logins
  - Within 5 minutes

### Accounts to Exclude

- Service accounts
- Scheduled task accounts
- Known administrator testing accounts

### Analyst Recommendations

- Verify user identity.
- Review login source.
- Check login history.
- Investigate repeated failures from unknown systems.

---

# Detection 2: Brute Force Detection

## Detection Objective

Identify possible brute-force attacks against Windows accounts.

### Event ID

4625

### Severity

High

### Common False Positives

- User repeatedly attempting to remember password.
- Password synchronization issues.
- Automated login scripts.

### Ways to Reduce Noise

- Increase threshold.
- Detect failures from the same source IP.
- Correlate with account lockout events.

### Better Threshold

- 10 or more failed logins
- Within 5 minutes

### Accounts to Exclude

- Service accounts
- Backup accounts
- Monitoring accounts

### Analyst Recommendations

- Investigate source IP.
- Check if multiple users are targeted.
- Block suspicious IP addresses.
- Reset affected account passwords if required.

---

# Detection 3: Successful Login After Failed Logins

## Detection Objective

Detect successful authentication immediately after repeated failed login attempts.

### Event IDs

- 4625
- 4624

### Severity

High

### Common False Positives

- User finally enters the correct password.
- Password manager retry.
- Cached credential updates.

### Ways to Reduce Noise

- Require at least five failed logins before success.
- Correlate login source.
- Ignore trusted administrator workstations.

### Better Threshold

- Five or more failed logins
- Followed by one successful login
- Within five minutes

### Accounts to Exclude

- Service accounts
- Automated maintenance accounts

### Analyst Recommendations

- Verify whether the login was expected.
- Review previous authentication history.
- Check device and source IP.
- Escalate if login originates from an unfamiliar location.

---

# Detection 4: Account Lockout

## Detection Objective

Detect Windows account lockout events.

### Event ID

4740

### Severity

Medium

### Common False Positives

- User repeatedly enters an incorrect password.
- Cached credentials on another device.
- Mobile devices using old passwords.

### Ways to Reduce Noise

- Correlate with Event ID 4625.
- Ignore isolated lockout events.
- Investigate repeated lockouts for the same account.

### Better Threshold

- Alert when multiple lockouts occur within one hour.
- Prioritize privileged accounts.

### Accounts to Exclude

- Test accounts
- Training lab accounts

### Analyst Recommendations

- Unlock account after verification.
- Check source system.
- Investigate repeated lockouts.
- Recommend password reset if compromise is suspected.

---

# Lessons Learned

During this exercise, I learned how detection tuning improves SIEM effectiveness by reducing false positives and improving alert accuracy. Proper thresholds, account exclusions, and event correlation help SOC analysts focus on genuine security incidents instead of unnecessary alerts.

---

# Skills Practiced

- Detection Engineering
- Splunk Alert Tuning
- False Positive Analysis
- Windows Security Monitoring
- SOC Investigation
- MITRE ATT&CK Mapping
- SIEM Optimization

---

# Deliverables Completed

- ✅ Reviewed all detection rules
- ✅ Identified common false positives
- ✅ Documented noise reduction methods
- ✅ Improved alert thresholds
- ✅ Listed accounts to exclude
- ✅ Added SOC analyst recommendations

---

## Status

✅ Completed
