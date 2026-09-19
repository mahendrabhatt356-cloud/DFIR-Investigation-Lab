# DFIR Investigation Process

## Case Reference

- **Case ID:** CASE-001
- **Case Name:** The Midnight Login
- **Investigation Type:** Digital Forensics and Incident Response (DFIR)
- **Environment:** Synthetic / Educational Investigation Lab
- **Primary System:** NOVA-FIN-07
- **Primary Account:** arjun.mehta

---

## 1. Purpose

This document defines the investigation methodology used for CASE-001.

The objective is to investigate a suspicious sequence of events involving:

- Unusual remote authentication
- Remote session activity
- Finance application access
- Financial record modification
- Access to sensitive finance files
- Outbound data transfer
- Unknown external destination

The investigation uses synthetic evidence created for educational and portfolio purposes.

No real user, organization, financial system, or production environment is involved.

---

## 2. Investigation Principles

The investigation follows these principles:

1. Preserve evidence before drawing conclusions.
2. Separate observed facts from assumptions.
3. Correlate multiple evidence sources.
4. Maintain a clear timeline.
5. Avoid unsupported attribution.
6. Record uncertainty explicitly.
7. Document findings so another investigator can reproduce the reasoning.

---

## 3. Investigation Lifecycle

The investigation follows this general lifecycle:

```text
Preparation
     ↓
Identification
     ↓
Preservation
     ↓
Collection
     ↓
Examination
     ↓
Correlation
     ↓
Analysis
     ↓
Findings
     ↓
Reporting
