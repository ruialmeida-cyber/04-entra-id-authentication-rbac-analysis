# Microsoft Entra ID Identity Lifecycle & Authentication Validation (Evidence-Based IAM Lab)

## Overview
This project simulates and analyses an end-to-end identity lifecycle within Microsoft Entra ID, focusing on authentication behaviour, group-based access control (RBAC), and directory-level identity operations.

The objective is to interpret identity behaviour using exported Entra ID Audit Logs and Sign-In Logs, applying structured IAM analysis principles commonly used in cloud security and SOC environments.

---

## Scope
This lab focuses on:

- Identity provisioning and group membership changes (RBAC)
- Authentication success, failure, and session behaviour
- MFA enforcement and token-based authentication patterns
- Separation of directory-level vs authentication-level telemetry

No SIEM, API ingestion, or live portal monitoring was used. All analysis is based on exported CSV logs.

---

## Evidence Structure

The repository is organised as follows:

```
Evidence/
├── Repo4_EntraID_AuditLogs_2026-05-07.csv
├── Repo4_EntraID_SignInLogs_2026-05-07.csv
```

- **Audit Logs** → Identity and directory operations (group membership, user management)
- **Sign-In Logs** → Authentication events (logins, failures, session handling)

---

## Key Observations (High-Level)

### Identity & RBAC Activity
- Security group membership changes observed (removal and re-addition of a user)
- Demonstrates dynamic identity state modification within Entra ID

### Authentication Behaviour
- Failed authentication due to invalid credentials
- Session interruption due to “Keep me signed in” flow
- Successful authentication events across later sessions

### MFA & Session Handling
- MFA satisfied via token-based claims
- Session persistence observed through token reuse mechanisms

---

## Security Assessment Summary
No indicators of compromise were identified.

Observed behaviour aligns with:
- normal user authentication errors
- expected session lifecycle handling
- standard RBAC administrative operations in a test environment

No evidence of:
- credential stuffing
- token abuse
- anomalous geographic sign-ins
- malicious identity activity

---

## IAM Interpretation
This dataset demonstrates that identity activity in Microsoft Entra ID operates across two distinct layers:

- **Directory layer (Audit Logs)** → identity and access state changes
- **Authentication layer (Sign-In Logs)** → login validation and session lifecycle

Correct IAM analysis requires separation of these layers.

---

## Skills Demonstrated
- Microsoft Entra ID identity lifecycle analysis
- RBAC and group-based access control interpretation
- Authentication log analysis (success, failure, interruption)
- MFA and session behaviour understanding
- Structured IAM reasoning aligned with SOC workflows

---

## Related Evidence Files
- `/Evidence/Repo4_EntraID_AuditLogs_2026-05-07.csv`
- `/Evidence/Repo4_EntraID_SignInLogs_2026-05-07.csv`

---

## Next Improvements (Planned)
- Add formal detection hypotheses (SOC-style reasoning)
- Map events to MITRE ATT&CK techniques
- Introduce Microsoft Sentinel / KQL queries
- Expand into full IAM incident case study format
