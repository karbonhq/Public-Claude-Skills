# AI SOP patterns — designing SOPs for human + AI work

Load this whenever an SOP touches AI tools, prompt libraries, or agent workflows. **Most modern SOPs do, even if the user doesn't immediately think so.** Email triage, transaction categorization, flux narratives, document follow-ups, draft client communications — all are AI-assisted in many firms now.

This file complements field 15 of the SOP anatomy (AI usage). For the foundational HITL theory and oversight tiers, see also `06-layer5-governance.md` Domain 16.

---

## The five concrete implications of AI for SOP design

These shape how every modern SOP is written:

### 1. SOPs are RACI-at-task-level, not RACI-at-process-level

Numeric's pattern: explicit task-level role assignment. AI introduces a new "actor" at many specific steps. The SOP must say who (or what) is Responsible at each substep — and who reviews the AI's work.

**Example — old style:**

> "Reconciliation: Senior Bookkeeper performs and Manager reviews."

**Example — new style:**

> Step 1 (Pull GL TB): R = AI tool / A = Senior / I = none
> Step 2 (Match transactions): R = AI tool / A = Senior / C = Manager (if confidence <95%)
> Step 3 (Investigate exceptions): R = Senior / A = Senior / C = Client controller
> Step 4 (Sign off): R = Senior / A = Manager / I = Partner

### 2. Prompt libraries are first-class SOP artifacts

A firm's prompt library is part of its quality system under SQMS 1's "intellectual resources" component.

**Requirements:**

- Versioned (semantic versioning works: 1.0, 1.1, 2.0)
- Tested before promotion (golden test cases — known inputs, expected outputs)
- Attributed to a **Skills Librarian** (named role, not "everybody")
- Reviewed quarterly when models change
- Deprecated formally when no longer fit

The skill produces both the procedural SOP **and** any associated prompt templates as paired deliverables when AI is used.

### 3. Audit trails for AI-assisted work are the new working papers

Every prompt + output + model version + timestamp + user + reviewer-edit pair is evidence for:

- SQMS 1 monitoring
- FTC §314.4(h) incident response
- AICPA AS 1105 audit evidence standards

**Retention: 7+ years** to match workpaper retention.

### 4. Agent oversight requires explicit "blast radius" limits

Karbon's Agent Management System pattern is the right design pattern. SOPs should specify, **for each AI agent:**

- Which **systems** it can write to
- Which **data** it can access
- What **materiality thresholds** gate its actions
- What **escalation triggers** human review
- What **monitoring** detects drift

### 5. The "HITL Fallacy" must be designed against

When humans review hundreds of AI outputs daily, decision fatigue produces rubber-stamping.

**Design countermeasures:**

- Exception-only review (don't review what AI does well)
- Materiality-driven sampling (review N% of outputs at random, weighted by dollar impact)
- Reviewer rotation (avoid same reviewer on same output type)
- Periodic full audits to catch drift

The mature pattern is **bounded autonomy with sampled oversight**, not blanket review of every output.

---

## Oversight tier selection — choosing the right tier for the work

When designing the AI usage section of an SOP, pick the oversight tier deliberately.

| Use case | Suggested tier | Rationale |
|---|---|---|
| Drafting a client email | Tier 1 (Copilot) | Tone and accuracy matter; human always reviews |
| Categorizing transactions <$1k with high pattern match | Tier 2 (Bounded Autonomy) | Volume too high for blanket review; materiality threshold caps risk |
| Categorizing transactions >$1k or low-confidence | Tier 1 (Copilot) | Higher stakes warrant human in the draft |
| AP invoice coding (high-volume, repetitive) | Tier 3 (Full Autopilot) with sampling | Vic.ai pattern; 99% accuracy reported but sampling required for drift |
| Generating flux narratives | Tier 1 (Copilot) | Numeric's pattern; human picks language and emphasizes business context |
| Drafting reconciliation entries | Tier 1 (Copilot) | Truewind's pattern; human reviews before posting |
| Posting JEs above materiality | Never AI | Always human-initiated; AI may suggest but cannot post |
| Sending payment | Never AI | SOD requirement; payment release is always human |
| Onboarding follow-up emails | Tier 2 (Bounded Autonomy) | Templated, low-stakes, high-volume; exception-only review |
| Tax research / position drafting | Tier 1 (Copilot) max | Hallucination risk; ***Mata v. Avianca*** precedent |
| Client-facing AI outputs (any) | Tier 1 minimum + named professional sign-off | RSM's "traceable to a specific professional" rule |

**Rule of thumb:** the higher the tier, the smaller the blast radius must be (tighter materiality, narrower data access, more sampling).

---

## The 6-step structure for AI-assisted SOP procedures

When the SOP's step-by-step procedure (anatomy field 9) involves AI, structure each AI-touching step as a sub-pattern of 6 phases:

1. **Prep** — gather inputs, stage for AI (this is human work)
2. **AI** — model/tool, versioned prompt, parameters, prohibited inputs
3. **Review/edit** — factual accuracy, tone, compliance, citations (use a checklist, not vibes)
4. **Sign-off** — named accountable professional approves
5. **Logging** — capture prompt + output + edits + reviewer + timestamp
6. **Feedback** — errors feed back into prompt library or fine-tuning

This pattern repeats for every AI-touching step. Make it explicit.

---

## Standard prohibited inputs (default AI-usage list)

Unless the firm has Enterprise-tier contractual no-training guarantees AND has explicitly approved the data class, **never** input:

- Social Security numbers
- Tax Identification Numbers (full)
- Full bank account numbers
- Full credit card numbers
- Driver's license numbers
- Passport numbers
- PHI (medical records)
- Date of birth + name + address combinations
- Attest-client confidential information (independence concern)
- Trade secrets
- Anything subject to IRC §7216 without proper consent

**Approved tools list (default starting set for accounting firms):**

- **OpenAI Enterprise** (with training opt-out)
- **Microsoft Copilot in M365 tenant** (data stays in firm tenant)
- **Anthropic Claude** (Enterprise tier with no-training)
- Specialty tools with SOC 2 Type II + contractual no-training: Karbon AI, Numeric, Truewind, FloQast, Caseware AiDA, Botkeeper, Vic.ai

**Prohibited tools (default):**

- Public ChatGPT (consumer tier)
- Public Gemini, Bard, Claude.ai consumer
- Any tool without SOC 2 or no-training contract
- Any tool not approved by the firm's AI Champion

---

## STAR prompt methodology

When documenting prompts in an SOP:

- **S — Situation** — context the AI needs to understand the task
- **T — Task** — what specifically the AI is being asked to do
- **A — Action** — the steps or output format required
- **R — Refine** — how the prompt has been tested and tuned

Example documented prompt for a flux narrative:

```
[S] You are reviewing month-over-month variance in a small business P&L.
    The business is a [INDUSTRY] with [REVENUE_RANGE] in revenue.
[T] Draft a 1-paragraph flux narrative for line item [ACCOUNT] which moved
    from $X to $Y, a [PCT]% change.
[A] Reference the prior period drivers from the attached MD&A.
    Use plain business language, not accounting jargon.
    Suggest one follow-up question to ask the client owner.
[R] Tested against 12 historical variances. Reviewer edit rate: ~30% on tone,
    <5% on substance. Last validated 2026-Q1 against GPT-5.
```

---

## Audit-trail capture template

For every AI-assisted action, capture:

| Field | Example |
|---|---|
| Date/time | 2026-04-27 14:32:11 UTC |
| User | jmurphy@firm.com |
| Tool | Karbon AI (Azure OpenAI Service) |
| Model | gpt-5-2026-04 |
| Prompt template ID | PMT-FLUX-001 v1.3 |
| Inputs (links, not raw if PII risk) | gl-export-2026-03-31.xlsx (link in SmartVault) |
| Output | [link to draft narrative in workpaper] |
| Reviewer | smanager@firm.com |
| Reviewer action | Edited tone (~5 word changes); approved 14:48:03 |
| Final disposition | Posted to client package P-2026-03 |
| Retention | 7 years (matches workpaper retention) |

This is the schema that goes in the AI usage field (anatomy field 15) of every SOP that uses AI.

---

## Client disclosure considerations

When the firm uses AI in delivering services, disclosure is increasingly expected:

- **Engagement letter language** — explicit clause stating AI tools may be used in service delivery, with named tools or categories
- **SOC 2 reporting** — if the firm is SOC 2 audited, AI tooling is part of the system description
- **Jurisdiction-specific:**
  - **Texas HB 149** (effective Jan 1, 2026) — Responsible Artificial Intelligence Governance Act
  - **Utah SB 226** — disclosure requirements
  - **EU AI Act Article 14** — HITL design mandate for high-risk AI

When writing a new SOP, ask the user:

> "Does the engagement letter for clients touched by this SOP disclose AI use? If not, flag for engagement letter update — this is increasingly expected and may be required in some jurisdictions."

---

## When the user says "we don't use AI"

Document it explicitly anyway. Silence is not a control.

```
## AI usage

No AI tools currently used in this SOP.

To add AI to this SOP in the future:
1. The firm's AI Champion must approve the tool (must be on the approved tools list)
2. The oversight tier must be specified
3. This SOP must be updated to reflect the AI step
4. Audit-trail capture must be enabled
5. Client disclosure must be reviewed
```

This converts "we don't use AI" from an unstated assumption into a documented control.
