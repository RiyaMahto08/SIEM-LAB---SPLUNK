# Week 5 - Day 3: MITRE ATT&CK Mapping

## Objective

Map Windows Security detections to the MITRE ATT&CK Framework to understand attacker techniques, tactics, and how security detections align with real-world adversary behavior.

---

# Overview

MITRE ATT&CK is a globally recognized knowledge base of adversary tactics and techniques used by cybersecurity professionals for detection engineering, threat hunting, and incident response.

In this lab, previously created Windows Security detections were mapped to their corresponding MITRE ATT&CK techniques and tactics.

---

# Detection Mapping

| Detection | Event ID | MITRE ATT&CK Technique | Technique ID | Tactic |
|------------|---------:|------------------------|--------------|---------|
| Multiple Failed Logins / Brute Force | 4625 | Brute Force | T1110 | Credential Access |
| New User Account Created | 4720 | Create Account | T1136 | Persistence |
| Administrator Group Changes | 4732 | Additional Local or Domain Groups | T1098 | Persistence |
| Privileged Logon | 4672 | Valid Accounts | T1078 | Defense Evasion |
| Account Lockout | 4740 | Brute Force | T1110 | Credential Access |

---

# Detection Matrix

| Event ID | Windows Activity | ATT&CK Technique | ATT&CK ID | Tactic |
|-----------|------------------|------------------|------------|---------|
| 4625 | Failed Login | Brute Force | T1110 | Credential Access |
| 4720 | User Account Created | Create Account | T1136 | Persistence |
| 4732 | User Added to Administrator Group | Additional Local or Domain Groups | T1098 | Persistence |
| 4672 | Special Privileges Assigned to Logon | Valid Accounts | T1078 | Defense Evasion |
| 4740 | Account Lockout | Brute Force | T1110 | Credential Access |

---

# Why MITRE Mapping Matters

Mapping detections to MITRE ATT&CK helps security teams to:

- Standardize detection coverage
- Understand attacker behavior
- Improve threat hunting
- Build detection engineering skills
- Identify security monitoring gaps
- Enhance SOC investigations

---

# Documentation

## Detection Coverage

| Detection | Status |
|------------|--------|
| Brute Force Detection | ✅ Mapped |
| New User Account Detection | ✅ Mapped |
| Administrator Group Change Detection | ✅ Mapped |
| Privileged Logon Detection | ✅ Mapped |
| Account Lockout Detection | ✅ Mapped |

---

# Deliverables

- ✅ MITRE ATT&CK Mapping
- ✅ Detection Matrix
- ✅ Documentation

---

# Skills Learned

- MITRE ATT&CK Framework
- ATT&CK Tactics and Techniques
- Detection Engineering
- Windows Event Mapping
- SOC Documentation
- Threat Intelligence

# Completed ✅

