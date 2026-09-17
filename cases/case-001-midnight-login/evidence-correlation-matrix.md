# 🧩 Evidence Correlation Matrix

## Case Information

| Field | Value |
|---|---|
| Case ID | CASE-001 |
| Case Name | The Midnight Login |
| Investigation Type | Suspicious Authentication / Possible Data Exposure |
| Evidence Status | Correlated |
| Final Attribution | Not Established |

---

## 🔍 Correlation Matrix

| Evidence | Related Evidence | What It Shows | Confidence | Status |
|---|---|---|---|---|
| Remote login from 203.0.113.45 | Session SES-88421 | Remote session started at 02:13 | High | Confirmed |
| Session SES-88421 | Finance activity | Finance application accessed during same session | High | Confirmed |
| Finance activity | Financial audit | Two payment records were modified | High | Confirmed |
| Session SES-88421 | File access logs | Sensitive finance files were accessed and exported | High | Confirmed |
| File exports | Data transfer logs | Exported files were transferred outbound | High | Confirmed |
| Data transfer | Destination mapping | Destination 203.0.113.90 is not identified as approved company infrastructure | Medium | Suspicious |
| Arjun's account | Remote session | Account was used during suspicious activity | High | Confirmed |
| Arjun's identity | Person operating session | Evidence does not establish who was physically operating the device | Low | Unknown |
| Financial changes | Actual financial loss | Record changes were observed, but financial loss is not confirmed | Medium | Unknown |

---

## 🧠 Key Correlations

### 1. Authentication → Session

The unusual remote login and session SES-88421 occurred at the same time and used the same account and source IP.

**Assessment:** Strong correlation.

### 2. Session → Finance Activity

Finance activity occurred inside the same suspicious session window.

**Assessment:** Strong correlation.

### 3. Finance Activity → Financial Changes

Two financial records were modified during the session:

- TXN-78422
- TXN-78424

**Assessment:** Confirmed record modification.

### 4. File Access → Data Transfer

Sensitive finance files were exported and outbound transfers were recorded shortly afterward.

**Assessment:** Strong correlation.

### 5. Account → Human Attribution

The account `arjun.mehta` was used, but this alone does not prove that Arjun personally performed the activity.

**Assessment:** Human attribution remains unresolved.

---

## ⚠️ Important Investigation Distinction

The evidence currently establishes:

**Account activity ≠ confirmed human identity**

and

**Data transfer ≠ confirmed financial loss**

These questions require additional evidence before making a final conclusion.

---

## 🎯 Current Investigative Assessment

The available evidence shows a strongly correlated sequence:

Remote Authentication
↓
Remote Session
↓
Finance Application Access
↓
Financial Record Modification
↓
Sensitive File Export
↓
Outbound Data Transfer
↓
Session Termination

The sequence is suspicious and requires incident-response action.

However, the available evidence does not independently establish:

- Who operated the remote session
- Whether the account was compromised
- Why the financial records were changed
- Whether the transferred data was actually received or used
- Whether confirmed financial loss occurred

---

## 🚧 Remaining Questions

1. Was the Arjun Mehta account compromised?
2. What authentication method was used?
3. Was multi-factor authentication involved?
4. Was the remote device authorized?
5. Was 203.0.113.90 an approved destination?
6. Can the modified financial records be validated?
7. Is there evidence of actual business or financial loss?

---

## 📝 Analyst Note

This matrix is based only on the synthetic evidence contained in CASE-001.

No conclusion should be made beyond what the evidence supports.
