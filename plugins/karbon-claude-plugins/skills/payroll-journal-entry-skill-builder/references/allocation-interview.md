# Payroll JE Skill Builder — Allocation Interview

> Load on demand from [../SKILL.md](../SKILL.md) during Step 2 of the workflow.

The accountant already knows their firm's general payroll JE method. This interview only captures what's **client-specific**: how this client's payroll splits across the GL, who maps to what, and any exceptions worth codifying.

Ask in order. Skip questions whose answer is already obvious from Step 1's register or from earlier replies. **Confirm bucket structure (Q3) and the employee→bucket map (Q4) before moving past Q4** — those are the most expensive answers to get wrong.

---

## 1. Client identity

1.1 Full legal name?
1.2 Short kebab-case slug for filenames? (e.g., `acme-manufacturing`, `bright-dental-pc`)

That's it. Entity type, industry, and home state are nice-to-haves — capture only if the accountant volunteers them or if they affect the JE (e.g., owner is on payroll → see Q8 owner-comp exceptions).

## 2. GL platform

2.1 Which GL? (QBO, Xero, Sage Intacct, NetSuite, Wave, FreshBooks, other)
2.2 Does the GL support classes / locations / dimensions / departments natively, and does the client use them? (Determines the mechanism options in Q3.)

## 3. Bucket structure (HIGH-LEVERAGE — confirm before moving on)

3.1 Does the client want payroll cost split across buckets, or all in one wage account?
   - **Single account** → Q4 collapses to "all employees → single bucket." Skip to Q6.
   - **Split** → continue.
3.2 What are the buckets? (Examples: COGS Labor / Owner Labor / Overhead Labor; Production / Sales / G&A; per location; per project; per department.)
3.3 What's the GL mechanism for each bucket?
   - **Separate GL accounts** (e.g., `Wages – Production`, `Wages – G&A`) — most common for COGS-vs-OpEx splits because P&L section is determined by account type
   - **Class tracking** (single account, class per bucket) — common when all buckets are within OpEx
   - **Location tracking** — when buckets = physical locations
   - **Custom dimension / department code** — Sage Intacct, NetSuite
3.4 If separate accounts: confirm each bucket's P&L section (COGS vs. Operating Expense vs. Other Expense).

## 4. Employee → bucket map (HIGH-LEVERAGE)

4.1 Take the employee list from the register. For each employee, which bucket?
4.2 Rule for **new hires** — does the firm assign at hire, or ask the client each time?
4.3 Rule for **role changes** — effective date is start of next pay period, retro to start of period, or retro to date of change?

## 5. Splits across buckets

5.1 Are any employees split across buckets? (e.g., 60% Production / 40% G&A)
5.2 If yes, allocation method — % of hours, % of revenue, fixed %, time tracking?

## 6. Burden allocation

6.1 Which costs follow the employee to their bucket?
   - **Gross wages** — always
   - **Employer payroll taxes** (SS, Medicare, FUTA, SUI, state/local) — usually yes ("match cost to labor")
   - **Employer benefit contributions** (health, dental, retirement match, HSA, life, disability) — usually yes
   - **Workers' compensation** — varies; some firms accrue separately
6.2 If only some costs follow: pooled costs go to which account? (e.g., "all ER taxes to one Payroll Tax Expense regardless of bucket")

## 7. Liability structure

7.1 How are payroll-tax liabilities structured?
   - One pooled `Payroll Liabilities` account
   - Split: Federal vs. State/Local
   - Per-state (rare; seen in multi-state firms with strong segregation)
7.2 How are benefit liabilities structured? (One per benefit type, or pooled into `Benefits Payable`?)
7.3 Net-pay handling: does the JE credit cash directly, or use a `Payroll Clearing` account that's offset by the provider's bank debit?

## 8. Client-specific exceptions

Only capture exceptions that **materially affect this client's JE**. Don't list generic possibilities the client doesn't actually do.

Prompt the accountant: "What does this client do that would surprise another bookkeeper?" Then probe these common areas only if relevant:

- **Owner / officer comp** — S-corp 2%+ shareholder health insurance added to W-2 Box 1 at year-end? Partnership guaranteed payments instead of W-2 wages?
- **Retirement** — 401(k) / SIMPLE / SEP? Employer match formula? Profit-sharing accrued monthly or booked annually?
- **Tipped employees** — reported tips, allocated tips, tip credit, tip pool reallocation?
- **Garnishments / child support / levies** — separate liability per garnishment, or pooled?
- **Pre-tax vs. post-tax classification** — confirm each deduction the register shows. Common gotchas: Roth 401(k) is post-tax; HSA is usually pre-tax via Section 125; FSA is pre-tax.
- **Reimbursements through payroll** — mileage, expense reimbursement, accountable plans → book to expense reimbursement, not wages.
- **Employer-only costs not on the register** — workers' comp premium, employer life, employer HSA outside payroll deduction. Are these accrued in this JE or booked separately?
- **Multi-state / multi-local** — which states/locals does the client have payroll-tax registration in? Notable: Oregon (Trimet, Workers' Benefit, Statewide Transit, PFML), Pennsylvania (LST, EIT per municipality), Ohio (school district + municipal), New York (NYC, Yonkers, MCTMT), Washington (WA Cares, PFML), California (SDI, ETT), Indiana/Maryland/Michigan (county income).
- **Period-end accruals** — does the pay period cross month-end? If yes, how is the accrual computed and does it reverse on the 1st?
- **Special pay runs** — bonus, commission, severance — confirm those are out of scope for this skill (one skill = one recurring cadence).

## 9. Anything else?

9.1 Any quirk, override, or convention specific to this client that another bookkeeper would be surprised by? Capture in plain English; the output skill will turn it into an exception entry.

---

## After the interview

Restate to the accountant in 5–8 bullets:

- Buckets and the mechanism (separate accounts / class / location / dimension)
- Employee→bucket map summary + new-hire rule
- Costs that follow employees vs. costs that pool
- Liability structure (federal/state split? per-benefit vs. pooled? clearing account?)
- Material client-specific exceptions
- Period-end accrual handling

Get explicit confirmation before moving to Step 3 (the reconciliation gate).
