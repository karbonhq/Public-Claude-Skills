# SOP anatomy — the 15-field standard

Every SOP this skill produces uses the same fixed anatomy. The first 14 fields are the traditional structure used across AICPA, FloQast, Karbon, Numeric, and Boomer Consulting templates. The 15th field — AI usage — is the modern addition required by SQMS 1's "intellectual resources" component, NIST AI RMF, and COSO's 2026 Internal Control framework for Generative AI.

When interviewing the user in Phase 5, walk these fields in order. Skip any that genuinely don't apply, but explain why. Save the in-progress draft after every answer.

---

## 1. Title and ID

- **Title** — descriptive name (e.g., "Monthly Bank Reconciliation — Operating Account")
- **ID** — short code for cross-reference (e.g., `BK-REC-001`). Recommended pattern: `[domain code]-[process code]-[NNN]`
- **Version** — semantic version (`1.0`, `1.1`, `2.0`)
- **Effective date**

**Interview question pattern:** "What's the working name for this SOP?" Then suggest an ID based on domain mapping.

---

## 2. Purpose

One short paragraph (3-5 sentences) answering: *Why does this SOP exist? What outcome does it enable? What risk does it mitigate?*

The purpose should be outcome-focused, not activity-focused. "Reconcile the bank account" is an activity. "Ensure recorded cash matches bank balances and identify reconciling items in time to remediate before close" is a purpose.

**Interview question pattern:** "If a new hire asked you why this SOP exists, what would you say in two sentences?"

---

## 3. Scope (and explicit exclusions)

**In scope:** which clients, accounts, periods, geographies, or service tiers does this SOP cover.

**Out of scope (exclusions):** what looks like it should be in scope but isn't. Explicit exclusions are a malpractice-prevention control — CNA/AICPA Professional Liability data tie >50% of malpractice claims to missing or unclear engagement scope.

**Interview question pattern:** "Which clients or accounts does this apply to?" then "What's specifically NOT covered? (e.g., 'this does not cover client-managed credit card recs')"

---

## 4. Owner (Accountable role)

The single role — not person — who is accountable for the SOP being followed and current. Use a role name (e.g., "CAS Manager", "Bookkeeping Senior", "Firm Owner") so the SOP doesn't break when staff change.

There is exactly one Accountable owner per SOP. RACI rules: Accountable cannot be delegated.

**Interview question pattern:** "Which role is ultimately accountable that this SOP is followed and kept current? (One role only.)"

---

## 5. Performers (RACI)

The full RACI table for the work itself:

- **Responsible** — who does the work (can be multiple roles)
- **Accountable** — same as Owner above (always exactly one)
- **Consulted** — roles whose input is required before completion
- **Informed** — roles who need to know about the output

Numeric's pattern of applying RACI **at the task/step level** rather than at the SOP level is best practice for AI-augmented work — when a step involves AI, RACI should explicitly identify which substeps the AI handles vs. the human.

**Interview question pattern:** Walk each role one at a time. "Who's Responsible for actually executing this work?" "Anyone who needs to be Consulted before signoff?" "Who needs to be Informed of the output?"

---

## 6. Frequency or trigger

When does this SOP run? Two patterns:

- **Cadence-based** — daily, weekly, monthly close day +N, quarterly, annual
- **Trigger-based** — fires when [event], e.g., "when a vendor is added", "when an invoice exceeds $10,000", "on receipt of a tax notice"

Many SOPs have both (e.g., monthly cadence + ad-hoc trigger for exceptions).

**Interview question pattern:** "Is this work scheduled (e.g., monthly) or triggered by an event? Or both?"

---

## 7. Inputs

What the performer needs to start work, with the source of each input:

- Source documents (bank statements, invoices, receipts)
- System reports (GL trial balance, AR aging)
- Approvals (manager sign-off on prior step)
- Data feeds (bank feed, payroll provider sync)
- Templates (PBC list, reconciliation template)

For each input, capture: name, source, format, owner, how it arrives.

**Interview question pattern:** "What does the person doing this work need in front of them before they can start?"

---

## 8. Outputs

What the SOP produces, with the destination of each:

- Reconciled GL accounts
- Posted journal entries
- A reconciliation workpaper signed by preparer and reviewer
- A client-facing financial package
- Notifications/emails to stakeholders
- Updates to a tracking system

For each output, capture: name, destination, format, retention period.

**Interview question pattern:** "What does this SOP produce? Where does each output go and how long is it retained?"

---

## 9. Step-by-step procedure

The numbered procedure. Best practices:

- **One actor per step.** If a step requires the actor to change, split it into two steps with a handoff.
- **Verb-first.** "Pull the GL trial balance" not "The GL trial balance is pulled."
- **Reference templates and tools by name.** "Open the FloQast bank rec template" not "open the rec template."
- **Include decision points explicitly.** "If variance ≥ $1,000 OR ≥ 5%, write a flux narrative." Don't bury thresholds in prose.
- **Make handoffs explicit.** Every transition between actors gets its own step.
- **Standard-compliant verbs.** "Reconcile" implies match-to-source; "substantiate" implies validate ending balance and sign off as reviewer.

A typical SOP has 8-25 steps. Anything above 30 usually means the SOP should be split.

**Interview question pattern:** Walk the user through the steps one at a time. "What's the first thing the person doing this work does?" Then "Then what?" Repeat. Periodically summarize what's been captured to let the user spot gaps.

---

## 10. Controls (with materiality thresholds)

Controls are the parts of the SOP that prevent or detect errors. Each control has:

- **What's being controlled** (e.g., "completeness of GL coding", "approval of payment release")
- **The control activity** (review, reconciliation, approval, segregation, system block)
- **Materiality threshold** — the dollar amount or percentage that triggers escalation
- **Evidence captured** — what proves the control was performed (signoff, log entry, screenshot, system audit trail)

Common control types in CAS SOPs:

- **Four-eyes** — preparer ≠ approver (required for journal entries above threshold, payment release, period-end financials)
- **Approval thresholds** — tiered approvers by dollar amount (e.g., <$1k auto, $1k-$10k manager, >$10k partner)
- **Variance threshold** — narrative required if variance ≥ $X or ≥ Y%
- **Aging threshold** — open items > 60/90 days require escalation
- **Segregation of duties** — initiator ≠ approver ≠ payer

**Interview question pattern:** "What's the dollar threshold above which something has to be reviewed by a manager?" "How do we prove that review happened?" "What aging triggers an escalation?"

---

## 11. Exceptions and escalation

What happens when the procedure can't be followed as written:

- Common exceptions (e.g., missing source document, mismatched balance, system outage)
- Who handles each exception type
- Escalation path (preparer → senior → manager → partner) with timing
- Stop-work conditions (when to halt the process entirely)

The exception path is often the highest-risk part of an SOP because it's the least practiced. Make it as concrete as the happy path.

**Interview question pattern:** "What are the most common things that go wrong in this work?" "When something goes wrong, who decides what to do next?"

---

## 12. Tools, templates, and prompts

The systems and artifacts the SOP relies on:

- **Tools/systems** — specific software (e.g., "QBO Online Accountant", "FloQast", "Liscio", "Karbon")
- **Templates** — the named templates referenced in the procedure (link to file location)
- **Standardized prompts** — for AI-assisted steps, the exact prompt template (versioned, owned by the firm's Skills Librarian)
- **Macros / saved searches / saved reports** — any automation referenced

Treat prompts as controls. Per Trullion: "your words are the controls. Treat them like working papers: clear, precise, and ready for someone else to follow and review."

**Interview question pattern:** "What software does this work happen in?" "What templates does the person reach for?" "If AI is used, what's the prompt?"

---

## 13. Authority / standard references

The professional standards, regulations, or firm policies the SOP implements. Examples:

- AICPA SQMS Nos. 1-3 (firm-level quality management)
- AICPA SAS 146 / SSARS 21-27 (engagement-level QM)
- AICPA Code §1.295 (independence — nonattest services)
- IRS Pub 4557 (Safeguarding Taxpayer Data)
- FTC Safeguards Rule (16 CFR Part 314)
- IRC §7216 / §6713 (taxpayer information disclosure)
- NIST AI RMF / COSO ICIF for GenAI (AI governance)
- SOC 2 Trust Services Criteria
- State board rules

This field anchors the SOP to its regulatory rationale. It's the field that gets referenced during peer review, audit, or litigation.

**Interview question pattern:** "What standards or regulations is this SOP implementing?" Default to suggesting the obvious ones based on the SOP topic (e.g., for a WISP-related SOP, default to IRS Pub 4557 + FTC Safeguards).

---

## 14. Review cadence and change log

- **Review cadence** — how often the SOP itself is reviewed (annual minimum; triggered by tool changes, regulatory changes, or material errors)
- **Last reviewed** — date and reviewer
- **Change log** — table of date / version / change / approver

Annual review is the floor. Trigger-based review supplements: any SOP affected by a regulatory change (SQMS effective date, SSARS 27, FTC breach-notification rule), tool migration, or post-error remediation gets reviewed immediately.

**Interview question pattern:** "How often does this SOP itself get reviewed?" Default to "annually plus on triggers" unless the SOP is in a high-change-velocity area (e.g., AI policy, tax law).

---

## 15. AI usage (the modern addition)

Every SOP needs an explicit "human work / AI work / handoff" topology. Even SOPs where AI isn't currently used should affirmatively document that — silence is not a control.

Capture:

- **Which AI tools/models are used** — name and version (e.g., "Karbon AI", "Truewind", "Microsoft Copilot in M365 tenant", "OpenAI GPT-5 via Enterprise tier")
- **Where in the SOP** — which steps use AI (cite step numbers from §9)
- **Oversight tier** — Tier 0 Suggestion / Tier 1 Copilot/Draft / Tier 2 Bounded Autonomy / Tier 3 Full Autopilot (see `09-ai-sop-patterns.md` for definitions)
- **Prohibited inputs** — data the AI must NOT receive (PII, SSNs, full account numbers, attest-client confidential info, anything that would violate IRC §7216 without consent)
- **Review checkpoints** — the human-in-the-loop gates (approval thresholds, confidence-based routing, exception-only review, pre-delivery review)
- **Audit-trail evidence** — what's captured for retention (prompt + output + model version + timestamp + user + reviewer edits + accept/reject decision); standard retention is 7+ years to match workpaper retention
- **Prompt template references** — link to versioned prompt in the firm's prompt library
- **Client disclosure** — whether and how AI use is disclosed to the client (per engagement letter language, SOC 2 reporting, or jurisdiction-specific rules like Texas HB 149 effective Jan 1, 2026)

**Critical: design against the "HITL Fallacy."** When humans review hundreds of AI outputs daily, decision fatigue produces rubber-stamping. Right-size review burden, embed materiality thresholds, rotate reviewers.

**Interview question pattern:** "Does any AI tool touch this work? If so, where, and what's the human checkpoint?" If user says "no AI," still document that explicitly: "No AI tools currently used in this SOP. To add AI, the firm's AI Champion must (1) update this SOP, (2) approve the tool, (3) define the oversight tier."

---

## Field-level interview tips

- **Don't ask all 15 questions in one message.** One field per interaction.
- **Always offer a default grounded in the framework.** "A common default for small bookkeeping firms is monthly cadence with ad-hoc trigger for exceptions — does that fit your work?"
- **When the user is uncertain, suggest options.** Don't make them invent the answer.
- **Loop back when needed.** If the user's answer to step 9 (procedure) reveals that there's actually a $500 approval threshold they didn't mention in step 10 (controls), go back and update.
- **Surface contradictions kindly.** "Earlier you said weekly, but step 4 references the monthly trial balance — should we adjust either?"
- **Save after every answer.** No exceptions.

---

## Output format (the rendered SOP)

When all 15 fields are complete, render the SOP as a polished Word document. Section headings match the field names. Include a cover page with title, ID, version, effective date, owner role, and review cadence. Use tables for RACI, controls, change log, and AI usage. Finish with a signature block for the Accountable owner.
