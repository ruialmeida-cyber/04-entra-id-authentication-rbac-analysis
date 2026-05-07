# Microsoft Entra ID Identity Lifecycle & Authentication Analysis

## 1. Scope
This analysis is based on exported Microsoft Entra ID Audit Logs and Sign-In Logs collected on 2026-05-07. No SIEM integration, API ingestion, or live portal monitoring was used.

The objective is to interpret identity behaviour across directory operations, authentication events, and session lifecycle activity within Microsoft Entra ID.

---

## 2. Methodology
The dataset was analysed by:

- Filtering events by timestamp and user principal identity
- Separating directory-level events (Audit Logs)
- Separating authentication-level events (Sign-In Logs)
- Mapping identity actions across lifecycle stages:
  - access modification
  - authentication attempts
  - session continuity behaviour

This separation is essential for accurate IAM interpretation.

---

## 3. Identity Lifecycle Observations

### 3.1 Group Membership (RBAC Activity)
Audit logs show:

- Removal of a user from a security group
- Re-addition of the same user shortly after

This indicates dynamic RBAC state changes within Entra ID.

Interpretation:
- Access control is not static
- Group membership directly influences effective permissions
- Identity state can be modified in real time

---

### 3.2 Directory-Level Identity Activity
Additional audit telemetry shows:

- Self-service group queries and property retrieval events
- Group metadata access operations

These represent standard identity directory interactions and administrative visibility into group structure.

---

## 4. Authentication Behaviour Analysis

Sign-in logs show multiple authentication states for the same identity.

### 4.1 Failed Authentication Event
- Result: Failure
- Reason: Invalid username or password

Interpretation:
- Credential validation failed at authentication layer
- Consistent with user input error patterns rather than compromise

---

### 4.2 Session Interruption Event
- Trigger: “Keep me signed in” flow interruption
- Result: Authentication flow paused and resumed

Interpretation:
- Represents normal session lifecycle behaviour in Entra ID
- Not a security failure, but a session continuity mechanism

---

### 4.3 Successful Authentication Events
- Multiple successful sign-ins observed
- Authentication completed successfully
- Token issuance confirmed

Interpretation:
- Valid identity verification
- Session established with successful authentication claims

---

## 5. MFA and Session Behaviour

- MFA requirement is reported as satisfied via token-based claims
- No evidence of repeated interactive MFA prompts for each authentication event

Interpretation:
- Session-based authentication persistence is in effect
- Token reuse is part of normal Entra ID authentication flow

---

## 6. Separation of IAM Layers

This dataset clearly demonstrates two distinct identity planes:

### Directory Layer (Audit Logs)
- Group membership changes
- Identity and access state modifications
- Administrative and self-service group operations

### Authentication Layer (Sign-In Logs)
- Login attempts (success/failure)
- Session lifecycle events
- MFA validation and token issuance

Correct IAM analysis requires strict separation of these layers.

---

## 7. Security Assessment

No indicators of compromise were identified.

Observed behaviour is consistent with:
- normal credential entry errors
- expected session management behaviour
- standard RBAC operations in a test environment

No evidence of:
- credential stuffing
- token abuse
- anomalous geographic access
- malicious identity behaviour

---

## 8. Key Insights

- Identity state in Entra ID is dynamic and mutable via group membership
- Authentication flows are multi-state rather than linear
- Session handling and token reuse significantly influence observed sign-in behaviour
- Audit and Sign-In logs must be analysed together for complete IAM understanding

---

## 9. Conclusion

This analysis demonstrates structured identity lifecycle interpretation within Microsoft Entra ID, including RBAC activity, authentication behaviour, and session lifecycle evaluation.

The dataset confirms expected IAM behaviour with no security anomalies detected.

---

## 10. Skills Demonstrated

- Microsoft Entra ID identity lifecycle analysis
- RBAC and group-based access control interpretation
- Authentication log investigation (failure, success, interruption)
- MFA and session lifecycle understanding
- Structured SOC-style reasoning for IAM environments
