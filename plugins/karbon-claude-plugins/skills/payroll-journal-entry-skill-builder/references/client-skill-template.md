# Payroll JE Skill Builder — Output Template

> Load on demand from [../SKILL.md](../SKILL.md) during Step 4 (drafting). Copy the SKILL.md block below into `<client-slug>/payroll-journal-entry/SKILL.md`. Fill every section. **Cut sections that genuinely don't apply** rather than leaving placeholders.

The output is **self-contained** — the next bookkeeper to use it should not need access to any other firm document. Memo conventions, approval workflows, or login steps that come from the accountant's firm should be captured here in their own words if relevant; this skill does not assume any external firm SOP.

The companion `references/department-mapping.md` and `references/je-template.md` templates follow the SKILL.md template.

---

## SKILL.md template (the main output file)

```markdown
---
name: <client-slug>-payroll-journal-entry
description: Use this skill when working on <Full Client Name>'s <pay cadence> payroll journal entry — building <a single consolidated JE | the override JE | the verification of the auto-synced JE> from the <Provider> <name of source report> with <wages | wages, employer taxes, and employer benefit contributions> split across <N> <bucket type> buckets (<Bucket 1>, <Bucket 2>, …). Triggers on "<Client> payroll JE", "book <Client> payroll", "<Client> <cadence> payroll journal entry", or any request to record <Client>'s <Provider> payroll into <GL>.
---

# <Client Name> — Payroll Journal Entry

## Context

- **Client:** <Full Legal Name>
- **Entity type:** <LLC / S-corp / C-corp / partnership / sole prop / nonprofit> <with tax classification if relevant>
- **Industry:** <Industry, if known>
- **Payroll provider:** <Gusto / ADP / Paychex / Rippling / QBO Payroll / other>
- **GL platform:** <QBO / Xero / Sage Intacct / NetSuite / other>
- **Pay cadence:** <Weekly / Bi-weekly / Semi-monthly / Monthly / custom>
- **Source report:** <Provider's exact report name>
- **JE type:** <Manual consolidated / Override of auto-sync / Verification of auto-sync / Reclass after auto-sync>
- **Last verified:** <YYYY-MM-DD> by <name>

## When to use

Trigger this skill any time <Client>'s <cadence> payroll needs to be booked. Typical user phrasings:
- "<phrase 1>"
- "<phrase 2>"
- "<phrase 3>"

Do **not** use this skill for: <list out-of-scope situations — e.g., bonus runs, severance, year-end true-ups, 1099 contractor payments>.

## Client-specific facts

### Employee → bucket map

| Employee | Home state | Bucket | Notes |
|---|---|---|---|
| <Employee 1> | <State> | <Bucket> | <e.g., Hourly; direct labor> |
| ... | | | |

Full map and rules for new hires / role changes: [references/department-mapping.md](references/department-mapping.md).

### Account labels (debits — expense side)

Each cost type × each bucket = its own GL account. Names below are <proposed labels — map to <Client>'s actual COA on first production use | the actual COA names>.

| Cost | Bucket 1 | Bucket 2 | Bucket 3 |
|---|---|---|---|
| Gross wages | <Account> (<P&L section>) | <Account> (<P&L section>) | <Account> (<P&L section>) |
| Employer payroll taxes | <Account> | <Account> | <Account> |
| Employer benefit contributions | <Account> | <Account> | <Account> |

_(If using class tracking instead of separate accounts: collapse to one row per cost type and document classes separately.)_

### Account labels (credits — liability/clearing side)

- **<Federal Payroll Taxes Payable>** — FIT withheld + SS (both sides) + Medicare (both sides) + FUTA
- **<State & Local Payroll Taxes Payable>** — <list the states/locals>
- **<Benefit X Payable>** — EE deduction + ER contribution
- ... <one per benefit>
- **<Payroll Clearing>** — net pay (matches provider's bank debit)

## Procedure

1. <If applicable> Confirm correct GL realm/entity is active before any write.
2. Obtain the <Provider source report name> for the period. Confirm period dates and pay date.
3. Build the per-employee allocation. For each employee, pull from the report:
   - Gross wages
   - Total employer taxes
   - Total employer benefit contributions
   - Total employee taxes
   - Total employee deductions
   - Net pay

   Route each cost to the employee's bucket per the map above.
4. Aggregate to account level. Sum each expense account and each liability account. See [references/je-template.md](references/je-template.md) for the worked template.
5. **Reconciliation gate.** All five identities from `references/je-template.md` must pass before posting:
   - Total debits = total credits
   - Total JE = total employer cost from the report
   - Wage account sum = total gross wages
   - ER tax account sum = total ER taxes
   - ER benefit account sum = total ER contributions

   If any check fails, stop and investigate before posting.
6. Draft the JE with:
   - **Date:** <last day of pay period | pay date | other>
   - **Memo:** `<naming convention used at the firm — e.g., REC-YYYY-MM-### | <Client> payroll — period MM/DD–MM/DD, pay date MM/DD>`
   - **Attachment:** <Provider source report PDF>
7. <If approval is required by firm process> Restate the proposed JE to the user for approval before posting.
8. Post the JE. Record the resulting JE ID in <wherever the firm tracks posted entries — Karbon work item, spreadsheet, GL memo, etc.>.

## Tool usage (if Claude is invoking GL APIs/MCPs)

- <Tool 1> — <when to call>
- <Tool 2> — <when to call>
- For any write operation, restate the proposed change in plain English and wait for user approval before executing.

## Verification

- [ ] JE posts in balance (debits = credits)
- [ ] Total JE amount = report's total employer cost
- [ ] Total net pay credit = report's total net pay (will match the provider's bank debit)
- [ ] Wage accounts sum to total gross wages
- [ ] Employer-tax accounts sum to total ER taxes
- [ ] Employer-benefit accounts sum to total ER contributions
- [ ] Federal + State/Local payroll-tax liabilities sum to (EE taxes + ER taxes)
- [ ] Each benefit liability credit equals (EE deduction + ER contribution); EE-only benefits equal EE deduction only
- [ ] JE memo follows naming convention; source report attached
- [ ] Next bank debit (provider auto-draft) matches net pay credit and clears the Payroll Clearing account

## Exceptions / edge cases

- **New hire mid-period** — confirm bucket assignment with <client / partner / firm owner> before booking. Add to `references/department-mapping.md`.
- **Termination with final check** — book to the same bucket as the employee's last regular paycheck.
- **Bonus / commission run** — not covered by this skill; create a separate ad-hoc JE referencing the same map.
- **Provider correction or void** — book an offsetting entry referencing the original JE number; do not edit the original.
- **Period-end accrual** — <state whether monthly accrual applies and how to compute it>
- **Other client-specific exceptions** — <list any captured during the interview>

## Change log

- <YYYY-MM-DD>: Skill created. Vibe-checked against <period> payroll ($<amount> employer cost). <Notes about placeholder account names, etc.> — <name>
```

---

## `references/department-mapping.md` template

```markdown
# <Client Name> — Department/Bucket Mapping & COA

> Load on demand from [../SKILL.md](../SKILL.md) when coding the payroll JE.

## Employee → Bucket

| Employee | Home state | Bucket | Notes |
|---|---|---|---|
| ... | | | |

**Rule for new employees:** <stated rule>
**Rule for role changes:** <stated rule>

## Bucket → Expense accounts

For each bucket, list the three cost-type accounts (wages, employer taxes, employer benefits). Names are proposed labels until verified against the live COA; record actual GL account IDs once confirmed.

### <Bucket 1> (P&L section: <COGS / OpEx / etc.>)

| Cost type | Proposed account name | Account type | GL account ID |
|---|---|---|---|
| Gross wages | <name> | <type> | <id or "to be filled"> |
| Employer taxes | <name> | <type> | <id or "to be filled"> |
| Employer benefits | <name> | <type> | <id or "to be filled"> |

_(Repeat for each bucket.)_

## Liability & clearing accounts (single-bucket, not departmental)

| Proposed account name | Account type | Purpose | GL account ID |
|---|---|---|---|
| Federal Payroll Taxes Payable | Other Current Liability | FIT + SS (both sides) + Medi (both sides) + FUTA | |
| State & Local Payroll Taxes Payable | Other Current Liability | <list states/locals> | |
| <Benefit X> Payable | Other Current Liability | EE deduction + ER contribution | |
| ... | | | |
| Payroll Clearing | <Bank or OCL> | Offsets net pay; cleared by provider bank debit | |

## Multi-state / multi-local tax footprint

- **Federal**: FIT, SS, Medicare, FUTA
- **<State 1>** (<employees>): <state-specific taxes>
- ...
```

---

## `references/je-template.md` template

```markdown
# <Client Name> — Payroll JE Template & Worked Example

> Load on demand from [../SKILL.md](../SKILL.md) when building the JE.

## JE structure

### Debits (expense side)

| Line | Account | Amount |
|---|---|---|
| 1 | <Wages – Bucket 1> | Σ gross wages of Bucket 1 employees |
| 2 | <Wages – Bucket 2> | Σ gross wages of Bucket 2 employees |
| ... | ... | ... |

Omit any line with $0.

### Credits (liability + clearing)

| Line | Account | Amount |
|---|---|---|
| A | Federal Payroll Taxes Payable | FIT + SS (both sides) + Medi (both sides) + FUTA |
| B | State & Local Payroll Taxes Payable | All state income tax + SUI + locals |
| ... | ... | ... |
| Z | Payroll Clearing | Total net pay |

## Reconciliation identities

```
Total Debits = Total Credits = Total Employer Cost

Σ wage account lines = Total Gross Wages
Σ employer-tax account lines = Total Employer Taxes
Σ employer-benefit account lines = Total Employer Contributions
Σ payroll-tax liability credits = (Total EE Taxes + Total ER Taxes)
Each benefit liability credit = (EE deduction + ER contribution); EE-only = EE deduction
Payroll Clearing credit = Total Net Pay
```

## Worked example — <Period> payroll (pay date <MM/DD/YYYY>)

Source: <Provider> <source report name>, period <MM/DD/YYYY> – <MM/DD/YYYY>.

### Per-employee inputs

| Employee | Bucket | Gross | ER taxes | ER benefits | EE taxes | EE deductions | Net pay |
|---|---|---|---|---|---|---|---|
| <Employee> | <Bucket> | $X | $X | $X | $X | $X | $X |
| ... | | | | | | | |
| **Totals** | | **$X** | **$X** | **$X** | **$X** | **$X** | **$X** |

### Aggregate JE

**Date:** <MM/DD/YYYY>
**Memo:** `<full memo per naming convention>`

| Line | Account | Debit | Credit |
|---|---|---:|---:|
| 1 | <Account> | $X | |
| ... | ... | | |
| | **Totals** | **$X** | **$X** |

### Reconciliation checks (each must tie)

- Total debits $X = Total credits $X = Total employer cost $X ✓
- Wage lines: $X = total gross wages $X ✓
- ER tax lines: $X = total ER taxes $X ✓
- ER benefit lines: $X = total ER contributions $X ✓
- Federal + State/Local liability credits: $X = (EE taxes $X + ER taxes $X) ✓
- Net pay credit: $X = total net pay $X ✓
```

---

## Filling guidance

**`description` frontmatter** is the most important line — it's what the agent reads to decide whether to load the skill. Strong example:

> ✅ "Use this skill when working on Goodbeast Creative LLC's monthly payroll journal entry — building a single consolidated JE from the Gusto Payroll Journal Report with wages, employer taxes, and employer benefit contributions split across three departmental buckets (COGS Labor, Owner Labor, Overhead Labor). Triggers on 'Goodbeast payroll JE', 'book Goodbeast payroll', 'Goodbeast monthly payroll'…"

Weak example to avoid:

> ❌ "Handles Goodbeast payroll."

**Self-contained procedure:** The output skill must be runnable by anyone, including someone who's never seen the firm's other documentation. Don't write "follow the firm SOP" — capture the actual steps in the procedure.

**Worked example:** Always include real numbers from Step 3. Future reviewers use this example as the smoke test.

**References folder:** Push anything longer than ~10 rows or ~30 lines out of SKILL.md and into a references file. Keep SKILL.md under ~200 lines.

**Account IDs vs. names:** Names are placeholders. Record GL account *IDs* on first production use and cache them in `references/department-mapping.md` so future runs don't re-lookup.
