# Per-Domain Interview Question Banks

Use this in Stage 6, after the dashboard identifies gaps. For each gap the firm wants to interview on, load the relevant question bank and run it conversationally.

Domain numbers refer to `framework.md` (1–16 across 5 layers).

## How to run a per-gap interview

1. **Set context.** Tell the firm what SOP you're about to capture: name, domain, layer, why it scored Partial or Missing, expected duration of the interview (15–45 minutes depending on domain).
2. **Ask for the owner.** Every SOP needs a single named owner (Field 4 of the 15-field anatomy). Confirm before starting content collection.
3. **Ask 2–4 questions per turn.** Don't dump all 15 anatomy questions at once. Group thematically: Inputs/Outputs together, Decision logic with Exceptions, RACI on its own, AI usage at the end.
4. **Push for specifics.** When a senior says "we use judgment," follow up: "OK, what's the threshold? What's an example where you applied it last month?" Tribal knowledge surfaces under pressure for examples. Field 10 (Controls with materiality thresholds) is the most common 0/2 — don't accept "if material" as an answer.
5. **Capture verbatim.** Quote the firm's actual words for decision rules and exceptions. Don't paraphrase into generic language.
6. **Write the capture.** After the interview ends, populate the 15-field template with what you got. Mark missing fields `[NEEDS INPUT]` or `[NEEDS POLICY DECISION]`.

## Universal questions (every SOP)

These map 1:1 to anatomy fields. Ask them on every interview, in approximately this order:

1. **Title and ID** — "What do you call this internally? Any abbreviation we should use as the ID?"  *(Field 1)*
2. **Owner** — "Who's the named owner — the person who reviews and signs off when this changes?"  *(Field 4)*
3. **Purpose** — "Why does this exist? What's the cost if it goes wrong?"  *(Field 2)*
4. **Scope** — "Which clients or situations does this apply to? Which ones does it NOT apply to?"  *(Field 3)*
5. **Frequency / trigger** — "When does this fire? Calendar trigger, event trigger, on demand?"  *(Field 6)*
6. **Inputs** — "Walk me through what you need on your desk before you can start."  *(Field 7)*
7. **Outputs** — "When you're done, what do you hand off and to whom?"  *(Field 8)*
8. **Procedure** — "Walk me through start to finish, in order. Pretend I'm a new senior who's never seen this before."  *(Field 9)*
9. **Controls / thresholds** — "Where in this procedure do you make a judgment call? What's the rule? What's the threshold? Give me a number."  *(Field 10)*
10. **Exceptions** — "What weird stuff happens here that nobody talks about? Tell me about the last three times this didn't go cleanly."  *(Field 11)*
11. **RACI** — "Who does what part? Walk me through R, A, C, I — responsible, accountable, consulted, informed."  *(Field 5)*
12. **Tools / templates / prompts** — "What software, files, or AI prompts are involved at each step? Name them specifically — version, date, exact file path."  *(Field 12)*
13. **Authority** — "Any standards or policies this has to comply with? IRS, AICPA, internal QC?"  *(Field 13)*
14. **Review cadence** — "How often does this get reviewed? What triggers a review?"  *(Field 14)*
15. **AI usage** — "Is AI involved anywhere here? Where? What model? What can it do, what can't it do, where do humans check?"  *(Field 15)*

The 15 universal questions cover most of any SOP. Domain-specific questions below add depth where each domain has unusual content.

---

## Domain 1 — Client Lifecycle

Add these:
- "What's the calendar-day target from signed engagement letter to first deliverable? Where do clients fall off?"
- "Walk me through the first hour of provisioning a brand-new client across QBO, Karbon, Bill.com, etc. What order, what permissions, what gets emailed?"
- "If a client terminated tomorrow, what files would you hand back, in what format, by when? Is the data portable or trapped in your tools?"
- "What's your SLA for client emails, urgent issues, and routine questions? Where does it break down?"

## Domain 2 — Document & Data Collection

Add these:
- "What's on your standard PBC list? How does it get communicated each period?"
- "What's your portal discipline — naming conventions, who uploads, who checks?"
- "When a client misses a deadline, what's the chase cadence? When do you escalate?"

## Domain 3 — Pricing & Billing

Add these:
- "When did you last raise prices? How do you decide who gets a price increase?"
- "What's your time-tracking policy? Hours, increments, notes? What's your realization target?"
- "What's your collections cadence on the firm's own AR? When do you write someone off?"

## Domain 4 — Transaction Processing

Add these:
- "What's your rules engine state — how many memorized transactions, how many uncategorized survive past 7 days?"
- "Vendor master cadence — when do you run 1099-eligibility checks? Monthly or only in January?"
- "What's the approval matrix for AP? Dollar thresholds, signers, what triggers escalation?"
- "30/60/90 collections — show me the actual email templates and call scripts."

## Domain 5 — Reconciliations

Add these:
- "What's the materiality threshold for tolerated unreconciled differences? Where does it go if not resolved?"
- "Which accounts get reconciled monthly vs. only at year-end? Why?"
- "Have you ever had a reconciliation pass with hidden plugs? How did you catch it?"

## Domain 6 — Period-End Close

Add these:
- "What's your close-cycle target in business days? Where in the cycle do you actually slip?"
- "What variance threshold triggers a flux narrative? Which line items always get a narrative regardless?"
- "Are you doing preparation, compilation, or review engagements? What's your engagement letter language?"
- "What gets done in December vs. January? What hard-locks the trial balance for tax?"

## Domain 7 — Financial Reporting

Add these:
- "Show me last month's commentary for your three biggest clients. What's formula vs. judgment?"
- "Per industry, what KPIs go on the dashboard? Where do they pull from?"
- "Are you SSARS 27 aware? How does that change your engagement language?"

## Domain 8 — Payroll & Sales Tax

Add these:
- "What gets verified before you click run on payroll — hours, new hires, terminations, garnishments, benefits changes?"
- "Which states do you track nexus in? Who watches for crossing thresholds?"
- "Per state, what's your final-pay timing rule? Who looks it up?"
- "What's your 1099 process? When did you last update for the OBBBA $2,000 TY2026 threshold?"
- "What's your classification framework for 1099 vs. W-2? When do you push back on a client's request?"

## Domain 9 — Advisory & CAS

Add these:
- "What controls do you actually test for clients? Segregation of duties, approval matrix, system access?"
- "13-week cash-flow forecast — what's the data source? Refresh cadence?"
- "What does a QBR agenda look like? Pre-read, in-meeting deliverables, follow-up?"
- "How do you decide a client is ready for advisory vs. just bookkeeping?"

## Domain 10 — QC & Review

Add these:
- "What's the partner sign-off threshold — by engagement type, by client size, by risk?"
- "When was the current reviewer checklist last updated? Does it match current bank-rec tolerance and JE thresholds?"
- "Have you adopted SQMS No. 1 (effective Dec 2025)? Where does the documentation live?"

## Domain 11 — Workflow & Practice Management

Add these:
- "What are your standard Karbon (or Canopy / Financial Cents) work templates? How often new vs. modified?"
- "How do you track WIP and capacity per person? When do you decide to hire / outsource / raise prices?"
- "Time entry — when, in what increments, with what notes? Realization target?"

## Domain 12 — Tech Stack & Integrations

Add these:
- "Walk me through every integration — QBO ↔ Karbon, Bill.com ↔ QBO, Gusto ↔ QBO. Where data crosses, who owns the controls?"
- "When a vendor ships a new feature (especially an AI feature), who reviews it before staff turns it on?"
- "What's your sandbox / test policy? Do staff test in client files?"

## Domain 13 — People, Training & RACI

Add these:
- "Per role, what's the 30/60/90-day training plan? Who delivers it?"
- "Do you have a documented career ladder? When does a Bookkeeper become a Senior?"
- "Where do training records live? CPE? Credentials?"

## Domain 14 — Internal Firm Operations

Add these:
- "Where does the firm's data live? What's your backup strategy — 3-2-1 with immutable copy?"
- "Last tabletop exercise on a backup restore? What broke?"
- "Insurance — E&O, cyber, BOP. Who reviews annually?"
- "Succession plan — what happens if the partner is hit by a bus on Monday