---
name: payroll-journal-entry-skill-builder
description: Use this skill when an accountant or bookkeeper wants to create a reusable, client-specific payroll journal entry skill. Triggers on phrases like "create a payroll JE skill for [client]", "build a payroll journal entry skill", "codify how we book [client]'s payroll", "help me make a skill for [client]'s payroll", or "generate a payroll JE procedure for [client]". The skill starts by reading a real payroll register, then asks a short set of allocation questions, validates the math, and produces a client-specific SKILL.md that any team member (or Claude) can use next pay period to book the same JE consistently. Firm-agnostic — works regardless of payroll provider, GL platform, or practice-management tool.
---

# Payroll Journal Entry Skill Builder

A meta-skill for accountants. Given a real payroll register and a few allocation answers, it produces a **client-specific** payroll JE skill so the next bookkeeper to touch that client's books can post the JE without rediscovering the rules.

The skill assumes the accountant already knows their firm's general approach to payroll JEs. It only captures what is **client-specific** — buckets, employee map, allocation rules, and any quirks worth flagging.

## What this skill produces

A self-contained directory the accountant can drop into any skills folder, knowledge base, or shared firm vault:

```
<client-slug>/payroll-journal-entry/
├── SKILL.md                       (the client-specific skill — under ~200 lines)
└── references/                    (loaded on demand from SKILL.md)
    ├── department-mapping.md      (employee → bucket map + account labels)
    └── je-template.md             (JE structure + a fully reconciled worked example)
```

## When to use

Trigger when an accountant explicitly asks to **codify** a recurring payroll JE for one client. Do **not** trigger for:

- Booking a single payroll run today (just book it — don't write a skill for a one-off).
- Generic payroll education (use a bookkeeping reference instead).
- Non-payroll JEs (different reconciliation rules).
- A client whose payroll auto-syncs cleanly with no overrides (no skill needed; the provider's GL sync is the procedure).

## Workflow

Four steps, in order. **Do not skip Step 3** (the reconciliation gate).

### Step 1 — Get the register

Ask the accountant to upload (or paste) the most recent pay period's payroll register, or a sanitized copy. Required fields per employee: gross wages, employee taxes total, employee deductions total, employer taxes total, employer benefit contributions total, net pay. Plus all-employee totals.

If the report is missing any of these, ask for a different report. The skill cannot be drafted from incomplete data — vagueness here produces a vague output skill that won't work next month.

Provider-specific guidance on which report to ask for is in [references/payroll-provider-notes.md](references/payroll-provider-notes.md).

Once the register is in hand, extract and confirm with the accountant:

- Provider + exact report name
- Pay period dates and pay date
- Employee list
- Per-employee totals and aggregate totals

This becomes the ground truth for everything that follows.

### Step 2 — Allocation interview

Walk the accountant through the questions in [references/allocation-interview.md](references/allocation-interview.md). The interview is short and only covers what is genuinely client-specific:

1. Client identity (legal name, slug)
2. GL platform + whether it supports classes/locations/dimensions
3. Bucket structure — split or single? mechanism (separate accounts / classes / locations / dimensions)?
4. Employee → bucket map (one row per employee from the register)
5. Splits — anyone allocated across buckets? method?
6. Burden allocation — do ER taxes and ER benefits follow the employee, or pool to a single account?
7. Liability structure — pooled or split federal/state/local? Net pay → cash directly or via a Payroll Clearing account?
8. Client-specific exceptions — owner comp, tipped employees, retirement match, garnishments, multi-state, period-end accruals, anything else another bookkeeper would be surprised by

The high-leverage answers are bucket structure (Q3) and the employee→bucket map (Q4). Confirm those explicitly before moving on.

Capture answers in working notes; they become the body of the output SKILL.md.

### Step 3 — Reconciliation gate

Before drafting anything, prove the example reconciles using the identities in [references/reconciliation-identities.md](references/reconciliation-identities.md):

1. Σ per-employee gross + ER taxes + ER benefits = total employer cost
2. Σ per-employee net pay = total net pay (= bank debit from the provider)
3. Σ EE taxes + Σ ER taxes = Σ payroll-tax liability credits
4. For each benefit: EE deduction + ER contribution = that benefit's liability credit (FSA and similar EE-only deductions have no ER side)
5. Total debits = total credits = total employer cost

If any identity fails, **stop**. Common failures: miscategorized line on the register, missed state/local tax, an "EE deduction" that's actually post-tax (or vice-versa), or a benefit the employee is enrolled in that isn't on the register because they were waived this period. Resolve with the accountant before drafting.

### Step 4 — Draft + vibe-check

Use the template at [references/client-skill-template.md](references/client-skill-template.md). Fill every section with facts from Steps 1–3. Cut any section that genuinely doesn't apply rather than leaving placeholders.

Push long material into `references/`:

- **`references/department-mapping.md`** — full employee → bucket map, account-label table for each bucket × cost type, multi-state tax footprint, rules for new hires and role changes.
- **`references/je-template.md`** — JE structure (debit lines, credit lines), the universal reconciliation identities, and the **fully worked example from Step 3** with every per-employee number and every aggregate that ties to the register.

The worked example is the single most important artifact. It's the smoke test next month.

Then re-walk the Step 3 example using only the drafted SKILL.md and references — pretend you've never seen the client before. The procedure must produce the exact JE that reconciled in Step 3. If anything is ambiguous, fix the SKILL.md (not the example) and re-walk.

Confirm with the accountant before closing:

- The path where the skill lives
- 2–3 trigger phrases the team will use to invoke it next time
- The next pay period it will run against in production
- Whether any account labels are still placeholders that need mapping to real GL account IDs on first production use

## Output requirements

Every output SKILL.md must include:

- A `description` frontmatter that **names the client explicitly** and includes 2–3 realistic trigger phrases
- A context block (client legal name, entity type if known, industry, payroll provider, GL platform, pay cadence)
- A self-contained procedure (no assumed firm SOP — the output skill must be runnable by anyone)
- Employee → bucket map (at least a pointer to `references/department-mapping.md`)
- Account label table per bucket × cost type
- Step-by-step procedure that produces a balanced JE
- Reconciliation checklist (the five identities, instantiated to the client's data)
- Exceptions section (new hires, mid-period changes, voids, special runs)
- A change log

## Anti-patterns — do not do these

1. **Don't draft without a reconciled example.** If the math doesn't tie in Step 3, it won't tie next month.
2. **Don't embed credentials, realm IDs, or employee PII** beyond legal name and home state. Reference secrets by location ("retrieve from firm vault"), never embed.
3. **Don't hardcode GL account IDs without verification.** Account *labels* are fine as placeholders; *IDs* must be verified against the live COA on first production use, then cached in `references/department-mapping.md`.
4. **Don't conflate cadences.** One skill = one client = one recurring payroll cadence. Bonus runs, severance, year-end true-ups go in separate skills.
5. **Don't skip the bucket conversation.** "We just have one wage account" might be true and the skill is much simpler — but confirm, don't assume.
6. **Don't write generic procedures.** "Book the wages" is not actionable. "Debit `Wages – COGS Labor` for $2,282.50 (Kiesel's gross from the Jan 2026 register)" is.
7. **Don't re-derive what the firm already knows.** This skill captures *client-specific* allocation logic. Memo conventions, approval thresholds, and provider login workflows belong in the firm's own SOPs, not in every client skill.

## Done criteria

The output skill is finished when:

- SKILL.md exists, under ~200 lines, with filled context, procedure, and verification sections
- `references/department-mapping.md` and `references/je-template.md` exist
- The worked example in `je-template.md` reconciles to the penny on all five identities
- No secrets, realm IDs, or sensitive PII are embedded
- The accountant can state in one sentence what the skill does and when to use it
- 2–3 trigger phrases appear in the description frontmatter
