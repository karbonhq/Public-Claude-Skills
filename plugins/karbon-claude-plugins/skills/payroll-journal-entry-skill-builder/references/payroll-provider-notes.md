# Payroll JE Skill Builder — Payroll Provider Notes

> Load on demand from [../SKILL.md](../SKILL.md) during Step 2 to identify which report to ask for and what behavior to expect.

This is a quick orientation, not exhaustive. When in doubt, ask the accountant which report they actually use today.

---

## Gusto

- **Canonical report:** "Payroll Journal Report" (under Reports → Payroll). Per-employee earnings, deductions, EE taxes, ER taxes, totals row.
- **GL sync:** Optional QBO/Xero integration. Default behavior creates **3 JEs per run**: net pay, tax payments, benefit vendor payments. GL mapping is configurable per earning/deduction code, but department-level splits are limited unless using Gusto departments + mapping each department to a separate set of accounts.
- **Common skill pattern:** Gusto auto-sync turned **off** for clients needing more than basic departmental splits; manual JE built from the Payroll Journal Report.
- **Quirks:** Multi-state taxes appear as separate line items per state — easy to miss one when aggregating. Oregon taxes especially numerous (Trimet, Workers' Benefit Fund both sides, Statewide Transit, PFML).

## ADP RUN (small business)

- **Canonical report:** "Payroll Register" or "Payroll Detail" report.
- **GL sync:** ADP's "General Ledger Interface" pushes to QBO via a downloadable file (IIF historically; CSV for newer integrations). Mapping is set up once per client.
- **Common skill pattern:** Verification of ADP's auto-pushed JE; reclass entries when ADP's mapping doesn't match the client's bucket structure.
- **Quirks:** ADP report column names differ between RUN and Workforce Now. Always confirm which ADP product. RUN is per-pay-period; Workforce Now is more configurable.

## ADP Workforce Now (mid-market)

- **Canonical report:** "Payroll Register" plus optional "GL Detail" report.
- **GL sync:** Direct integrations to QBO, NetSuite, Sage Intacct, Workday Financial. Strong departmental support.
- **Common skill pattern:** Verification + reclass for nuanced splits the GL sync doesn't natively handle.

## Paychex Flex

- **Canonical report:** "Payroll Journal" (per pay period, all employees).
- **GL sync:** "General Ledger Reporting" via downloadable file or Flex Integration to QBO. Mapping at the earning/deduction level.
- **Quirks:** Some Paychex reports show only employer cost without splitting EE vs. ER on each tax — confirm by running the "Tax Breakdown" report alongside.

## Rippling

- **Canonical report:** "Payroll Run Summary" + per-employee breakdown.
- **GL sync:** Native QBO, NetSuite, Sage Intacct, Xero integrations with strong department/class/location mapping.
- **Common skill pattern:** Auto-sync usually correct; skill mainly verifies the sync rather than rebuilding the JE.

## QuickBooks Online Payroll (Intuit)

- **Canonical report:** "Payroll Summary" or "Payroll Details" report inside QBO.
- **GL sync:** Built-in — JEs are created directly in QBO with no separate sync step.
- **Common skill pattern:** **Reclass entry** post-payroll because QBO Payroll has limited departmental controls. The skill aggregates QBO's auto-posted entries and journals corrections to the right buckets.
- **Quirks:** QBO Payroll's account mapping is firm-wide per company file, not per-employee. If two employees should hit different wage accounts, QBO Payroll alone can't do it without a reclass.

## Patriot, OnPay, Wave Payroll, Square Payroll

- Smaller providers, similar pattern: per-pay-period payroll register report + optional GL sync (limited mapping). Most clients on these providers need a manual JE for any non-trivial bucket structure.

## Manual / Spreadsheet

- The accountant builds the payroll on a spreadsheet (often when an EOR or PEO is involved and the firm only sees a summary).
- **Source:** Whatever the EOR/PEO provides — usually a per-pay-period invoice plus a payroll detail file.
- **Quirks:** EOR/PEO billing often pools fees with payroll cost; isolate the EOR fee as a separate operating expense, not as wages.

---

## Universal report fields the accountant needs

Regardless of provider, the report passed to Step 2 must include per employee:

- Gross wages (and any pay-type breakdown if relevant: regular, OT, bonus, commission)
- Total employee taxes (federal income tax, SS_EE, Medicare_EE, state/local income, employee-side state-specific items)
- Total employee deductions (each benefit + each garnishment, broken out)
- Total employer taxes (SS_ER, Medicare_ER, FUTA, SUI, employer-side state items)
- Total employer benefit contributions (each benefit, broken out)
- Net pay

Plus an all-employee totals row.

If the report omits any of these, ask for a different report or a per-employee breakdown. Don't try to draft the skill from incomplete data.

---

## Bank-debit timing per provider

Most providers debit the operating account in **two or three pulls**:

1. **Net pay** — on the pay date (sometimes 1–2 business days earlier)
2. **Taxes** — same day, next day, or scheduled by deposit frequency
3. **Benefits** — separate, often monthly invoice from each carrier (not always in sync with payroll)

The skill's net-pay credit (the Payroll Clearing account) ties to debit #1. Tax-deposit debits clear the federal/state liability accounts. Benefit-vendor debits clear the benefit liability accounts.

Document this timing in the output skill's verification section so the next bookkeeper knows what to expect on the bank reconciliation.
