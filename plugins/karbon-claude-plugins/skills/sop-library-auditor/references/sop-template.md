# 15-Field SOP Template

Use this template for every captured-from-interview SOP. Save captures to `interview-captures/D{NN}-{kebab-title}.md` where `{NN}` is the domain number from the 16-domain framework.

The 15 fields match the anatomy-scoring grid in the dashboard. Each field present and substantive = 2 points (●), partial = 1 point (◐), missing = 0 points (○). A complete SOP scores 30/30 (15/15 in simplified display).

**Critical rule:** Only fill fields with content the firm actually provided during the interview. Mark any field without firm-provided content as `[NEEDS INPUT]` so the firm sees exactly where their tribal knowledge still lives. Never speculate, never infer, never copy text from a "typical firm" template.

---

## The template

```markdown
---
# Field 1: Title and ID — required, fill from interview
sop_id: D06-monthly-close-service-smb
title: Monthly Close — Service-Based SMB
version: 1.0
status: draft               # draft | working | active | deprecated
domain: 6                   # 1–16, matches framework.md
layer: Production           # Value chain | Production | Quality | Enablement | Governance
last_reviewed: 2026-04-29
review_cadence: quarterly   # or whatever the firm said
risk_level: medium          # low | medium | high

# Field 4: Owner — single named person, not "the firm"
owner: [name from interview]

# Field 6: Frequency / trigger
frequency: monthly
trigger: 1st business day after month-end

# Field 12: Tools, templates, prompts (named, not feel)
tools: [QuickBooks Online, Karbon, Keeper, Fathom, Relay]
templates: [/templates/close-checklist.xlsx, /templates/flux-narrative.md]

# Field 13: Authority / standard references
authorities: [AICPA SSARS 21-25, IRS Pub 4557, internal QC policy v3]

# Field 15: AI usage (model, prompts, prohibitions, checkpoints)
ai_usage:
  used: true
  models: [Claude Sonnet 4.6, Karbon AI Agents]
  prompts: [/prompts/flux-draft.md, /prompts/categorization-confidence-check.md]
  prohibited: [final partner sign-off, SSARS attestation language]
  human_checkpoints: [step 9.1 reviewer sign-off, step 9.6 partner sign-off]

prerequisites: [D04-vendor-master-hygiene, D05-bank-rec]
description: >
  [One-paragraph plain-English summary written from interview answers.]
---

# Field 2: PURPOSE
[Why this SOP exists, what business outcome it produces, and the cost of doing it wrong — in the firm's own words from the interview. If they didn't articulate a purpose, ask before filling.]

# Field 3: SCOPE & EXCLUSIONS
[Which client types, entity types, software stacks, revenue ranges this applies to. Explicit non-applicability list. From interview question "When does this NOT apply?"]

# Field 5: ROLES & RACI
| Step bucket | [role 1] | [role 2] | [role 3] | Client | AI Agent |
|---|---|---|---|---|---|
| [bucket 1] | R | C | A | I | R (assist) |
| [bucket 2] | R | A | C | C | R (draft only) |

(R = Responsible, A = Accountable, C = Consulted, I = Informed)

[Use the firm's actual role names — "Bookkeeper Tier 2," "Senior Reviewer," whatever they said. Don't generic-ify.]

# Field 7: INPUTS (structured)
- [input_1_name]: [file format], [source], [timing]
- [input_2_name]: [file format], [source], [timing]

[List every artifact the procedure needs to start. Interview question: "What do you need on your desk before you can start this?"]

# Field 8: OUTPUTS (structured)
- [output_1_name]: [destination], [recipient]
- [output_2_name]: [destination], [recipient]

[List every artifact the procedure produces. Interview question: "When you finish, what do you hand off and to whom?"]

# Field 9: STEP-BY-STEP PROCEDURE
Each step uses this sub-structure:

## Step 9.1 — [Step name from interview]
- **Actor:** [role]  [AI: ai_eligibility tag from field 15]
- **Tool:** [named tool]
- **Action:** [what gets done, in plain language from interview]
- **Validation:** [how the actor knows they did it right]
- **Decision logic** *(field 10)*:
  - IF [condition with threshold] → [action]
  - IF [condition with threshold] → [action]
  - ELSE → [default]
- **Exception examples** *(field 11)*: [edge cases the firm has hit in real life]
- **Evidence to capture:** [what to save and where]

[Repeat for every step. The number of steps comes from the interview — don't pad.]

# Field 10: CONTROLS (with materiality thresholds)
[Explicit control language with numbers. Examples:
- "Unreconciled difference > $10 → escalate to Senior."
- "Variance > 5% on any P&L line → flux narrative required."
- "JE > $500 requires controller approval."
The threshold MUST be specific. "Use judgment" or "if material" is a 0.]

# Field 11: EXCEPTIONS AND ESCALATION
[Each enumerated exception gets its own playlet:
- **Symptom** — what the actor observes
- **Diagnosis** — likely cause
- **Action** — what to do
- **Escalation** — when to bump up, to whom, by when

Pull these from the interview question "What weird stuff happens here that nobody talks about? Tell me about the last three times this didn't go cleanly."]

# Field 12: TOOLS, TEMPLATES, PROMPTS
- Tools: [list with versions where relevant — "QBO Online (not Desktop)", "Karbon March 2025+ UI"]
- Templates: [file paths]
- Prompts: [file paths to AI prompts; or inline if short]
- Macros / scripts: [file paths]

# Field 13: AUTHORITY / STANDARD REFERENCES
- [IRS Pub 4557 controls invoked]
- [SSARS framework applied (preparation engagement / compilation / review)]
- [WISP cross-references]
- [Internal policy references]

# Field 14: REVIEW CADENCE AND CHANGELOG
**Review cadence:** [quarterly / annually / on-trigger]
**Trigger events forcing review:** [regulation change, tool change, incident]

| Version | Date | Author | Change |
|---|---|---|---|
| 1.0 | 2026-04-29 | [interviewee] | Initial capture from interview |

# Field 15: AI USAGE — DETAIL
**Models in use for this SOP:** [list]
**Where AI is used:**
- Step [n]: [what AI does, what tier (`ai_assisted` / `ai_executed` / `ai_proposes`)]

**Prompts:** [paths or inline]

**Prohibitions:**
- [List of things this SOP MUST NOT delegate to AI — partner sign-off, SSARS attestation, conflict-of-interest decisions, fraud escalation, fee-collection negotiations]

**Human checkpoints:**
- [Step n] — Reviewer must approve AI output before [downstream action]

**Logging:**
- [Where AI runs are logged for evals and audit]

If AI is **not used** in this SOP, this field still must say so explicitly: "AI is not used in this procedure. All steps are `human_only` or `client_action`." This is a 2 (●), n