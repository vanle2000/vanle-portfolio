---
title: "Financial Reconciliation Analytics"
category: "Business Intelligence Engineering"
tags: ["Python", "SQL", "Pandas", "Financial Analytics", "ETL", "Variance Detection"]
result: "Automated reconciliation pipeline · Variance detection and flagging across source systems"
github: "https://github.com/vanle2000/Financial-Reconciliation-Analytics"
---

## The Problem

Financial data reconciliation is one of the most error-prone and time-consuming tasks in accounting and tax workflows. When data flows from multiple source systems — payroll, invoicing, banking, ERP — discrepancies accumulate silently until they surface at reporting time, often under deadline pressure.

The manual process: export CSVs from each system, open in Excel, VLOOKUP or filter row-by-row, flag mismatches, email back and forth. This creates:
- Audit trails that live in email threads, not databases
- Error-prone manual comparison on large datasets
- No systematic flagging of anomaly types or variance thresholds
- No reproducible pipeline — every reconciliation is a one-off

## Solution

An automated reconciliation pipeline that:
1. Ingests data from multiple source systems via modular loaders
2. Applies configurable matching rules per reconciliation type
3. Computes variance at the line-item level with explainable flagging
4. Produces structured, audit-ready output in the format required for tax and advisory reporting

## Pipeline Architecture

```
data/source_a/     ← System 1 exports (invoicing, ERP)
data/source_b/     ← System 2 exports (banking, payroll)
data/reconciled/   ← Matched records with variance columns
data/exceptions/   ← Flagged discrepancies with reason codes

src/
├── loaders/       ← System-specific ingestion with schema validation
├── matching/      ← Record linkage logic (exact + fuzzy match)
├── variance/      ← Threshold rules, flag generation, reason coding
└── reporting/     ← Audit-ready output generation (CSV, Excel, PDF)
```

**Matching Strategy**

Records are matched across systems in three passes:
1. **Exact match**: transaction ID or reference number (highest confidence)
2. **Fuzzy match**: amount + date within tolerance window (catches formatting differences)
3. **Unmatched**: records present in one system but not the other — highest-priority flags

**Variance Classification**

Each discrepancy is assigned a reason code:

| Code | Meaning |
|------|---------|
| `AMT_DIFF` | Same transaction, different amount |
| `DATE_SHIFT` | Same transaction, different posting date |
| `MISSING_A` | Present in source A, absent in source B |
| `MISSING_B` | Present in source B, absent in source A |
| `DUP` | Duplicate entries detected in one system |

**Audit-Ready Output**

The final report is structured for direct submission to tax and financial advisory workflows: one row per discrepancy, with source values, computed variance, reason code, and a confidence score for the match. No manual post-processing required.

## What Makes This Different

Most reconciliation tools require you to configure their schema to yours. This pipeline is code — every matching rule, tolerance threshold, and reason code is version-controlled, reproducible, and auditable. A reconciliation run from six months ago can be re-run identically with `make reconcile --date 2024-06-30`.

## What Would Be Explored Next

- Add ML-based anomaly detection to flag structurally unusual transactions — not just mismatches, but records that look like outliers even within a matched pair
- Extend to real-time reconciliation via database CDC (change data capture) rather than batch exports
- Build a lightweight dashboard to track exception rates over time and detect when a source system is degrading in data quality
