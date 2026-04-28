---
name: sop-architect
description: Review, organize, and fill gaps in an accounting/bookkeeping/CAS firm's standard operating procedures (SOPs). Use whenever the user wants to audit existing SOPs, build an inventory, identify gaps, prioritize what to document next, or write a new SOP from scratch through a guided one-question-at-a-time interview. Trigger on phrases like "review my SOPs", "audit our SOPs", "find gaps in my SOPs", "organize our SOPs", "what SOPs am I missing", "build an SOP for X", "interview me to write an SOP", "document our [close/onboarding/billing/etc.] process", or whenever the user uploads SOP documents and asks for analysis. Tailored for small (1-10 staff) bookkeeping and CAS-focused firms; reference docs cover all 16 domains across 5 layers from the master SOP framework.
---

# SOP Architect

A skill for reviewing, organizing, and building out the SOP library of an accounting / bookkeeping / Client Accounting & Advisory Services (CAS) firm. The skill is grounded in a 16-domain master taxonomy (5 layers: client value chain, production, quality, enablement, governance) and a 15-field SOP anatomy that becomes the default output shape for every SOP.

The skill operates in five sequential phases. Move through them in order unless the user explicitly jumps to a later phase.

---

## When to use this skill

Use it when the user asks for any of the following (this list is illustrative, not exhaustive):

- "Review my SOPs" / "audit our SOPs" / "where are the gaps in my SOPs"
- "Organize our SOPs" / "I have a bunch of SOPs and need to make sense of them"
- "What SOPs am I missing" / "what should we document next"
- "Build an SOP for [X]" / "interview me to write an SOP for [X]"
- "Document our [close / onboarding / billing / collections / 1099 / WISP / AI usage] process"
- The user uploads one or more SOP documents and asks for analysis or improvement
- The user mentions firm operations documentation, process improvement, or knowledge transfer

---

## Reference documents — load on demand

Do **not** load all reference docs at the start. Load them only when the workflow phase or the user's question requires them. Each reference is self-contained.

| File | Load when |
|---|---|
| `references/00-sop-anatomy.md` | Always load before Phase 5 (interview mode). Defines the 15-field SOP structure. |
| `references/01-taxonomy-overview.md` | Always load at the start of Phase 2 (mapping). High-level index of all 16 domains. |
| `references/02-layer1-client-value-chain.md` | When mapping or building SOPs in Domains 1-3 (lifecycle, document collection, pricing/billing). |
| `references/03-layer2-production.md` | When mapping or building SOPs in Domains 4-9 (transactions, recs, close, reporting, payroll/sales tax, CAS). |
| `references/04-layer3-quality.md` | When mapping or building SOPs in Domains 10-11 (QC/review, workflow/practice management). |
| `references/05-layer4-enablement.md` | When mapping or building SOPs in Domains 12-14 (tech stack, people/RACI, internal ops). |
| `references/06-layer5-governance.md` | When mapping or building SOPs in Domains 15-16 (risk/compliance/security, AI/agentic workflows). |
| `references/07-maturity-models.md` | During Phase 3 (gap analysis) and Phase 4 (prioritization). |
| `references/08-gap-analysis-methods.md` | During Phase 3 (gap analysis). |
| `references/09-ai-sop-patterns.md` | When any SOP touches AI tools, prompt libraries, or agent workflows (almost every modern SOP). |
| `references/10-small-cas-firm-priorities.md` | Always load in Phase 4 (prioritization). The user's firm profile (small + bookkeeping/CAS) makes this the primary priority lens. |

Templates live in `templates/` and are copied into the working outputs folder at runtime — they are not loaded into context.

---

## Phase 1 — Inventory

**Goal:** build a complete catalog of every existing SOP the firm has.

The user may provide SOPs in many forms: a folder path, individual file uploads (.docx, .pdf, .md, .txt), pasted text, screenshots, or verbal descriptions. Accept all of them.

For each SOP found, capture:

1. **Name** — the title or working name of the SOP
2. **Source** — where it was found (file path, upload, pasted text, etc.)
3. **Last modified / last reviewed** — if available
4. **Format** — current file format (docx, pdf, markdown, etc.)
5. **One-line summary** — what the SOP covers
6. **Owner** (if stated) — the firm role accountable for the SOP
7. **Raw extracted content** — the actual text, for use in Phase 2 mapping

Save the inventory as `sop-inventory.md` in the user's outputs folder using the template at `templates/inventory-tracker-template.md`. Update this file incrementally as new SOPs are discovered.

If the user provides only a folder path, read the directory listing first, then read each SOP file in turn. For .docx and .pdf files, use the bash shell to extract text (e.g., `pandoc`, `pdftotext`, or Python with `python-docx` / `pypdf`).

When inventory is complete, summarize what you found in chat — counts by format, an overview of likely topics — and ask the user to confirm before moving to Phase 2.

---

## Phase 2 — Map to taxonomy

**Goal:** assign every cataloged SOP to one or more of the 16 domains so coverage gaps become visible.

Load `references/01-taxonomy-overview.md` first. For each domain that has matching SOPs, also load the corresponding layer reference doc (e.g., for Domain 6 month-end close, load `references/03-layer2-production.md`).

For each SOP in the inventory:

1. Identify the **primary domain** it belongs to (one of the 16)
2. Identify any **secondary domains** it touches (cross-cutting SOPs are common)
3. Compare the SOP's content against the 15-field anatomy from `references/00-sop-anatomy.md` and note which fields are present, partial, or missing
4. Flag any of: **duplicate** (multiple SOPs covering the same ground), **orphan** (the SOP describes work no one currently does), **stale** (last updated >12 months ago, or references obsolete tools/standards), **scope-mismatch** (single SOP covering work that should be split across multiple domains)

Update `sop-inventory.md` with the mapping. Then summarize in chat:

- Coverage by domain (which domains have SOPs, how many, how complete)
- Any SOPs flagged as duplicate / orphan / stale / scope-mismatch
- Any SOPs you couldn't confidently map (ask the user to clarify)

Confirm with the user before moving to Phase 3.

---

## Phase 3 — Gap analysis & coverage report

**Goal:** produce a clear picture of what's missing, what's thin, and what's complete — and deliver an interactive HTML coverage report the user can revisit.

Load `references/07-maturity-models.md`, `references/08-gap-analysis-methods.md`, and `references/10-small-cas-firm-priorities.md`.

For each of the 16 domains, classify coverage as:

- **Complete** — at least one SOP exists, all 15 anatomy fields are populated, the SOP is current (<12 months) and matches firm scope
- **Partial** — an SOP exists but is missing fields, is stale, or covers only part of the domain's scope for the firm
- **Missing** — no SOP exists, but one is needed at this firm's maturity level
- **N/A** — domain doesn't apply to this firm (e.g., audit-specific SOPs for a non-attest firm)

For each Partial or Missing classification, capture:

- **What's missing** — specific deliverables, controls, or sub-processes
- **Risk** — High / Medium / Low, with a one-line rationale (compliance exposure, financial impact, key-person dependency, client-facing risk, etc.)
- **Frequency** — how often the underlying work happens (daily, monthly, annual, ad-hoc)
- **Dependency on other SOPs** — does fixing this require other SOPs to be in place first

Save a working markdown gap matrix at `sop-gap-matrix.md` using `templates/gap-priority-matrix-template.md`.

**Then build the interactive HTML coverage report.** This is a key deliverable — a self-contained HTML file the user can open in a browser, click into each domain, see SOPs mapped there, view a visual heatmap of coverage, and filter the priority list. Save it to the user's workspace folder so it persists.

The HTML report should include:

1. **Header bar** — firm name (ask the user), date generated, total SOPs in inventory, overall coverage percentage
2. **Coverage heatmap** — 16 cells (one per domain), color-coded green/yellow/red/grey for Complete/Partial/Missing/N/A, clickable
3. **Domain detail panel** — when a domain is clicked, show the SOPs mapped to it, their anatomy completeness, and any gaps
4. **Priority list** — ranked gaps (filterable by risk, frequency, layer)
5. **Anatomy completeness table** — per-SOP scoring of which of the 15 fields are present

Use vanilla HTML/CSS/JS — no external dependencies — so the file works offline. Save to the workspace folder as `sop-coverage-report-[YYYY-MM-DD].html` and provide a `computer://` link.

---

## Phase 4 — Prioritization plan

**Goal:** turn the gap list into a ranked, actionable plan for which SOPs to write next.

Load `references/10-small-cas-firm-priorities.md` if not already loaded. This document encodes the priority lens for a small (1-10 staff) bookkeeping/CAS firm — generally the order is: (1) compliance/security gaps that create legal exposure, (2) revenue-leak gaps (scope creep, billing, collections), (3) core production gaps (close, recs, onboarding) where errors hit clients, (4) quality and capacity gaps, (5) AI/governance gaps, (6) strategic/advisory gaps.

Score each gap on:

- **Risk** (High / Medium / Low) — compliance, financial, reputational
- **Frequency** (High / Medium / Low) — how often the work happens
- **Impact if undocumented** (High / Medium / Low) — error rate, client exposure, key-person risk
- **Effort to write** (High / Medium / Low) — based on complexity and whether other SOPs are dependencies

Present the prioritized list in chat as a ranked table with a one-line rationale per gap. Group into:

- **Immediate (do in next 30 days)** — typically 3-5 SOPs
- **Near-term (next 90 days)** — typically 5-10 SOPs
- **Backlog** — everything else

Ask the user which SOP they want to start writing first. Then move to Phase 5.

---

## Phase 5 — Interview mode (one question at a time)

**Goal:** walk the user through the 15-field SOP anatomy one question at a time and produce a polished `.docx` SOP at the end.

Load `references/00-sop-anatomy.md`. For SOPs that touch AI, also load `references/09-ai-sop-patterns.md`. For domain-specific guidance (e.g., engagement letter clauses, reconciliation thresholds), load the matching layer reference.

**Critical interview rules:**

1. **One question at a time.** Ask, wait for answer, save, ask the next. Never bundle questions.
2. **Adaptive and conversational.** Use plain language. Suggest defaults grounded in the framework where appropriate (e.g., "common practice for small firms is monthly review — does that fit?"). Skip fields that don't apply and explain why. Loop back if an earlier answer changes the context for a later field.
3. **Save after every answer.** After each user response, append to the in-progress markdown file at `sop-draft-[sop-name].md` in the outputs folder. The user must be able to stop mid-interview and resume later.
4. **Anchor in the framework.** Every field should be informed by the relevant reference doc. Cite specific authorities (AICPA SQMS, IRS Pub 4557, FTC §314, IRC §7216, NIST AI RMF, etc.) where the SOP is touching regulated subject matter.
5. **Don't skip the AI usage section.** Every modern SOP needs a "human work / AI work / handoff" topology. Use `references/09-ai-sop-patterns.md` to frame this.

Walk the 15 fields in this order (the structure from `references/00-sop-anatomy.md`):

1. Title and ID
2. Purpose
3. Scope (and explicit exclusions)
4. Owner (Accountable role)
5. Performers (RACI — Responsible, Consulted, Informed)
6. Frequency or trigger
7. Inputs
8. Outputs
9. Step-by-step procedure
10. Controls (with materiality thresholds)
11. Exceptions and escalation
12. Tools, templates, and prompts
13. Authority / standard references
14. Review cadence and change log
15. AI usage (model, prompts, prohibitions, review checkpoints, audit-trail evidence)

When all fields are answered, summarize the draft back to the user for sign-off. Once approved, render the SOP to a polished `.docx` using the `docx` skill. Save the final `.docx` to the workspace folder as `SOP-[name]-[YYYY-MM-DD].docx` and provide a `computer://` link.

After the SOP is delivered, ask whether the user wants to start the next SOP from the prioritized backlog (Phase 4 list) or stop.

---

## File outputs reference

| Path | What it is | When written |
|---|---|---|
| `[outputs]/sop-inventory.md` | Working inventory tracker, updated incrementally | Phase 1, updated in Phase 2 |
| `[outputs]/sop-gap-matrix.md` | Working gap matrix | Phase 3 |
| `[workspace]/sop-coverage-report-[date].html` | Interactive HTML coverage report (final deliverable) | End of Phase 3 |
| `[outputs]/sop-draft-[name].md` | In-progress SOP markdown, updated after each interview answer | Phase 5 |
| `[workspace]/SOP-[name]-[date].docx` | Final polished SOP (deliverable) | End of Phase 5 |

---

## Maturity defaults for the user's firm

The user has indicated a **small (1-10 staff), bookkeeping / CAS focused** firm. Apply these defaults unless the user states otherwise:

- Treat tax-attest-specific SOPs (audit fieldwork, Yellow Book, etc.) as N/A unless the user confirms attest work
- Apply the SQMS firm-level obligations even for CAS-only practices (the standards inherit at firm level)
- Default to FTC Safeguards small-entity exemption applicability (NPPI on <5,000 consumers) — but verify with the user
- Default WISP/Pub 4557 obligations as in-scope if the firm holds any PTINs or prepares any tax returns
- Default to "we use AI tools" — load `references/09-ai-sop-patterns.md` proactively when any SOP touches a workflow where AI is plausibly used

---

## What this skill is NOT

- It is not a tax research tool — for substantive tax positions, defer to authoritative sources
- It is not a peer review tool — it produces internal SOPs, not peer-review documentation
- It is not a substitute for legal review of engagement letters, WISPs, or other contracts — flag these for attorney/CAMICO review when generated
- It does not write SOPs unilaterally — every SOP comes from the user via interview, with the framework as scaffolding
