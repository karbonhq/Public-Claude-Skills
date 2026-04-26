# Pre-interview context — what to extract, how to confirm, how to reconcile

This file tells you how to handle Step 0 (pre-interview context) when the user supplies firm documents. Read it before reading any docs they share.

The goal is to make the interview sharper without taking the firm's stated position at face value. Documents are aspirational. Spoken answers are real. Your job is to read both, treat them as a starting hypothesis, and surface the tension when they disagree.

## What to ask the user up front

> "Before we start, do you have anything written down about the firm I should read first? Things like a mission or values doc, your current strategy or business plan, an existing AI policy, recent partner-meeting notes, marketing positioning, prior consultant deliverables — anything that already captures who the firm is and where you're heading. The interview will be sharper if I read it first."

Followed by, once docs are in:

> "How current are these — recent, a year or two old, or older? And honestly: do they reflect how the firm actually operates today, or are some parts more aspirational?"

The "honestly" word matters. It gives the user permission to admit the values doc is from 2019 and they don't really live it.

## What to extract from each document type

For every document the firm supplies, extract the facts below if present, and tag the source so you can cite it during the interview.

### Mission / vision / values / purpose

- Stated mission and vision (verbatim)
- Named values (verbatim — these will appear in the output if the firm wants them to)
- Stated client commitments ("we know every client by name", "we respond within 4 hours", etc.)
- Implied positioning (boutique, full-service, niche, regional, national)

### Current strategy / business plan / 3-year plan

- Top firm priorities (next 12–24 months)
- Revenue or capacity targets
- Service-line mix targets (e.g., "we're shifting to 30% advisory by 2027")
- Geographic or niche expansion plans
- Succession or sale-prep horizon
- Hiring plans or org-design commitments

### Existing AI policy (or any policy mentioning AI)

- Sanctioned tools (with tiers if listed)
- Banned tools or rules
- Named owner / Qualified Individual under WISP
- Vendor-vetting process if any
- Engagement-letter language if any
- Training requirements if any
- Last revision date

### Partner meeting notes / retreat outputs

- Recently agreed priorities
- Open debates (especially anything 2-camps)
- Named champions and skeptics
- Budget commitments
- Specific named workflow pain points

### Marketing positioning / capability statement / About page

- How the firm describes itself externally
- Service-line emphasis
- Named industry niches
- Stated differentiators
- Implicit value prop (compliance / advice / capacity / peace-of-mind)

### Prior consultant deliverables

- Prior strategy recommendations and what was acted on
- Prior assessments of firm strengths and weaknesses
- Prior tech-stack reviews
- Prior partner-engagement findings

### Org chart / staffing list

- Staff count and role distribution
- Partner count and seniority spread
- Tenure profile (junior-heavy, senior-heavy, balanced)
- Named individuals (useful for the AI lead and the AI skeptic — see Q3.5 / Q6.1)

## How to confirm what you found

After reading, mirror back what you extracted in 4–6 short bullets. Use the firm's own phrasing wherever possible. Then ask one question to confirm it still reflects today.

Example confirmation:

> "Quick check before we start. From your strategy doc and About page, here's what I'm working from:
>
> - 28-person multi-service firm in Charlotte, mostly tax (60%) and CAS (30%), with a small audit practice.
> - Top three priorities for the next 18 months: advisory shift, partner succession (you have two partners retiring in 2028), and reducing tax-season hours.
> - Stated values include 'every client knows their accountant by name' and 'we measure twice and file once'.
> - You have an AI policy from late 2024 that lists ChatGPT and Microsoft Copilot as approved, but no Karbon-specific guidance.
>
> Does this still reflect where the firm is today, or has anything moved?"

Note that this confirmation is also a chance for the user to admit gaps — "honestly the AI policy is on a shelf and nobody follows it" is a critical answer that should escalate Stage 5.

## When to skip vs. shorten vs. ask anyway

Use the following guide:

| Question | Skip if doc says... | Shorten if doc says... | Ask anyway if... |
|---|---|---|---|
| Q1.1 (firm profile) | All of size + mix + niche + stage are clearly stated and confirmed current | Some present, some missing | Doc is older than 12 months |
| Q1.2 (AI in firm today) | Detailed AI inventory in policy or recent doc | Partial inventory | Always — shadow AI is rarely in docs |
| Q2.1 / Q2.2 (north star + priorities) | Strategy doc names them and user confirms current | Some present | Always — phrase in user's voice |
| Q3.1 / Q3.3 (PM and native AI) | Tech stack inventory present | Partial | Always — usage % is rarely written |
| Q3.5 (champion / skeptic) | Org chart or partner notes name them | Hints only | Always — this is a personal answer |
| Q5.1 (AI policy) | Policy supplied | — | Always — verify it's current and lived |
| Q5.2 (consumer-tier AI use) | Never skip | Never skip | Always |
| Q6.1 (AI lead) | Named in policy or org chart | Hints | Always — confirm and add a named skeptic |
| Q7.1 / Q7.2 / Q7.3 (metrics + budget) | If a strategy doc commits dollars and metrics | Partial | Almost always — the metric question is too important to delegate |
| Q7.4 (not-this-year list) | Never skip | Never skip | Always — this is what makes the strategy a strategy |

In short: **the AI policy questions, the consumer-tier-AI question, the wedge, the named owner, the metrics, and the not-this-year list are never skipped, even if a doc covers them.** Everything else can be compressed if the supplied context is rich enough.

## How to handle contradictions (the most important section)

When a spoken answer contradicts a supplied document, do not silently pick one. Surface the tension and ask the firm to reconcile it. Use this pattern:

> "Earlier in your [doc name], you wrote [exact phrase]. What you just said sounds different — help me reconcile that. Has the firm's view shifted, or is the doc more aspirational than reality?"

Three productive outcomes:

- **The view has evolved.** Update the working state to the new answer. Note in the output that the strategy reflects the firm's current thinking (and that the prior doc may want to be updated accordingly).
- **The doc is aspirational.** Update to the spoken answer for the working interview, but flag the gap in the output's change-management section — "[stated value] is something the firm wants to live up to; the strategy includes [specific steps] to close that gap."
- **The contradiction is real and unresolved.** Surface it explicitly in the output. A strategy that names a tension is more useful than one that hides it.

### Three contradictions worth pressing especially hard

1. **Stated values vs. operating reality.**
   *Example:* "We know every client by name" + "we want to scale to 10× clients without adding staff."
   *Press:* "Both of these can't be fully true at scale. Which one wins, and what does that mean for the strategy?"

2. **Stated priorities vs. budget envelope.**
   *Example:* "Our top priority is the advisory shift" + "AI budget is $2,000."
   *Press:* "If the advisory shift is the top priority, the AI investment level may be a constraint. Is the priority real, or is the budget a placeholder?"

3. **Stated AI policy vs. shadow AI.**
   *Example:* "We have an AI policy" + "everyone uses ChatGPT but I haven't checked."
   *Press:* "If the policy is real, the shadow use is a violation. If the shadow use is reality, the policy isn't being lived. Which is it, and what should the strategy do about it?"

Be respectful. Don't make the firm feel caught. Frame it as you trying to make the strategy honest — "I want to make sure the document we produce reflects what's actually true, not just what's already written down."

But do press. Glossing over contradictions produces the anodyne-output trap.

## Compliance loop-back — the client-data check

While reading supplied docs, watch for anything that looks like client data: account numbers, SSNs, identifiable client names with financial figures attached, identifiable returns, screenshots of QBO with client data visible.

If you see any:

1. **Stop reading immediately.**
2. **Tell the user plainly:** "Just to flag — the [doc name] you shared contains what looks like client data (specifically: [brief description]). Before we keep going, can you remove that and re-share? And if this doc has been shared with anyone outside the firm, that's a §7216 / GLBA conversation we should add to the strategy."
3. **Note it in the output.** This is a real-time confidentiality incident, not a hypothetical one. The strategy's Stage 5 governance section should address (a) document-handling hygiene, (b) the WISP review, and (c) staff training on what counts as "client data."

This is also a useful teaching moment for the training session. A firm that ships a strategy doc with client data attached has demonstrated, in the most concrete possible way, why the strategy needs guardrails.

## What to put in the output

If pre-interview context was supplied:

- **In the executive summary or section 2 (Firm context):** "This strategy was developed using [list of docs] supplied by the firm, plus a [SHORT/DEEP] interview conducted on [date]."
- **Where the strategy reuses firm language:** quote the source ("[Firm] mission, 2024: '...'").
- **Where the strategy diverges from the prior doc:** name it ("In the strategy doc, the firm committed to [X]; in this engagement, the firm has updated that view to [Y].")
- **Where contradictions remain unresolved:** name them in the change-management section as open tensions to address.

If no context was supplied: note that the strategy was built from the interview alone, and recommend that the firm circulate the draft to partners for alignment with any existing strategy or values work.
