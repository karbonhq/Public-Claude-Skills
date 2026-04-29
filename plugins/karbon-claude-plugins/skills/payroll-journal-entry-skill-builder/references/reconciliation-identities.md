# Payroll JE Skill Builder — Reconciliation Identities

> Load on demand from [../SKILL.md](../SKILL.md) during Step 3 (the reconciliation gate) and again when drafting the verification checklist in Step 4.

Every payroll JE must satisfy these identities. They are universal — independent of payroll provider, GL platform, entity type, and bucket structure. If any fails, the JE is wrong; do not post.

The verification checklist in the output SKILL.md should restate these identities with the client's actual numbers.

---

## The five identities

### Identity 1 — Total cost identity

```
Σ per-employee gross wages
+ Σ per-employee employer taxes
+ Σ per-employee employer benefit contributions
= Total employer cost (from the register's totals row)
```

This is the "cost of payroll to the company" check. If this fails, the per-employee data was misread or the totals row was miscategorized.

### Identity 2 — Net pay identity

```
Σ per-employee net pay
= Total net pay (from the register's totals row)
= The bank debit the payroll provider will pull
```

If the JE's net-pay credit doesn't match the bank debit, the bank reconciliation will fail next month.

### Identity 3 — Payroll-tax liability identity

```
Σ employee-side taxes (FIT + SS_EE + Medicare_EE + state income tax + local income taxes
                       + employee-side state-specific items like OR PFML, WA Cares)
+ Σ employer-side taxes (SS_ER + Medicare_ER + FUTA + SUI + employer-side state items
                          like OR Workers' Benefit ER, Trimet, MCTMT)
= Σ all payroll-tax liability credits in the JE
  (whether pooled into one account or split federal/state/local)
```

Liability accounts are pass-throughs — the company collected the tax but doesn't owe it as an expense. Both EE and ER amounts flow through liabilities; only ER amounts hit expense.

### Identity 4 — Per-benefit liability identity

For each benefit (health, dental, vision, 401(k), HSA, life, disability, etc.):

```
Employee deduction for benefit X
+ Employer contribution for benefit X
= Liability credit for benefit X
```

Special cases:
- **EE-only benefits** (commonly FSA, Roth 401(k), garnishments): no ER side. Liability credit = EE deduction only.
- **ER-only benefits** (employer-paid life, employer HSA): no EE side. Liability credit = ER contribution only.
- **Section 125 cafeteria-plan** items: usually pre-tax, so EE deduction reduces taxable wages. Confirm pre-/post-tax classification per item.

### Identity 5 — JE balance identity

```
Total debits = Total credits = Total employer cost (from Identity 1)
```

This is the master check. In a balanced JE, the debits (the gross cost to the company) must equal the credits (where the money goes: to the bank for net pay, to the IRS/states for taxes, to the benefit vendors for benefits).

---

## Cross-checks to derive missing values

If the register is incomplete, derive the missing value before reconciling:

**Net pay derivation:**
```
Net pay = Gross wages − Employee taxes − Employee deductions
```

**Total employer cost derivation:**
```
Employer cost = Gross wages + Employer taxes + Employer benefit contributions
```

**Total bank impact:**
```
Net pay (bank debit on pay date)
+ Tax deposits (separate bank debits, may be same day or scheduled by provider)
+ Benefit vendor payments (separate debits, often monthly not per-payroll)
= Total cash outflow tied to this payroll
```

The total cash outflow over time equals the total employer cost — but the timing differs. The JE recognizes the full cost on the pay date; the bank debits trickle out as taxes and vendors get paid.

---

## Common reconciliation failures and what they mean

| Symptom | Likely cause |
|---|---|
| Identity 1 fails by ~$1–$10 | Rounding in per-employee totals; trust the register's totals row, not the sum of rounded line items |
| Identity 1 fails by a clean line item amount | A line on the register was misread as a different category (e.g., FSA EE-only treated as having ER side, or vice-versa) |
| Identity 2 fails | A direct-deposit reversal, a check vs. direct-deposit difference, or a final-pay manual check |
| Identity 3 fails | Missed a state/local tax (esp. OR Trimet, NYC MCTMT, WA Cares, PA EIT); employer-side state tax not separated from employee-side |
| Identity 4 fails on a specific benefit | Pre-/post-tax classification wrong; benefit shown for an employee who waived it that period; employer contribution paid separately by vendor invoice rather than via payroll |
| Identity 5 fails but 1–4 pass | Debit/credit transposition on a single line; sign error on a deduction |

---

## What to do when a check fails

1. Identify which identity failed and by how much.
2. Match the variance against single line items on the register — most failures equal exactly one line item amount.
3. If unmatched, ask the accountant whether anything unusual happened this period (terminations, retro pay, benefit waivers, garnishment changes).
4. Do not move on to drafting until all five identities pass.

A reconciled example is the smoke test for the entire skill. A skill built on a non-reconciling example will produce non-reconciling JEs every month after.
