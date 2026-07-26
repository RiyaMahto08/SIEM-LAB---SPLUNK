# Week 5 - Day 4: SOC Investigation Playbooks

## Objective

Create standardized Security Operations Center (SOC) investigation playbooks for common Windows authentication and account management alerts. These playbooks provide analysts with a structured process to investigate, validate, and respond to security incidents.

---

# Overview

SOC investigation playbooks ensure every security alert is handled consistently and efficiently. Each playbook defines the investigation workflow from initial alert triage to incident recovery.

---

# Playbook 1 – Multiple Failed Login

## Purpose

Investigate repeated failed authentication attempts that may indicate password guessing or unauthorized access attempts.

**Severity:** Medium

### Investigation Steps

1. Review failed login events (Event ID 4625).
2. Identify the affected user account.
3. Check the number and timing of failed attempts.
4. Determine whether a successful login followed.
5. Verify user activity with the account owner.

### Evidence Collection

- Event ID 4625 logs
- Username
- Computer Name
- Timestamp
- Logon Type

### Containment

- Monitor the affected account.
- Reset the password if suspicious activity is confirmed.

### Escalation

Escalate if repeated failures originate from multiple systems or continue over an extended period.

### Recovery

- Confirm legitimate user access.
- Continue monitoring for additional failed logins.

---

# Playbook 2 – Brute Force Attack

## Purpose

Detect repeated authentication attempts targeting user accounts.

**Severity:** High

### Investigation Steps

1. Review Event ID 4625 logs.
2. Identify targeted accounts.
3. Determine attack frequency.
4. Look for successful logins after failures.
5. Investigate source systems.

### Evidence Collection

- Event ID 4625
- Failed login count
- Target account
- Login timestamps

### Containment

- Lock or disable affected accounts if necessary.
- Reset passwords.
- Block malicious source if identified.

### Escalation

Escalate immediately if multiple accounts are targeted.

### Recovery

Continue monitoring until attack activity stops.

---

# Playbook 3 – Successful Login After Failed Logins

## Purpose

Identify successful authentication following multiple failed login attempts.

**Severity:** High

### Investigation Steps

1. Review Event IDs 4625 and 4624.
2. Verify login timeline.
3. Determine whether the login was legitimate.
4. Review account activity after login.

### Evidence Collection

- Event ID 4625
- Event ID 4624
- Username
- Login timestamps
- Computer Name

### Containment

- Reset account password if compromise is suspected.
- Monitor account activity.

### Escalation

Escalate if login behavior appears abnormal.

### Recovery

Verify user identity and continue monitoring.

---

# Playbook 4 – Account Lockout

## Purpose

Investigate Windows account lockout events.

**Severity:** Medium

### Investigation Steps

1. Review Event ID 4740.
2. Identify affected account.
3. Determine the cause of the lockout.
4. Check for repeated failed logins.

### Evidence Collection

- Event ID 4740
- Username
- Lockout timestamp
- Computer Name

### Containment

- Unlock the account after verification.
- Reset password if necessary.

### Escalation

Escalate if repeated lockouts occur.

### Recovery

Monitor the account for recurring activity.

---

# Playbook 5 – New User Account Creation

## Purpose

Investigate newly created Windows user accounts.

**Severity:** High

### Investigation Steps

1. Review Event ID 4720.
2. Identify who created the account.
3. Verify whether account creation was authorized.
4. Review assigned permissions.

### Evidence Collection

- Event ID 4720
- Username
- Creator account
- Timestamp

### Containment

Disable unauthorized accounts immediately.

### Escalation

Escalate unauthorized account creation to security management.

### Recovery

Remove unauthorized accounts and review audit logs.

---

# Playbook 6 – Administrator Group Changes

## Purpose

Investigate modifications to privileged local administrator groups.

**Severity:** High

### Investigation Steps

1. Review Event ID 4732.
2. Identify the user added to the group.
3. Verify administrator approval.
4. Review related account activity.

### Evidence Collection

- Event ID 4732
- Username
- Group Name
- Timestamp

### Containment

Remove unauthorized users from privileged groups.

### Escalation

Escalate unauthorized privilege assignments immediately.

### Recovery

Restore approved group membership and monitor future changes.

---

# Summary

| Detection | Event ID | Severity |
|-----------|---------:|----------|
| Multiple Failed Login | 4625 | Medium |
| Brute Force Attack | 4625 | High |
| Successful Login After Failed Logins | 4624 / 4625 | High |
| Account Lockout | 4740 | Medium |
| New User Creation | 4720 | High |
| Administrator Group Changes | 4732 | High |

---

# Deliverables

- ✅ Six SOC Investigation Playbooks
- ✅ Investigation Procedures
- ✅ Evidence Collection Guidelines
- ✅ Containment and Recovery Steps
- ✅ Documentation

---

# Skills Learned

- SOC Incident Response
- Alert Investigation
- Windows Security Event Analysis
- Incident Triage
- Evidence Collection
- Containment Procedures
- Escalation Process
- Recovery Planning
