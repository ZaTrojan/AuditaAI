# Zecathon 6.0 — Application Form Answers

**Track:** AI-Powered Transaction Investigation and Resolution
**Deadline:** October 13, 2026
**Portal:** https://cutt.ly/zecathon6

Word counts verified against the form's limits. Fields 2 and 3 are hard-capped at 100 words each.

---

## Field 1 — Hackathon Track

> **AI-Powered Transaction Investigation and Resolution**

---

## Field 2 — Problem Description (max 100 words)

> Statutory and internal audits test a sample. That sample is commonly 5–10% of transactions, and fraud does not occur in the sample. In Nigeria the gap is wider: invoices and receipts arrive as scans and paper, while payments sit in bank ledgers as free-text NIBSS narrations. Matching them by hand consumes most of an audit's hours. Duplicate vouchers, ghost vendors, amounts split just below approval tiers, and unapplied withholding tax survive for months. At banks, that leakage becomes non-performing loan risk across corporate lending.

**Word count: 84 / 100** ✓

---

## Field 3 — Solution Overview (max 100 words)

> AuditaAI audits every transaction, not a sample. Gemini multimodal models read scanned invoices, receipts and purchase orders into structured fields. A deterministic Python engine performs three-way matching across purchase order, invoice and bank debit using decimal arithmetic, so the language model never performs a calculation. Forensic rules test for duplicate vouchers, threshold splitting, vendor account substitution and unapplied withholding tax. Every exception carries a side-by-side citation to its source document and the rule breached. Findings resolve through query, hold, recovery or escalation, and close into an ISA 230 workpaper an auditor can sign.

**Word count: 93 / 100** ✓

---

## Field 4 — Technologies to Be Adopted

**Generative AI / Multimodal**
Google Gemini multimodal API for document understanding and OCR across scanned invoices, receipts and purchase orders, constrained to a strict JSON output schema. The model performs perception and semantic reasoning only — never arithmetic.

**Agentic orchestration**
Python multi-agent pipeline with typed data contracts (Pydantic) between every stage, so a malformed extraction fails loudly instead of silently corrupting a reconciliation.

**Deterministic computation**
Python `decimal` for all matching, totals, tolerance checks and tax computation. Every figure an auditor signs is reproducible from source.

**Forensic analytics**
Rule engine for duplicate and near-duplicate voucher detection (fuzzy vendor/amount/date matching), approval-threshold-splitting detection, and vendor bank-account integrity checks against the vendor master.

**Backend**
FastAPI, SQLAlchemy, PostgreSQL (SQLite for the hackathon build).

**Frontend**
Next.js (React), Tailwind CSS, Recharts for the risk and exception dashboards.

**Compliance framework**
ISA 240 (fraud), ISA 230 (audit documentation) and ISA 500 (audit evidence); FIRS Withholding Tax and VAT schedules; CBN internal-control expectations.

**Data protection**
PII pseudonymisation before any model inference, zero-retention model endpoints, Nigeria Data Protection Act 2023 alignment.

**Deployment**
Containerised, deployable inside the bank's own environment rather than as a public multi-tenant SaaS.

---

## Field 5 — Implementation Approach

**Integration points, in order of how little they demand**

1. **Statement and ledger export (day one).** AuditaAI ingests CSV/Excel exports plus scanned documents. No core-banking integration, no IT change request, no procurement cycle. This is how the pilot starts.
2. **ERP connector (phase two).** Read-only connector to pull purchase orders and vendor master directly, removing the manual export step.
3. **Core banking API (phase three).** Streaming transaction feed so investigation runs at settlement time rather than after the fact — the point at which a payment hold becomes possible.

**Phases**

- **Phase 1 — Pre-sprint (Oct 14–19).** Synthetic test file of 60 realistic disbursement transactions with five seeded exception cases, GitHub repository, FastAPI and Next.js scaffolding, regulatory rule definitions.
- **Phase 2 — Live hackathon (Oct 20–22).** Multimodal extraction pipeline, deterministic three-way matching engine, forensic rule engine, auditor workbench UI. Success condition: all five seeded cases trigger with correct citations.
- **Phase 3 — Pitch and demo polish (Oct 23–28).** Dry runs, backup demo recording, final deck.
- **Phase 4 — Pilot (post-hackathon).** Single-entity deployment inside an internal audit or inspection function, running on historical data first so results can be compared against known findings before anything touches live payments.

**Methods**

Test-first on the fraud cases: each of the five exception patterns is written as a failing test before the detector exists. Deployment is containerised and environment-agnostic, so the same image runs in a laptop demo, a bank VPC and a cloud instance.

---

## Before you submit — verify these

- [ ] Paste both word-limited fields into a counter before submitting; some portals count hyphenated words differently.
- [ ] The deck cites no external statistics — every figure traces to the seeded test file or a named regulatory schedule. Keep it that way; don't add market-size or loss estimates you can't source.
- [ ] Confirm the Google Drive link is set to **"Anyone with the link – Viewer"** and open it in an incognito window.
- [ ] Confirm the PDF is landscape 13.333in × 7.5in, not portrait.
- [ ] Before saving the PDF, untick **Headers and footers** in the print dialog (under *More settings*). Chrome otherwise prints the date, time and file path into every page margin — no CSS can suppress it.
- [ ] Remove the recommended subtitle *"Powered by Zenith Bank Corporate Solutions"* from any earlier draft — it claims an endorsement that doesn't exist.
