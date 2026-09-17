# 🎯 MITRE ATT&CK Mapping — CASE-001

## Case

| Field | Value |
|---|---|
| Case ID | CASE-001 |
| Case Name | The Midnight Login |
| Framework | MITRE ATT&CK Enterprise |
| Mapping Status | Preliminary |
| Attribution | Not Established |

---

## 🔎 Technique Mapping

| Technique ID | Technique | Tactic | Case Evidence | Confidence |
|---|---|---|---|---|
| T1078 | Valid Accounts | Initial Access | `arjun.mehta` account was successfully used during an unusual remote login | High |
| T1133 | External Remote Services | Initial Access | Successful remote access was recorded from an external source | Medium |
| T1005 | Data from Local System | Collection | Sensitive finance files were opened, read and exported | High |
| T1565.001 | Stored Data Manipulation | Impact | Two financial records were modified during the suspicious session | High |

---

## 🧩 T1078 — Valid Accounts

### Evidence

The `arjun.mehta` account successfully authenticated remotely at:

`2026-09-15 02:13:44`

The same account was associated with the suspicious session `SES-88421`.

### Assessment

This is consistent with the ATT&CK concept of **Valid Accounts**, where legitimate account credentials may be abused to access systems.

However, the evidence does **not** establish that the account was compromised.

**Confidence: HIGH**

---

## 🌐 T1133 — External Remote Services

### Evidence

A remote login originated from:

`203.0.113.45`

The session was classified as:

`Remote`

and continued as session:

`SES-88421`

### Assessment

The evidence is consistent with external remote access.

The exact remote technology used (VPN, RDP, VDI, etc.) is not available in the current evidence.

Therefore, this mapping remains **preliminary**.

**Confidence: MEDIUM**

---

## 📂 T1005 — Data from Local System

### Evidence

During the suspicious session:

- `Vendor_Payment_List.xlsx` was opened and read.
- `Vendor_Payment_List.xlsx` was exported.
- `Employee_Finance_Data.xlsx` was opened and read.
- `Employee_Finance_Data.xlsx` was exported.

### Assessment

The observed access and collection of sensitive local files is consistent with **Data from Local System**.

MITRE describes T1005 as searching local system sources for files and sensitive information before potential exfiltration.

**Confidence: HIGH**

---

## 💰 T1565.001 — Stored Data Manipulation

### Evidence

Two financial records were modified:

- `TXN-78422`
  - Old value: 185000
  - New value: 285000

- `TXN-78424`
  - Old value: 210000
  - New value: 310000

### Assessment

The evidence shows modification of stored financial data during the suspicious session.

MITRE's T1565.001 covers manipulation of stored data that can affect business processes and data integrity.

**Confidence: HIGH**

---

# 🚫 Techniques NOT Mapped

The investigation does NOT currently have enough evidence to confidently map:

- Credential Dumping
- Phishing
- Brute Force
- Malware Execution
- Persistence
- Command and Control
- Defense Evasion
- Privilege Escalation

These techniques should not be added merely because they are possible explanations.

---

# 🧠 Analyst Conclusion

The strongest ATT&CK-aligned observations are:

1. A legitimate user account was used during unusual remote access.
2. A remote session accessed financial systems.
3. Sensitive files were collected.
4. Financial records were modified.
5. Outbound data transfer occurred.

The evidence supports behavioral mapping to ATT&CK techniques, but it does not identify the human operator or establish the exact initial credential-compromise method.

Further evidence is required for attribution and root-cause determination.
