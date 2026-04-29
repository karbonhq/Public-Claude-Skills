---
name: sop-library-auditor
description: Audit, organize, score, and fill gaps in an accounting/bookkeeping/CAS firm's existing library of standard operating procedures (SOPs). Trigger this skill whenever a firm wants to "audit our SOPs," "review our procedures," "see where our SOPs stand," "organize our messy SOP library," "find SOP gaps," "score our SOP coverage," "build SOPs from what we already have," or hands over a folder of existing SOP files (Word, PDF, Markdown, Karbon templates) and asks for an assessment. Also trigger when a firm describes having outdated, scattered, or incomplete SOPs and wants a structured way to fix them. The skill produces (1) an interactive HTML coverage report with a clickable 16-domain heatmap, (2) a written gap report, (3) a reorganized SOP library folder, and (4) interview-driven captures that become new SOPs for the gaps. Do not use this skill for writing a single brand-new SOP from scratch with no existing library — use a basic SOP-authoring approach instead.
---

# SOP Library Auditor

A skill for auditing an accounting firm's existing SOP library against a structured framework, producing a clickable coverage report, and conducting interviews to fill the identified gaps. Built on the AI-Ready SOP Framework: 16 domains organized across 5 operating layers (Value chain, Production, Quality, Enablement, Governance), the 15-field anatomy template, 3-state coverage scoring with a 5-axis maturity drill-down, and composite priority bucketing into 30/60/90/180-day roadmap stages.

## When to use this skill

Trigger this skill any time a 1–100-person accounting, bookkeeping, or CAS firm wants help with their **existing** SOP library — not when they want a single SOP written in isolation. The hallmarks of a good fit:

- "Our SOPs are a mess and out of date."
- "We have a folder of procedures but no idea what's missing."
- "Can you organize and score what we have?"
- "We need a roadmap for what to document next."
- "Help us turn our existing SOPs into something AI can use."

## What this skill produces

By the end of a session, the firm walks away with four artifacts saved to their working folder:

1. **`sop-dashboard.html`** — a self-contained interactive coverage report they can open in any browser. Headline: 3-state status (Complete / Partial / Missing / N/A) for each of 16 domains, an at-a-glance stat strip, a clickable heatmap, a per-SOP 15-field anatomy grid, a prioritized gap table with filter pills, and a per-SOP 5-axis maturity drill-down accessed by clicking any SOP name.
2. **`sop-gap-report.md`** (or `.docx` if requested) — a written report with executive summary, methodology, coverage by layer, compliance posture, domain-by-domain findings, prioritized 30/60/90/180-day roadmap, and recommended next steps.
3. **`SOP-Library/`** — a reorganized folder mirroring the 16-domain taxonomy, with the firm's existing SOPs filed and renamed to a consistent convention (D{NN}-{kebab-case-title}.{ext}).
4. **`interview-captures/`** — structured Markdown captures from the per-gap interviews. **These captures ARE the new SOPs.** The skill never speculates or auto-drafts SOPs from templates without interviewing the firm first. The firm's actual answers become the procedure content, formatted into the 15-field anatomy template.

## Workflow at a glance

The skill runs through seven stages in order. Stages 1–4 must complete before Stage 5+ — the dashboard cannot be built without a scored inventory, and per-gap interviews can't be prioritized without knowing what gaps exist. Stages 6 and 7 run alongside each per-gap interview.

| Stage | What happens | Reference doc |
|---|---|---|
| 1. Intake | 12-question firm-profile interview | `references/intake-interview.md` |
| 2. Inventory | Read existing SOPs from folder, uploads, or verbal description | `scripts/parse_sops.py` |
| 3. Classify & Score | Map each SOP to a domain (1–16); score 15-field anatomy and 5-axis maturity; identify gaps against size-tier expected set | `references/framework.md`, `references/scoring-rubric.md`, `references/size-tier-expected-sets.md` |
| 4. Coverage report | Render the interactive HTML | `assets/dashboard.html` |
| 5. Reorganize | Build `SOP-Library/` mirroring the 16-domain taxonomy; file existing SOPs by copy | `references/framework.md` |
| 6. Per-gap interviews | For each priority gap, run a structured interview that captures the firm's actual procedure into 15-field anatomy | `references/sop-interview-bank.md`, `references/sop-template.md` |
| 7. Gap report | Produce the written report | `assets/gap-report-template.md` |

## Stage 1 — Intake interview

Start every session with the 12-question intake. **Do not skip this** — every downstream stage depends on the firm's size, service mix, tech stack, and goals. A 10-person CAS-focused firm needs a different expected SOP set than a 3-person bookkeeper; without intake, the skill cannot tell which "missing" SOPs are actual gaps versus correctly out of scope.

Read `references/intake-interview.md` for the full question set. Use AskUserQuestion for the size band, service-mix tiers, and security-posture state. Use natural conversation for free-form answers (pain points, strategic goal). Group related questions to reduce friction.

Save the firm profile to `working/firm-profile.md` as you collect answers.

## Stage 2 — SOP inventory

Three intake modes:

**Mode A — Folder.** Firm points the skill at a directory. Use `scripts/parse_sops.py` to walk it, extract text from `.md`, `.docx`, `.pdf`, `.txt`, and emit JSON inventory.

**Mode B — Individual uploads.** Read each file with the Read tool.

**Mode C — Verbal description.** Capture each item with `coverage: described_only`. Counts toward existence but scores low on other axes until content is supplied.

Most firms mix modes. Build one combined inventory.

## Stage 3 — Classify and score

For every inventory item:

**Classify.** Map each existing SOP to a domain (1–16) and layer using `references/framework.md`. If a single document covers multiple domains (e.g., "Bookkeeping Manual" covering AP + AR + reconciliations), split into multiple inventory entries pointing at the same source file and tag with `scope`.

**Score, two views computed simultaneously:**

1. **Headline — 3-state coverage + 15-field anatomy.** For each existing SOP, score the 15 fields (each 0/1/2) for an anatomy total of 0–30. Each domain gets a single status: Complete / Partial / Missing / N/A based on its mapped SOPs and the anatomy of the strongest. See `references/scoring-rubric.md` for the rules.

2. **Secondary — 5-axis maturity (0–10).** Existence, Currency, Coverage, AI-readiness, Adoption — each 0–2. Per-SOP and per-domain. Surfaced in the dashboard as a per-SOP drill-down (click any SOP name).

Then identify **missing** SOPs (existence = 0) by comparing the classified inventory against the expected set for the firm's size tier (`references/size-tier-expected-sets.md`).

For every gap (missing SOP OR existing SOP < 7/15 anatomy OR flagged `crit`), compute a **composite priority** = Risk + Frequency + Impact + Effort (each 1–3; effort is inverted so 3 = low effort = quicker win). Range 4–12.

Bucket gaps into 30 / 60 / 90 / 180-day roadmap stages by composite score and compliance-floor status. Strategic-goal weights from intake Q12 promote gaps up a bucket per the rules in `scoring-rubric.md`.

Save scores to `working/sop-inventory.json`.

## Stage 4 — Coverage report

Read `assets/dashboard.html` — it's a self-contained HTML template with placeholder JSON. Replace the placeholder with the firm's actual scored inventory and write the result to `sop-dashboard.html` in the firm's working folder.

The dashboard renders:
- Header with firm name, generation date, document/SOP/draft counts, overall coverage percentage
- "At a glance" stat strip (complete / partial / missing domains, critical compliance gaps, stuck-in-draft, stale)
- 16-domain heatmap in 8 columns, color-coded by status, click-to-drill
- Per-domain detail panel (mapped SOPs, anatomy scores, identified gaps)
- Prioritized gap table with filter pills (30/60/90/180-day, risk-high, effort-low, compliance floor)
- 15-field anatomy completeness grid — one row per SOP, one column per field, ● ◐ ○ at a glance
- Click any SOP name to open a 5-axis radar drill-down modal
- Recommended starting point callout
- Footer note pointing back at the working folder

The HTML uses Chart.js from CDN for the radar (renders only when modal opens). No build step. Firm can email it, post to SharePoint, or open offline.

After writing, confirm with the user it looks right before moving on. Provide a `computer://` link.

## Stage 5 — Reorganize the library

Create the directory structure inside the firm's working folder, organized by layer:

```
SOP-Library/
├── A-Value-Chain/
│   ├── D01-Client-Lifecycle/
│   ├── D02-Document-Data-Collection/
│   └── D03-Pricing-Billing/
├── B-Production/
│   ├── D04-Transaction-Processing/
│   ├── D05-Reconciliations/
│   ├── D06-Period-End-Close/
│   ├── D07-Financial-Reporting/
│   ├── D08-Payroll-Sales-Tax/
│   └── D09-Advisory-CAS/
├── C-Quality/
│   ├── D10-QC-Review/
│   └── D11-Workflow-Practice-Mgmt/
├── D-Enablement/
│   ├── D12-Tech-Stack-Integrations/
│   ├── D13-People-Training-RACI/
│   └── D14-Internal-Firm-Operations/
├── E-Governance/
│   ├── D15-Risk-Compliance-Security/
│   └── D16-AI-Agentic-Workflows/
└── _index.md
```

For every existing SOP in the inventory, copy (don't move — preserve originals) the file into its mapped domain folder, renamed `D{NN}-{kebab-case-title}.{ext}`. Use Bash for file ops.

Generate `_index.md` listing every SOP with status, anatomy score, owner, last-reviewed date, and the gap list at the bottom. This is the firm's master index.

If a single source document was split into multiple inventory entries (Stage 3), copy it into the primary domain and add cross-reference notes in `_index.md`.

## Stage 6 — Per-gap interviews

For every gap (missing SOP OR existing SOP < 7/15 anatomy), run an interview that captures enough content to populate the 15-field anatomy template. Process gaps in priority order — the dashboard's gap list is sorted by composite priority.

**Critical rule: do not write speculative SOP drafts.** The user has been clear that interviews are how SOPs get written in this skill. Never pre-fill content based on what a typical firm would do — only write what the firm actually says.

For each gap:
1. Confirm with the firm: interview now, defer, or skip.
2. If "now": load the relevant question bank from `references/sop-interview-bank.md` (per-domain) plus the universal questions.
3. Conduct the interview. Use AskUserQuestion sparingly — most SOP content is free-form. Ask 2–4 questions per turn.
4. After enough content is gathered, write the captured SOP to `interview-captures/D{NN}-{kebab-title}.md` using the 15-field template (`references/sop-template.md`). Fill only fields the interview produced content for; mark missing as `[NEEDS INPUT]` (firm needs to look something up) or `[NEEDS POLICY DECISION]` (firm needs to make a call).

Long sessions are expected. Offer to pause and resume — save state to `working/session-state.json`.

When a per-gap interview is complete enough to be a working SOP (typically when fields 1, 2, 3, 5, 6, 7, 8, 9, 10 are filled), the captured file IS the firm's new SOP.

## Stage 7 — Final gap report

When the firm signals they're done, produce `sop-gap-report.md` (offer `.docx` if preferred). Use `assets/gap-report-template.md` as the structure. Includes: executive summary, methodology, coverage by layer table, compliance posture table, domain-by-domain findings, recommended starting point, prioritized 30/60/90/180-day roadmap, captures list, maintenance cadence, and next steps.

Provide `computer://` links to all four deliverables (dashboard, report, library folder, captures folder) at the end.

## Scope rules

**Do.** Audit and organize an existing library; conduct interviews to fill gaps; produce dashboards and reports; flag regulatory exposure; rename and refile files (by copy).

**Do not.** Write speculative SOP content without interviewing. Modify or destroy original SOP files (always copy). Make claims about regulatory compliance unsupported by the firm's own evidence (e.g., "you're SOC 2 compliant" — the skill flags whether documented controls exist, not audit fitness). Pretend to substitute for legal/compliance counsel. The 3-state and 5-axis scores are heuristics, not audit opinions — say so when delivering them.

## Working files vs. deliverables

The skill creates a `working/` directory inside the firm's folder for intermediate state (`firm-profile.md`, `sop-inventory.json`, `session-state.json`). This is the skill's scratchpad. The four numbered deliverables in "What this skill produces" are what the firm consumes.

Don't show the user `working/` files unless they ask.

## Reference files

Read these as needed during the relevant stage. Don't preload them all — that wastes context.

- `references/framework.md` — 16 domains × 5 layers taxonomy. Load during Stage 3.
- `references/intake-interview.md` — 12 firm-profile questions. Load during Stage 1.
- `references/scoring-rubric.md` — 3-state coverage, 15-field anatomy, 5-axis maturity, composite priority, 30/60/90/180-day buckets. Load during Stage 3.
- `references/sop-template.md` — 15-field SOP capture template. Load during Stage 6.
- `references/ai-readiness.md` — AI-eligibility tagging and Tier 1–4 automation candidates. Load during Stage 6 if firm wants AI tagging in their captures.
- `references/size-tier-expected-sets.md` — Expected SOP sets per size tier. Load during Stage 3.
- `references/sop-interview-bank.md` — Per-domain interview question banks. Load during Stage 6.
- `references/compliance-quickref.md` — WISP / IRS Pub 4557 / FTC Safeguards / SSARS / SQMS / §7216. Load during Stage 7.

## Assets

- `assets/dashboard.html` — Self-contained HTML coverage report template. Replace placeholder DATA at runtime.
- `assets/gap-report-template.md` — Markdown gap report structure with placeholders.

## Scripts

- `scripts/parse_sops.py` — Walks a folder, extracts text from `.md`/`.docx`/`.pdf`/`.txt`, emits JSON inventory. Run with `python parse_sops.py <folder> <output.json>`.

## Closing thought

The point of the framework is not bureaucratic completeness. A 3-person firm with 10 survival SOPs at Complete coverage is more mature than a 30-person firm with 80 SOPs all stuck at Partial. Score honestly, prioritize ruthlessly, interview thoroughly, and resist the urge to fabricate content.
                                                                                                                                                 