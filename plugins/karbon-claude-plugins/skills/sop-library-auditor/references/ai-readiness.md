# AI-Readiness Tagging

This guide explains how to tag steps in a captured SOP for AI-eligibility, and how to advise the firm on which SOPs are highest-priority for AI automation.

## The 5-tag controlled vocabulary

Every step in Section 9 of the 14-section template gets exactly one tag. Use this small, fixed vocabulary — don't invent new tags.

- **`human_only`** — Judgment, client-facing communication, partner sign-off, regulatory attestation, fee negotiations. Cannot be delegated.
- **`ai_executed`** — Fully delegated to an agent. High volume, rules-based, low-judgment work where the agent has the data and the rules to act. (Example: categorizing a known-vendor transaction with high confidence.)
- **`ai_assisted`** — Agent drafts, human reviews and approves before action takes effect. The most common pattern. (Example: agent reconciles, human signs off.)
- **`ai_proposes`** — Agent surfaces a question or exception for a human to decide; the agent does not act. (Example: agent flags an unusual vendor charge for the controller to review.)
- **`client_action`** — The ball is in the client's court. Not a firm staff action and not an AI action.

A reasonable rule of thumb (validated by Digits' "zero-touch transaction" model and Karbon AI Agents):
- Anything **repetitive, rules-based, low-judgment, high-volume** → `ai_executed` or `ai_assisted`.
- Anything **regulatory sign-off, client trust, material judgment** → `human_only`.

## How to tag during a per-gap interview

If the firm has signaled in intake (Q9) they're interested in AI tooling, ask one tagging question per step:

> "When you describe step [name], who's actually doing it today — and could you imagine a piece of software doing the bulk of it with someone reviewing?"

The answer maps cleanly:
- "I do it and only I should do it" → `human_only`
- "Someone could do it but a senior reviews" → `ai_assisted`
- "We already have a rule, the rule applies" → `ai_executed`
- "We just want to know when it happens, then we decide" → `ai_proposes`
- "We're waiting on the client" → `client_action`

If the firm hasn't signaled AI interest, skip per-step tagging — don't impose it. Default the YAML `ai_eligibility` field to `hybrid` and move on.

## AI-automation candidate tiers

When recommending which SOPs to AI-enable first, use these tiers (drawn from Digits, Karbon AI Agents, Botkeeper, Aider, and Intuit CAS Foundations):

### Tier 1 — Highest leverage (build AI workflows here first)

1. Transaction categorization & bank-feed coding (vendors claim 95%+ auto-booking)
2. Bank/credit-card reconciliation & exception flagging
3. Document extraction (bills, receipts, statements) — OCR + categorization
4. Uncategorized transaction follow-up with clients (magic-link templates)
5. 1099 vendor identification & W-9 chase
6. Sales-tax filing prep (rate updates, jurisdiction tie-out)
7. AR collections cadence (automated reminders, escalations)
8. Payroll pre-run checklist & exception detection

### Tier 2 — High leverage with human review

9. Month-end close checklist orchestration
10. Flux/variance analysis & narrative drafting
11. KPI dashboard refresh & commentary draft
12. Client onboarding document collection & tech-stack provisioning
13. Recurring journal-entry posting
14. Reconciliation tie-out workpaper assembly
15. Standard monthly reporting package generation

### Tier 3 — AI-augmented but human-led

16. Cash-flow forecast first draft
17. Budget vs. actual commentary
18. QBR prep
19. Engagement-letter & proposal drafting
20. SOP authoring itself (LLM generating SOP first drafts from screen recordings)

### Tier 4 — Keep human-only

21. Final partner sign-off / SSARS attestation
22. Client conflict-of-interest acceptance decisions
23. Termination / fee-collection negotiations
24. Whistleblower / fraud escalation
25. Tax-position judgments and tax-advice opinions

The dashboard's "automation candidates" panel ranks the firm's gaps by which tier they fall into, then by priority. The roadmap section of the gap report does the same — Tier 1 SOPs that the firm doesn't have yet are typically the fastest path to ROI.

## Caveats on vendor claims

Vendor-published automation rates (Digits' 95–98%, Karbon AI Agents' productivity claims, Aider's close-time reductions, Botkeeper's bookkeeping automation) are vendor-stated, not independently audited. Treat them as upper-bound estimates. The skill should reproduce these claims with attribution ("Digits states..." not "AI achieves...") in any output that quotes them.

The Bench Accounting collapse (December 2024) is the cautionary tale: automation without strong human oversight, data portability, and SOC 2 / IRS Pub 4557-grade controls is fragile. The skill should never recommend reducing the `human_only` set as a way to claim higher AI maturity. The Tier 4 list above is a hard floor.
