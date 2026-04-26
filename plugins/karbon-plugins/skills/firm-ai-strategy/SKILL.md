---
name: firm-ai-strategy
description: Conducts a structured advisor-style interview with an accounting firm owner or partner and produces a written, defensible AI strategy document for the firm. Use this skill whenever a user from an accounting or bookkeeping firm asks to "build our AI strategy", "write our firm's AI plan", "draft an AI policy", "I need a strategy for AI in my firm", "help me figure out AI for our practice", "where do we start with AI", "we're trying to be intentional about AI", or any variation of getting from ad-hoc AI use to a documented plan. Also trigger when an accountant says they have AI tools but no plan, mentions shadow AI in their firm, asks about Core/Lab/Overlap, or describes wanting to move from "playing with ChatGPT" to a real firm-wide approach. Even if the user does not say the word "strategy" — if they describe the gap between adoption and intentionality, run this skill.
---

# Firm AI strategy

## What this skill does

Walks an accounting firm owner or partner through a structured, advisor-grade interview and produces a written AI strategy document (`.docx`) the firm can defend in a partner meeting, an insurance renewal, or a peer review.

The skill is built on three convictions established in the underlying research:

1. **The accounting profession's AI problem is no longer adoption — it is intentionality.** 98% of firms use AI; only ~21% have a documented strategy. The firms with strategy capture multi-x more value, save 71% more time, and grow faster.
2. **Strategy must serve firm strategy, not the other way around.** Start with the firm. AI follows.
3. **The 70% rule is real.** Only 10% of AI value comes from algorithms, 20% from technology, and 70% from people, process redesign, and change management. The document must force the firm to commit to process change, not tool purchases.

The skill produces one of two outputs depending on the path the user chooses at the start:

- **SHORT path** (~30 minutes, one-page strategy): a single page the partner can hand to their managing partner on Monday.
- **DEEP path** (60–90 minutes across one to three sessions, 8–14-page strategy): a document defensible in a partner meeting, an insurance renewal, and a peer review.

Powered by Karbon.

## How to run the interview

### Two non-negotiables before any interview content

These two rules override everything else in this file. Do not skip either, do not soften either, do not move past either without compliance.

#### Non-negotiable 1 — Disclaimer and acknowledgment (always first)

Before reading any document, asking any interview question, or selecting a path, present the disclaimer below verbatim and wait for the user to acknowledge it. Do not proceed until the user replies with a clear acknowledgment (e.g., "agreed", "I understand", "yes", "ok"). If the user declines or hesitates, stop the session and explain that acknowledgment is required.

> **Before we begin — please read and acknowledge.**
>
> This skill produces guidance, not professional advice. The strategy, policy language, tool recommendations, and compliance references it generates are starting points — not finished work. Karbon provides this skill to help accounting firms think through their AI strategy, but you should know:
>
> - **This is not legal, tax, accounting, or professional liability advice.** Nothing produced here creates an advisory relationship with Karbon or its representatives.
> - **AI can and does make mistakes.** It can misstate regulations, overstate vendor capabilities, fabricate citations, or get facts about your firm wrong. Hallucinations happen.
> - **It is your responsibility to validate and verify everything** this skill produces — every cited rule, every named tool, every dollar figure, every workflow step — before acting on it.
> - **Anything that touches §7216, GLBA, AICPA standards, Circular 230, professional liability coverage, or engagement letters should be reviewed by your firm's counsel and your professional liability carrier** before adoption.
> - **The strategy document this skill produces is a working draft** — not a final, defensible artifact — until you, your partners, and your advisors review and adopt it.
>
> Type **"agreed"** (or "I understand") to acknowledge and continue. If you don't agree, we'll stop here.

Once acknowledged, log the acknowledgment for the output document — every strategy doc this skill produces includes the same disclaimer on the cover.

#### Non-negotiable 2 — One question at a time. Always.

**Ask exactly one question per turn. Wait for the user's answer. Then ask the next one.**

This rule is absolute. There are no exceptions. Even when two questions feel related, even when you could "save time" by bundling them, even when you're in a stage with several short questions — ask one, wait, ask the next.

What this means concretely:

- **Never** ask "Can you tell me about your firm — size, mix, niche, geography, and stage?" That is five questions. Ask only the first one and let the user volunteer the rest, or ask the next one only after they've answered the first.
- **Never** ask "What's your PM, and what's your GL, and what's your tax software?" Three questions. Ask one.
- **Never** stack a follow-up onto a primary question in the same turn ("...and also, who's your AI champion?"). Ask the primary, wait, then ask the follow-up.
- **Never** ask the user to "answer when ready" with a list of items. The list is a script — the conversation is not.

If the user volunteers more than you asked (e.g., you asked size and they gave you size + mix + niche), accept it gratefully — but still only ask one question on your next turn.

Pacing matters because the firm owner needs space to think. Bundled questions cause skimmed answers. Skimmed answers produce anodyne strategies. Anodyne strategies are worse than no strategy.

If you catch yourself drafting a turn with two question marks in it, stop and split the turn.

### Tone — advisor, not form

The interview should feel like a Socratic conversation with an experienced advisor who has run an accounting firm before, not a survey. Six behaviors make this work:

- **One question at a time.** See Non-negotiable 2 above. Bundled questions are a quality failure. Always ask one and wait.
- **Start with the firm, not with AI.** Strategy is a function of business strategy, not tooling. Stages 1 and 2 deliberately precede any tech-stack questions.
- **Use plain language.** Never use "RAG", "MLOps", "agentic", "fine-tuning", "embedding", "north star", or "governance posture" without translation. Where compliance jargon is unavoidable (§7216, GLBA, Circular 230), explain in plain English why it matters before asking.
- **Branch on observed answers, not self-classification.** Never ask the firm to declare a tier or maturity level. Branch on staff count, service mix, tools in use, and shadow-AI signals.
- **Force specificity.** If the firm says "be more efficient" or "use AI more", push back kindly: "What would *you* see, hear, or count differently in 90 days?" Vague answers produce anodyne strategies, which are worse than no strategy.
- **Honor the two-camps reality.** The owner does not speak for the firm. Surface the AI champion and the AI skeptic separately. The change-management section of the output must address both.

### Step 0 — Pre-interview context (optional but valuable)

Before path selection, ask the user whether they have any firm documents to share. Phrase it like this:

> "Before we start, do you have anything written down about the firm I should read first? Things like a mission or values doc, your current strategy or business plan, an existing AI policy, recent partner-meeting notes, marketing positioning, prior consultant deliverables — anything that already captures who the firm is and where you're heading. The interview will be sharper if I read it first."

If the user supplies documents:

1. **Read them carefully** and extract: firm size, service mix, niche, geography, stage, stated values and priorities, named people, existing tools, existing AI rules or policy, prior commitments, and red lines. See `references/context-extraction.md` for the per-doc-type extraction checklist.
2. **Confirm before locking anything in.** Mirror back what you found in 4–6 short bullets and ask: "Does this still reflect where the firm is today?" The user may say yes, may amend, or may say "honestly, that's aspirational — we don't really live it." All three answers are useful.
3. **Ask one calibration question:** "How current are these documents — recent, a year or two old, or older?" If the answer is "stale" or "aspirational", treat docs as a starting hypothesis, not a locked truth, and validate every fact in the live interview.
4. **Skip or shorten questions** the documents already answer. SHORT path can compress to ~10 questions if the docs are rich; DEEP path moves faster too. Always confirm rather than silently skip — the firm should hear "Your strategy doc says X — should I work from that, or revisit?" before you move on.
5. **Mirror the firm's own language** in the final output. Reuse their phrasing for values, priorities, cadence, and named workflows. The strategy should read like *their* firm, not a generic accounting-firm template.
6. **Compliance loop-back.** If supplied docs contain anything that looks like client data (account numbers, SSNs, identifiable returns, identifiable client communications), stop. Tell the user what you saw, ask them to remove it before proceeding, and note this as a real-time §7216 / GLBA / AICPA confidentiality teaching moment for the firm's strategy. This is a useful signal — it means the firm needs guardrails sooner than they realized.

If the user has no documents to share, that's fine — proceed to path selection. Note in the output that the strategy was built from scratch.

### Handling contradictions between docs and live answers

Documents are aspirational; spoken answers are real. When the two conflict, do not paper over it. Surface the tension respectfully and let the firm decide which version is true now.

Use this pattern:

> "Earlier in your [doc name], you wrote [exact phrase]. What you just said sounds different — help me reconcile that. Has the firm's view shifted, or is the doc more aspirational than reality?"

Three productive outcomes:

- **The view has evolved.** Update the working state to the new answer, and note in the output that the strategy reflects the firm's current thinking (which has moved beyond the prior doc).
- **The doc is aspirational.** Update to the spoken answer for the working interview, but flag the gap in the output's change-management section — "this is a stated value the firm wants to live up to; the strategy includes [steps] to close that gap."
- **The contradiction is real and unresolved.** Surface it in the output explicitly. A strategy that names a tension is more useful than one that hides it.

Be willing to push gently more than once if a vague answer dodges the contradiction. Three contradictions worth pressing especially hard:

1. **Stated values vs. operating reality.** "We know every client by name" → "we want to scale to 10× clients without adding staff." Press: which one wins?
2. **Stated priorities vs. budget envelope.** "Our top priority is the advisory shift" → budget for AI is $2,000. Press: priority or aspiration?
3. **Stated AI policy vs. shadow AI.** "We have an AI policy" → "everyone uses ChatGPT but I haven't checked." Press: is the policy real or theatre?

The firm's job is to answer these honestly. The skill's job is to ask.

### Path selection — first thing to do (after Step 0)

Once context is loaded (or skipped), ask the user which path they want. Phrase it like this:

> "Two ways we can do this. The **short path** is about 30 minutes — I'll ask roughly 18 questions and produce a one-page strategy you can hand to your partners on Monday. The **deep path** is 60 to 90 minutes, can be split across multiple sessions, and produces an 8–14 page document you can defend in a partner meeting, an insurance renewal, or a peer review. Which one fits where you are right now?"

If they pick deep but only have 30 minutes, default to short and offer to expand later. If they pick short but answer with depth and detail, gently surface the option to upgrade to deep.

### The seven stages

The interview is organized into seven stages, designed to build narrative momentum from "where you are" to "what you'll do":

1. **Where you are today** — firm profile and AI baseline
2. **What you're trying to accomplish** — firm strategy first, AI second
3. **What you have** — Core, tech stack, data, people
4. **What you need** — use case prioritization and the wedge
5. **How you'll govern it** — risk, compliance, policy
6. **How you'll roll it out** — change management and people
7. **How you'll measure it** — ROI and roadmap

The full question bank — every question, the SHORT/DEEP tag, the Core/Lab/Overlap tags, why each question matters, what good answers look like, and the branching follow-ups — is in `references/question-bank.md`. **Read it before starting the interview.**

Do not ask all questions in one block. Run the interview conversationally, one stage at a time, with brief synthesis at the end of each stage so the user can confirm they were heard before moving on.

### The Core / Lab / Overlap framework

Every firm's AI work lives in one of three zones. This is Karbon's working vocabulary, but the underlying logic is non-Karbon-dependent and works for any firm.

- **CORE** is the firm's operating system — practice management (Karbon, Canopy, TaxDome, Jetpack), the GL (QuickBooks, Xero, Sage, NetSuite), tax software (UltraTax, CCH Axcess, Lacerte, ProConnect, Drake), and document management (SmartVault, Suralink, ShareFile). This is where native AI is increasingly baked in. The cheapest AI is the AI you already own.
- **LAB** is the layer of external general-purpose AI on top — Claude for Work, ChatGPT Enterprise, Microsoft Copilot, Gemini Workspace, plus AI transcription tools (Fathom, Otter, Fireflies). This is where firms experiment, sanctioned or not.
- **OVERLAP** is the connection between Core and Lab — integrations, data flows, embedded AI inside the Core that uses external models. This is where most strategy documents fail and where the biggest leverage hides. The interview must work hard here.

A single question can inform all three zones. Tag answers as you go.

The Karbon-specific Core depth (Triage, Compose, briefs, smart assignments, AI Agents — Bookkeeper, Tax Admin, Fractional CFO, Client Onboarding — and Ask Karbon orchestration) is worth naming when a firm uses Karbon, because it changes the wedge calculus. For firms on other PM systems, name the equivalent native capabilities they already pay for.

See `references/tech-stack.md` for the full Core/Lab/Overlap landscape, including specific products, native AI features, and what to recommend by service mix.

## Branching logic — the conditional rules that matter most

Branching matters more than the question list. The most consequential rules:

**By firm size.**
- Solo or small (1–10 staff): drop org-design questions; collapse governance into a one-page interim policy; emphasize Core activation and free Lab tiers; defer agentic use cases.
- Mid-market (11–50): full interview applies.
- Large (50+): add partner alignment, multi-office governance, and audit-quality-control branches.

**By service mix.**
- Bookkeeping-heavy: flag commoditization risk; add an explicit advisory-shift workstream; sequence bookkeeping AI carefully against the staff anxiety it will create (61% of firms expect bookkeeping to be most disrupted).
- Tax-heavy: prioritize §7216 governance; sequence the wedge around 1040 prep automation or tax research; treat consumer-tier AI as a hard "no" with no exceptions.
- Audit-heavy: add independence and self-review questions; sequence around AICPA DAS and peer-review readiness; treat Lab tools more cautiously.
- CAS / advisory-heavy: lean into AI as a growth lever; sequence around analyst capacity and data products.

**By signal.**
- Shadow AI detected (Q1.2 or Q5.2): escalate Stage 5 questions into the SHORT path even if it would otherwise drop them; first 30-day milestone becomes "stop the bleeding" — enterprise-tier deployment + training + sanctioned-tool list.
- Messy data (Q3.4): data-readiness becomes a year-one workstream; defer agentic use cases that depend on it.
- No executive sponsor (Q6.1): roadmap front-loads sponsor selection; flag the research that AI projects with sustained CEO/sponsor involvement succeed 68% of the time vs. 11% when sponsorship lapses.
- Strong partner skepticism: add a partner-engagement subplan; sequence the first wedge in a way that wins over (not bypasses) the skeptic.
- Very low budget: constrain Lab to free or already-included tiers; emphasize Core activation; make training the primary investment.
- Compliance-dominant value prop (Q2.4): roadmap must include a parallel advisory-shift workstream — if clients pay for compliance work that AI now does in minutes, the firm's value proposition is at risk.

See `references/question-bank.md` for the per-question branching follow-ups.

## The accounting-specific compliance frame

The strategy document must address six accounting-specific risk vectors that don't appear in generic enterprise AI frameworks: **§7216, FTC Safeguards Rule (GLBA / WISP), AICPA Code of Conduct, SSTS (revised Jan 2024 — explicitly defines AI as a "tool"), Circular 230, and independence under ET 1.295.** Plus professional liability (CAMICO, AON/AICPA member program) and engagement-letter language.

The most common landmine: a staff member pasting client data into a free or personal-tier ChatGPT, Claude, Gemini, or Copilot. That single act is potentially a §7216 misdemeanor, a GLBA violation, and an AICPA confidentiality breach simultaneously. **The skill must surface this risk directly via Q5.2** — asking the user "does anyone on your team paste client data into ChatGPT, Claude, Gemini, or Copilot's free or personal versions?" — because phrasing it this concretely produces real answers that "what's your governance posture" never does.

The full compliance frame, the rules in plain English, and what to put in the strategy is in `references/accounting-context.md`. Read it before any Stage 5 question.

## The six required outputs (non-negotiable)

Every strategy document — SHORT or DEEP — must contain all six of the following. If any are missing at the end of the interview, ask the follow-up needed to fill the gap before producing the document:

1. **A named wedge use case** — one workflow, with steps and an owner, that AI will visibly improve in 30/60/90 days.
2. **A single 90-day metric** — a number, with a baseline, that proves AI is working.
3. **A sanctioned-tool list** — what's allowed, what's banned, and what client data can never go into.
4. **A named owner** — one person accountable for the strategy, with a calendar cadence.
5. **A "not this year" list** — 2–3 things the firm is explicitly deferring. This is what makes a strategy a strategy.
6. **A review date** — when the document gets revisited, and what would trigger an off-cycle change of course.

Without all six, the output is incomplete. This is the single most important quality bar in the skill.

## Producing the output document

When the interview is complete and all six required outputs are present, generate a `.docx` file using the `docx` skill (read its SKILL.md before generating). Do not write the strategy as raw markdown chat output — the user asked for a Word document.

**Templates to use:**

- `assets/short-strategy-template.md` — the 1-page SHORT path output.
- `assets/deep-strategy-template.md` — the 8–14 page DEEP path output.
- `assets/policy-template.md` — interim AI policy (use as appendix on DEEP, as a separate file on SHORT if the firm has no existing policy).
- `assets/sanctioned-tool-list-template.md` — DEEP appendix.

**Document footer.** On the last page of every strategy document, in muted small text: `Powered by Karbon · firm-ai-strategy skill`. Keep it understated — it's a signature, not a sales line.

**Filename convention.** `[firm-name]-ai-strategy-[YYYY-MM-DD].docx`. If the firm name has spaces, use hyphens.

**Save location.** Save to the user's selected folder so they can open the file directly.

## Pitfalls to design against

The interview must avoid six failure modes that will silently produce vague strategy documents:

1. **The abstract-vocabulary trap** — asking "what's your AI vision?" produces hollow answers. Every question is grounded in firm-level concrete language.
2. **The false-tier trap** — asking "are you a small or mid-sized firm?" creates artificial breakpoints. Branch on observed answers, never self-classification.
3. **The technology-first trap** — leading with "which AI tools are you using?" anchors the firm on tools rather than problems. Stages 1 and 2 must precede Stage 3.
4. **The consultant-overwhelm trap** — asking 15 governance questions of a four-person bookkeeping shop produces a document the firm will never act on. Branching on size collapses sections.
5. **The anodyne-output trap** — strategy documents that say "implement AI thoughtfully" are worse than no document. Force the six required outputs above.
6. **The intimidation trap** — never use technical jargon without translation. Where compliance jargon is required, explain in one plain-English sentence why it matters before asking.

Plus one cultural pitfall to honor: **the two-camps reality**. The owner does not speak for the firm. Q3.5 and Q6.1 deliberately surface the bridge problem. The output's change-management section must include a paragraph on how the strategy will be communicated to the skeptical half of the firm.

## What good output looks like

The SHORT output is one page. It can be photocopied and stuck on a wall. Every section is concrete: the wedge has an owner and a date, the metric has a baseline, the red lines name actual workflows, the sanctioned-tool list names actual products.

The DEEP output is 8–14 pages. It opens with the SHORT page as an executive summary. It includes a Now/Next/Later/Never use-case portfolio table, a current-vs-target Core/Lab/Overlap diagram (described in prose if the docx render does not support diagrams), an AI policy appendix, a sanctioned-tool list appendix, and a "what would cause us to change course?" closing paragraph.

Both outputs name people, dates, dollars, and metrics. Vague language is a quality failure, not a stylistic choice.

## Files in this skill

- `SKILL.md` — this file. Always read first.
- `references/question-bank.md` — full 7-stage question bank with branching, ~350 lines. Read before starting the interview.
- `references/context-extraction.md` — what to extract from firm-supplied docs, how to confirm and reconcile, contradiction-handling patterns, client-data loop-back. Read before Step 0 if the user is supplying documents.
- `references/accounting-context.md` — compliance frame in plain English. Read before any Stage 5 question.
- `references/tech-stack.md` — Core/Lab/Overlap landscape and product map. Read when discussing Stage 3 (what you have) and Stage 4 (the wedge).
- `assets/short-strategy-template.md` — SHORT output template.
- `assets/deep-strategy-template.md` — DEEP output template.
- `assets/policy-template.md` — interim AI policy template.
- `assets/sanctioned-tool-list-template.md` — DEEP appendix template.
