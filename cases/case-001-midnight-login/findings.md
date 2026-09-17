# 🔎 Findings & Severity Assessment — CASE-001

## Case Information

| Field | Value |
|---|---|
| Case ID | CASE-001 |
| Case Name | The Midnight Login |
| Investigation Type | Suspicious Authentication / Possible Data Exposure |
| Assessment Status | Preliminary |
| Human Attribution | Not Established |
| Financial Loss | Not Confirmed |

---

# 🚨 Finding 01 — Unusual Remote Authentication

**Severity:** HIGH  
**Status:** CONFIRMED

### Evidence

A successful remote login for `arjun.mehta` was recorded at:

`2026-09-15 02:13:44`

Source:

`203.0.113.45`

The same source generated two failed login attempts shortly afterward.

### Assessment

The authentication pattern is unusual compared with the user's normal office logins.

### Confidence

**High**

---

# 💰 Finding 02 — Financial Records Modified

**Severity:** HIGH  
**Status:** CONFIRMED

### Evidence

Two financial transactions were modified during suspicious session `SES-88421`.

| Transaction | Previous Value | New Value |
|---|---:|---:|
| TXN-78422 | 185000 | 285000 |
| TXN-78424 | 210000 | 310000 |

### Assessment

Stored financial data was changed during the suspicious remote session.

The evidence confirms data modification, but does not by itself establish who performed the modification or whether money was actually transferred.

### Confidence

**High**

---

# 📂 Finding 03 — Sensitive Finance Files Exported

**Severity:** HIGH  
**Status:** CONFIRMED

### Evidence

The following files were accessed and exported:

- `Vendor_Payment_List.xlsx`
- `Employee_Finance_Data.xlsx`

### Assessment

Sensitive finance-related information was collected during the suspicious session.

### Confidence

**High**

---

# 🌐 Finding 04 — Outbound Data Transfer

**Severity:** HIGH  
**Status:** CONFIRMED

### Evidence

Outbound transfers were recorded from `NOVA-FIN-07` to:

`203.0.113.90`

The transfers occurred shortly after the corresponding file-export events.

### Assessment

The evidence shows outbound transfer activity associated with the suspicious session.

The current evidence does not independently prove what happened to the data after reaching the destination.

### Confidence

**High**

---

# ⚠️ Finding 05 — External Destination Not Identified as Approved

**Severity:** MEDIUM  
**Status:** SUSPICIOUS

### Evidence

Destination:

`203.0.113.90`

Asset mapping does not identify this destination as approved company infrastructure.

### Assessment

The destination requires investigation and validation against authorized infrastructure records.

### Confidence

**Medium**

---

# ❓ Finding 06 — Human Attribution

**Severity:** INFORMATIONAL  
**Status:** UNKNOWN

### Evidence

The account `arjun.mehta` was used during the suspicious session.

However, the evidence does not establish who physically operated the remote device.

### Assessment

Account attribution and human attribution must be treated separately.

### Confidence

**Low / Insufficient Evidence**

---

# ❓ Finding 07 — Actual Financial Loss

**Severity:** INFORMATIONAL  
**Status:** NOT CONFIRMED

### Evidence

Two financial records were modified.

### Assessment

Record modification has been confirmed, but actual financial loss has not been established by the available evidence.

Additional financial reconciliation would be required.

### Confidence

**Insufficient Evidence**

---

# 📊 Severity Summary

| Finding | Severity | Status |
|---|---|---|
| Unusual Remote Authentication | HIGH | Confirmed |
| Financial Records Modified | HIGH | Confirmed |
| Sensitive Files Exported | HIGH | Confirmed |
| Outbound Data Transfer | HIGH | Confirmed |
| Unknown External Destination | MEDIUM | Suspicious |
| Human Attribution | INFORMATIONAL | Unknown |
| Actual Financial Loss | INFORMATIONAL | Not Confirmed |

---

# 🧠 Overall Assessment

The evidence demonstrates a strongly correlated suspicious sequence:

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

The investigation therefore requires incident-response attention.

However, the available evidence does NOT establish:

- The identity of the person operating the remote session
- The exact method by which the account was accessed
- Whether the account was compromised
- Whether the external destination was controlled by an unauthorized party
- Confirmed financial loss

These remain investigation questions.

---

# 🚧 Recommended Investigation Priorities

1. Validate whether `203.0.113.90` is an approved destination.
2. Review authentication and MFA records.
3. Validate the financial record changes with the finance team.
4. Preserve relevant logs and session evidence.
5. Determine whether the exported data was successfully received.
6. Investigate the source and authorization of the remote device.
