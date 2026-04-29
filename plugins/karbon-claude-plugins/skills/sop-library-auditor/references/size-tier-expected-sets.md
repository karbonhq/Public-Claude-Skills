# Size-Tier Expected SOP Sets

What SOPs a firm "should have" depends on its size. Don't penalize a 3-person bookkeeper for not having a partner sign-off matrix; don't let a 30-person firm off the hook for the same thing.

Use this file in Stage 3 (Classify and Score). For each tier, the listed SOPs are the **minimum expected set**. Anything beyond them is bonus. Anything missing from them is a gap. Domain numbers refer to `framework.md`.

## Tier 1 — Solo / 1–3 person firm

Document survival-critical and compliance-mandatory SOPs only. Don't try to build 50.

- 15.1 — WISP (legally required if you touch any tax data)
- 1.1–1.6 — Client onboarding (single combined SOP)
- 6.1–6.4 — Monthly close (single master template)
- 5.1 — Bank reconciliation
- 4.5–4.9 — AP / bill-pay (combined)
- 4.10–4.13 — AR / invoicing (combined)
- 8.11–8.13 — 1099 process
- 8.4–8.7 — Payroll process (or "we use Gusto and here's our exception SOP")
- 1.15–1.18 — Client offboarding / data export
- 1.3 + 1.12 — Engagement letter + scope-change
- 6.17 — Tax-prep handoff package

**Total: ~10–11 SOPs.**

Compliance floor at this tier: Domain 15.1 (WISP). If absent, `compliance_floor: true` with composite priority floored at 11.

## Tier 2 — 4–15 person firm

Add operational depth and start tagging AI-eligibility.

Everything from Tier 1, plus:

- 1.10 — Client cheat sheet template
- 13.2 — RACI matrix (firm-level, can be referenced by individual SOPs)
- 5.x split — Weekly reconciliation cadence
- 8.14–8.15 — Sales-tax compliance (if any clients have sales-tax obligations)
- 4.14–4.16 — Expense management (combined)
- 6.13–6.16 — Year-end close
- 7.6–7.8 — Basic KPI reporting (P&L, BS, CF, AR/AP aging at minimum)
- 11.1–11.3 — Workflow management in Karbon/Canopy/Financial Cents
- 13.4 — Hiring / firm onboarding
- 13.6 — CPE tracking
- 14.8 — SOP version control / knowledge management
- 15.2 — FTC Safeguards program (legally required if 11+ federal returns or ~5,000 PII records)
- 16.1–16.2 — AI usage policy + approved tools list (if firm uses any AI, even ChatGPT informally)

**Total: ~22–25 SOPs.**

Compliance floor adds 15.2 (FTC Safeguards) at this tier. If the firm uses AI tools (sanctioned or unsanctioned) and has no Domain 16 policy, that's a critical compliance flag too.

## Tier 3 — 16–40 person firm

Add advisory, quality, and governance.

Everything from Tier 2, plus:

- 9.1–9.3 — Outsourced controller (combined)
- 9.6–9.8 — Budgeting / FP&A
- 9.4–9.5 — Cash-flow management
- 9.9–9.12 — Fractional CFO playbook
- 10.1–10.10 — Full QC & review domain (SQMS quality program)
- 12.2, 12.4 — Vendor security review, data-flow controls
- 15.6 — Vendor / third-party security review
- 15.14 — SOC 2 readiness (if any clients require)
- 9.13 — Industry KPI library (if niche concentration)
- 3.1–3.3 — Client-segmentation pricing & annual price review
- 16.3–16.5 — Prompt library, oversight tier, AI consent in engagement letters

**Total: ~40–55 SOPs.**

## Tier 4 — 41–100 person firm

Add scale, niche, and AI-orchestration.

Everything from Tier 3, plus:

- 9.13 (full per niche) — Per-niche service catalogs
- 9.11 — M&A diligence support
- 6.x specialized — Lease accounting (ASC 842), revenue recognition memos (ASC 606), stock-based comp memos
- 8.2 (full) — Multi-state nexus
- 10.x — Audit prep / PBC management
- 15.14 (full) — SOC 2 attested program
- 16.6–16.10 — Full Domain 16 — vendor AI feature review, model risk policy, AI execution logs/evals, prohibited-use list, onboarding AI-consent disclosure
- 14.5 — Succession planning
- 13.5–13.7 — Training academy & career ladder
- 14.8 (full) — Knowledge-management governance

**Total: ~70–95 SOPs.**

## How the skill uses this file

In Stage 3, after intake:

1. Pull the size tier from `working/firm-profile.md`.
2. Load the corresponding tier's expected set.
3. Adjust:
   - If the firm has 0% in a service mix area, drop expected SOPs from that domain (e.g., 0% payroll → drop the 8.1–8.10 expectations; mark Domain 8 as N/A if no sales tax either).
   - If the firm has niche concentration ≥60%, add expected niche-specific SOPs (typically inside whichever production domain houses them, plus Domain 9.13).
   - If the firm requires SOC 2, add 15.14 SOPs even if their tier wouldn't otherwise demand them.
   - If the firm offers fractional CFO, add Domain 9.9–9.12 even at Tier 2.
   - If the firm uses ANY AI tools (intake Q9), Domain 16.1–16.2 become floor regardless of tier.
4. The expected set minus the existing inventory = gaps. Each gap becomes a row in `working/sop-inventory.json` with `exists: false` and a composite priority computed.

## Why these specific lists

The lists synthesize CAS 2.0, Karbon's template library, AICPA SSARS / SQMS, IRS Pu