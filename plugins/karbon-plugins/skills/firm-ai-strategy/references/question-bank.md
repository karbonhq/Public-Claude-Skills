# The question bank

Every question is tagged for SHORT, DEEP, or both, and for which Core/Lab/Overlap zone it informs. The SHORT path uses ~18 questions; the DEEP path uses all of them with branched follow-ups.

## The pacing rule — one question at a time, always

This is non-negotiable and overrides everything else in this file. **Ask exactly one question per turn. Wait for the user's answer. Then ask the next one.**

- Never bundle two questions in one turn, even when they feel related.
- Never ask "Tell me about your firm — size, mix, niche, geography, and stage." That is five questions. Ask one.
- Never stack a follow-up onto a primary question in the same turn. Ask the primary, wait, then follow up.
- A turn with two question marks is a quality failure. Stop, split, and ask only the first.

If the user volunteers more than you asked, accept it — but still only ask one question on your next turn. Pacing gives the firm owner space to think; bundled questions produce skimmed answers; skimmed answers produce anodyne strategies.

## Conversational style

Run questions conversationally — never read them as a script. Use the user's previous answers to weave context into the next question. After each stage, briefly synthesize what you heard before moving to the next stage. The synthesis itself is *not* a question and does not count against the one-per-turn rule, but the question that follows the synthesis is the next single question.

## If the user supplied pre-interview context (Step 0)

If firm documents were supplied and read in Step 0, use them to compress the interview — but do not silently skip questions. Always confirm rather than assume. See `references/context-extraction.md` for the per-question skip-or-shorten guide. A few rules that apply across every stage:

- **Never skip these, even if a doc covers them:** Q5.1 (policy), Q5.2 (consumer-tier AI), Q4.2 (the wedge), Q6.1 (AI lead and skeptic), Q7.1–Q7.4 (metrics, budget, not-this-year list).
- **Pre-fill, then confirm:** for any question the docs answer, mirror back what you read and ask the user to confirm or amend before locking it in.
- **Press contradictions.** When a live answer conflicts with a supplied doc, surface the tension respectfully and ask the firm to reconcile. See the contradiction-handling section in `references/context-extraction.md` — three contradictions worth pressing especially hard are values-vs-operating-reality, priorities-vs-budget, and policy-vs-shadow-AI.

---

## Stage 1 — Where you are today (firm profile and AI baseline)

### Q1.1 — Tell me a bit about your firm.
*Open with this single question. Let the user volunteer what they want to share first. Then follow up with one question per turn until you have what you need.*

- **Path:** SHORT + DEEP. **Tags:** Core.
- **Why it matters:** every later answer branches off firm size and service mix.
- **Follow-ups (ask one at a time, in any order, only what wasn't volunteered):**
  - "How many people work in the firm — staff and partners?"
  - "What's the service mix — roughly, what percentage tax, audit, CAS, advisory?"
  - "Do you serve a particular industry or niche?"
  - "Where's the firm right now — launching, growing, prepping for transition or sale?"
- **Set branch flags for:**
  - `[size: solo / small (2-10) / mid (11-50) / large (50+)]`
  - `[mix: tax-heavy / CAS-heavy / audit-heavy / bookkeeping-heavy / balanced]`
  - `[niche: yes / no — name it]`
  - `[stage: launch / grow / transition / sell]`

### Q1.2 — How does AI show up in the firm today?
*Ask just this. Let the user paint the picture. Then if you need detail, follow up one turn at a time: "Which tools specifically?" → "Who's using them?" → "For what kinds of tasks?"*

- **Path:** SHORT + DEEP. **Tags:** Core, Lab.
- **Why it matters:** separates sanctioned use from shadow AI.
- **Good answers** name specific tools (Karbon AI, ChatGPT Plus, Copilot, Fathom, Blue J), specific people, and specific tasks.
- **Branching:**
  - "I'm not sure" or "everyone's using ChatGPT but I haven't checked" → flag shadow-AI risk and add Q5.2 to the SHORT path even if it would otherwise drop.
  - Heavy use of consumer-tier ChatGPT/Claude/Gemini → flag §7216/GLBA exposure for Stage 5.

### Q1.3 — What was the last AI win at your firm — even a small one?
*Ask the win first. Wait for the answer. Then follow up on a separate turn: "And what was the last flop or near-miss?"*

- **Path:** DEEP only. **Tags:** Core, Lab.
- **Why it matters:** surfaces what already works (replicable) and what scared people (cultural barrier).
- **Good answers** are concrete: "Sarah saved 4 hours on a memo using Claude" / "A staff member pasted a 1099 into ChatGPT and we had a panic."
- **Branching:** a flop involving client data → immediate compliance branch, escalate Stage 5.

### Q1.4 — On a scale from "we're testing things out" to "AI is part of how we work", where is your firm honestly?
- **Path:** SHORT + DEEP. **Tags:** Core.
- **Why it matters:** places firm on a simplified Aware → Active → Operational scale without forcing them to read a maturity matrix.
- **Branching:**
  - "Testing" → roadmap leads with one wedge use case.
  - "Part of how we work" → roadmap leads with governance and scaling.

---

## Stage 2 — What you're trying to accomplish (firm strategy first, AI second)

### Q2.1 — If I came back in 18 months and the firm was visibly better, what would be different?
- **Path:** SHORT + DEEP. **Tags:** all three.
- **Why it matters:** this is the firm's North Star, in the firm's own words.
- **Good answers** name a measurable change — "we doubled CAS revenue without adding staff," "we cut our tax season hours by 20%," "we transitioned 30% of clients to advisory."
- **Vague answers** ("more efficient," "more modern") trigger this follow-up: **"What would *you* see, hear, or count differently?"**

### Q2.2 — What are the top two or three priorities for the firm overall — not AI, just the firm?
- **Path:** SHORT + DEEP. **Tags:** all three.
- **Why it matters:** AI strategy must serve firm strategy.
- **Common answers:** growth, margin, talent retention, advisory shift, succession, sale prep, partner work-life.
- **Branching:**
  - Succession → roadmap emphasizes value-of-firm and reduced key-person risk.
  - Advisory shift → roadmap emphasizes data products and analyst capacity.
  - Talent retention → roadmap emphasizes burnout reduction and high-leverage tools.

### Q2.3 — Where is the firm's biggest source of pain right now? Where do people get stuck, repeat work, or burn out?
- **Path:** SHORT + DEEP. **Tags:** Lab + Overlap.
- **Why it matters:** high-friction × high-frequency work is where AI investment compounds.
- **Good answers** name a workflow ("review notes come back five times before a 1040 is filed"), not a function.
- **Branching:**
  - Pain in client comms → comms wedge first (Lab tool + Core triage like Karbon AI).
  - Pain in close/reconciliation → bookkeeping AI (Truewind, Numeric, Botkeeper, native Karbon Bookkeeper Agent).
  - Pain in research → tax-research AI (Blue J, Checkpoint with Materia, TaxGPT).
  - Pain in review cycles → Core agent (Karbon Tax Admin Agent, automated review tools).

### Q2.4 — What do your best clients actually pay you for — compliance, peace of mind, advice, capacity?
- **Path:** DEEP only. **Tags:** Lab + Overlap.
- **Why it matters:** AI commoditizes what AI is good at. If clients pay for compliance work that AI now does in minutes, the firm's value proposition is at risk.
- **Good answers** distinguish "they pay us to file" from "they pay us to think."
- **Branching:** compliance-dominant value prop → roadmap must include a parallel advisory-shift workstream.

### Q2.5 — If competitors figured out AI before you did, what would you lose?
- **Path:** DEEP only. **Tags:** all three.
- **Why it matters:** surfaces urgency and competitive context.
- **Good answers** name specific clients, specific service lines, specific price points.

---

## Stage 3 — What you have (Core, tech stack, data, people)

### Q3.1 — What practice management system does the firm use?
*Ask this first. Wait. Then follow up next turn: "And how much of the firm's work actually flows through it — would you say 80%, half, less?"*

- **Path:** SHORT + DEEP. **Tags:** Core.
- **Why it matters:** the Core anchors everything. A firm using its PM at 80% looks different from one using it as a glorified inbox.
- **Good answers** name the tool (Karbon, Canopy, TaxDome, Jetpack, Pixie) and the % of work that flows through it.
- **Branching:**
  - Low PM usage → first roadmap item is consolidating into the Core before adding Lab tools.
  - "We don't have one" → PM selection becomes a 90-day milestone.
  - Karbon at 80%+ → flag the AI Agents in beta (Bookkeeper, Tax Admin, Fractional CFO, Client Onboarding) and Ask Karbon as Core wedge candidates.

### Q3.2 — What GL system does the firm use?
*Then on separate turns: "What about tax software?" → "And document management?" → "Of those, which integrations work well, and which are manual or broken?" One question per turn.*

- **Path:** DEEP only (SHORT can ask only the GL and tax parts, still one at a time). **Tags:** Core, Overlap.
- **Why it matters:** the Overlap lives in these integrations. A firm where Karbon doesn't talk to QBO and tax software is leaking value.
- **Good answers** list each tool and which integrations are live, manual, or broken.
- **Branching:** heavy manual re-keying between systems → integration becomes top Overlap investment.

### Q3.3 — What native AI does the software you already pay for actually have, and are you using it?
- **Path:** SHORT + DEEP. **Tags:** Core.
- **Why it matters:** the cheapest AI is the AI you already own.
- **Good answers** reflect specific features turned on (Karbon Triage / Compose / briefs / Ask Karbon, Intuit Intelligence agents, Sage Copilot, Xero JAX, CCH Axcess Blue J integration, Materia in Checkpoint Edge).
- **Branching:** many features available, few used → roadmap leads with Core activation, not Lab purchases. (This is the highest-leverage finding for most firms.)

### Q3.4 — How clean and accessible is your client data — file structures, naming conventions, where things live?
- **Path:** DEEP only. **Tags:** Overlap.
- **Why it matters:** 57% of organizations say their data isn't AI-ready (Gartner).
- **Good answers** admit messy reality.
- **Branching:** messy data → data-readiness becomes a foundational workstream before agentic use cases.

### Q3.5 — Who in the firm is most fluent with AI today?
*Wait for the answer. Then follow up next turn: "And who'd you say is most resistant or skeptical?"*

- **Path:** SHORT + DEEP. **Tags:** all three.
- **Why it matters:** surfaces the two-camps dynamic and identifies the AI translator (one of the most predictive success variables in PwC's discovery process).
- **Good answers** name people, not roles.
- **Branching:**
  - No internal champion → roadmap must include a designated AI lead role.
  - Visible resistance from a partner → change-management workstream gets a partner-engagement subsection.

### Q3.6 — What's the firm's appetite for training?
*Then if helpful, follow up: "When was the last time you did formal training on anything?" → "How did that go?"*

- **Path:** DEEP only. **Tags:** all three.
- **Why it matters:** training investment correlates 1.6× with AI success (Deloitte) and 28% extra time savings (Karbon — trained users save 71% more time per day).
- **Good answers** reflect realistic cadence (monthly lunch-and-learns, dedicated CPE, none).

---

## Stage 4 — What you need (use case prioritization and the wedge)

### Q4.1 — If you could give every person in the firm an extra hour a day, what would you want them to spend it on?
- **Path:** SHORT + DEEP. **Tags:** all three.
- **Why it matters:** defines what "winning" looks like.
- **Good answers** separate "selling more advisory" from "leaving at 5 pm."
- **Branching:**
  - Capacity-for-growth → roadmap optimizes for revenue per FTE.
  - Quality-of-life → roadmap optimizes for hours saved.
  - Both can be measured.

### Q4.2 — Pick one workflow that, if AI handled 50% of it next month, would make a visible difference. Walk me through that workflow step by step.
- **Path:** SHORT + DEEP. **Tags:** Lab + Overlap.
- **Why it matters:** **this is the wedge**. The skill must produce a specific 30/60/90-day pilot plan around it.
- **Good answers** describe a real, recurring workflow with steps, owners, and current pain.
- **Branching:**
  - Comms-heavy workflow → Lab tool (Claude/Copilot) + Core triage (Karbon AI Triage/Compose).
  - Document-heavy workflow → Core add-on (DataSnipper, SmartVault SmartRequest, Suralink).
  - Research-heavy → Lab tool (Blue J, Claude with curated sources, Checkpoint with Materia).
  - Review-heavy → Core agent (Karbon Tax Admin Agent, Truewind, Numeric, Aiwyn).
  - Bookkeeping-heavy → Bookkeeper Agent / Booke.ai / Botkeeper / Vic.ai.

### Q4.3 — Which of your services is most at risk of being commoditized by AI, and which is most likely to grow because of it?
- **Path:** DEEP only. **Tags:** all three.
- **Why it matters:** forces strategic candor.
- **Good answers** reflect awareness that 1040 prep and bookkeeping commoditize fastest, advisory and audit grow.

### Q4.4 — What are two or three things you'd never want AI to touch?
- **Path:** SHORT + DEEP. **Tags:** all three.
- **Why it matters:** defines the firm's red lines. These become explicit guardrails in the policy.
- **Good answers** cite client meetings, tax positions, audit opinions, sensitive comms.

---

## Stage 5 — How you'll govern it (risk, compliance, policy)

### Q5.1 — Does the firm have a written AI policy?
*Wait for yes/no. If yes, follow up next turn: "What does it cover?" If no: "What's the rule everyone seems to follow, even unwritten?"*

- **Path:** SHORT + DEEP. **Tags:** all three.
- **Why it matters:** 21% of firms have a policy (Karbon 2026); the rest run on tribal norms.
- **Good answers** cite specific rules (no client data in consumer tiers, approved tools list, training required).
- **Branching:**
  - No policy → SHORT-path output includes a one-page interim policy (use `assets/policy-template.md`).
  - Mature policy → output focuses on operationalization and gap analysis.

### Q5.2 — Does anyone on your team paste client data into ChatGPT, Claude, Gemini, or Copilot's free or personal versions?
- **Path:** SHORT + DEEP. **Tags:** Lab.
- **Why it matters:** this is the §7216 / GLBA / AICPA confidentiality landmine. Asking it directly forces a real answer that "what's your governance posture" never gets.
- **Good answers** are honest. The answer is almost always "yes" or "probably."
- **Branching:** yes (or "probably") → immediate remediation in the strategy: enterprise-tier deployment within 30 days, mandatory training session, sanctioned-tool list. Make this the first 30-day milestone if not already.

### Q5.3 — Which of your clients' regulatory contexts matter most — tax §7216, audit independence, GLBA, state board, healthcare/legal client industries?
- **Path:** DEEP only. **Tags:** all three.
- **Why it matters:** shapes vendor selection and engagement-letter language.
- **Good answers** name the actual rules in play.

### Q5.4 — When AI gets something wrong on a client deliverable, what happens?
*Single open question. Then follow up turn-by-turn as needed: "Who catches it?" → "Who's accountable?" → "What does the workpaper trail look like?"*

- **Path:** DEEP only. **Tags:** all three.
- **Why it matters:** surfaces the human-in-the-loop pattern and workpaper retention. McKinsey's data: high performers establish defined HITL processes 65% vs. 23% of others.
- **Good answers** describe a real review step with a named reviewer.

### Q5.5 — Have your engagement letters been updated to reflect AI use?
*Wait. Then follow up next turn: "And have you had the AI conversation with your E&O carrier yet?"*

- **Path:** DEEP only. **Tags:** all three.
- **Why it matters:** CAMICO and AON now ask. Insurers have begun adding AI questions on renewal applications.
- **Branching:** no → adds a 30-day legal/insurance task to the roadmap.

---

## Stage 6 — How you'll roll it out (change management and people)

### Q6.1 — Who's leading AI inside the firm right now — formally or informally?
*Wait for the lead. Then on a separate turn: "And who'd you call your unofficial AI skeptic?"*

- **Path:** SHORT + DEEP. **Tags:** all three.
- **Why it matters:** every successful AI rollout has a named owner and a named bridge to the skeptical camp. AI projects with sustained executive sponsorship succeed 68% of the time vs. 11% when sponsorship lapses.
- **Good answers** name two people.
- **Branching:**
  - No named lead → roadmap appoints one (often a manager, not a partner).
  - No named skeptic → likely under-surveyed; loop back to Q3.5.

### Q6.2 — How do you want to train people — formal sessions, async videos, peer-led "AI office hours," vendor-led sessions, all of the above?
- **Path:** DEEP only. **Tags:** all three.
- **Why it matters:** training cadence is a leading indicator of ROI (trained users save 71% more time).
- **Good answers** commit to a frequency.

### Q6.3 — How will you communicate this strategy to the team?
*Wait for the answer. Then follow up: "And how will you handle the staff member who hears 'AI' and thinks 'I'm being replaced'?"*

- **Path:** DEEP only. **Tags:** all three.
- **Why it matters:** 33% of individual contributors fear job loss; 37% of ops/admin staff are concerned (up 17 points YoY in Karbon 2026).
- **Good answers** acknowledge the fear and address it concretely (capacity for advisory, not headcount cut).
- **Branching:** nervous workforce → roadmap includes explicit "no AI-driven layoffs in year one" type commitments and reinvestment language.

### Q6.4 — Are there roles your firm needs to add or rethink because of AI — an AI ops person, a prompt librarian, a data lead, a younger partner?
- **Path:** DEEP only. **Tags:** all three.
- **Why it matters:** surfaces hiring implications. SMBs rarely add roles; they add responsibilities to existing people.
- **Good answers** reallocate before they hire.

---

## Stage 7 — How you'll measure it (ROI and roadmap)

### Q7.1 — In 90 days, what's the one number you want to see move that proves AI is working?
- **Path:** SHORT + DEEP. **Tags:** all three.
- **Why it matters:** forces a single, measurable success metric. 73% of failed AI projects lacked clear metrics (S&P Global 2025).
- **Good answers** are specific: "hours per 1040," "monthly close days," "advisory revenue %," "review cycles per return," "client onboarding days."
- **Branching:** metric is unmeasurable today → first roadmap milestone is establishing a baseline.

### Q7.2 — In 12 months, what does success look like financially — capacity freed, revenue grown, margin gained, or all three?
- **Path:** SHORT + DEEP. **Tags:** all three.
- **Why it matters:** the reinvestment ratio question — efficiency gains either become hours saved (capacity), price increases (margin), or new services (revenue).
- **Good answers** commit to one of the three.
- **Branching:**
  - Capacity → roadmap includes new-services pipeline.
  - Margin → pricing review.
  - Revenue → advisory or productized service launch.

### Q7.3 — What's the budget envelope realistically available for AI in the next 12 months — software subscriptions, training, consulting, time?
- **Path:** SHORT + DEEP. **Tags:** all three.
- **Why it matters:** anchors realism. Progressive firms invest 10–25% of tech budget in AI; average firm tech spend is ~$20k.
- **Good answers** commit a number.
- **Branching:**
  - Very low budget → roadmap leans on Core activation and free Lab tiers.
  - Meaningful budget → roadmap includes purpose-built accounting AI (Aiwyn, Black Ore, Truewind, Blue J, MindBridge, Fieldguide).

### Q7.4 — What comes first?
*Then on separate turns: "What comes second?" → "And what are you explicitly NOT doing this year?" The "not this year" question is the most important — get it on its own turn.*

- **Path:** SHORT + DEEP. **Tags:** all three.
- **Why it matters:** the explicit "not this year" list is what makes the strategy a strategy.
- **Good answers** name 2–3 priorities and 2–3 deferrals.
- **Branching:** every "not this year" item becomes a future-state roadmap entry rather than disappearing.

### Q7.5 — Who reviews this strategy in 90 days?
*Then on separate turns: "Who reviews it in 12 months?" → "And what would cause you to change course off-cycle — what kind of event or signal?"*

- **Path:** DEEP only. **Tags:** all three.
- **Why it matters:** turns the document into a living plan.
- **Good answers** name a person, a calendar cadence, and concrete trigger conditions (new tool category emerges, regulatory change, major incident, missed milestone).

---

## SHORT path — question sequence

The SHORT path is roughly 18 questions, ~90 seconds each:

Q1.1, Q1.2, Q1.4, Q2.1, Q2.2, Q2.3, Q3.1, Q3.3, Q3.5, Q4.1, Q4.2, Q4.4, Q5.1, Q5.2, Q6.1, Q7.1, Q7.2, Q7.3, Q7.4.

Adaptively add Q5.2 follow-ups if shadow-AI risk surfaces, Q3.4 if data readiness is clearly weak, and Q3.2 (just the GL/tax part) if the wedge depends on integration.

## DEEP path — session structure

- **Session 1 (~45 min): Stages 1–3** — where you are, what you're trying to accomplish, what you have. Output: a "firm profile + AI baseline" working document the firm can edit between sessions and circulate to partners.
- **Session 2 (~30–45 min): Stages 4–5** — what you need, how you'll govern it. Output: prioritized use-case portfolio, draft policy, vendor decisions, red lines.
- **Session 3 (~30 min): Stages 6–7** — rollout and measurement. Output: training plan, change-management plan, KPIs, roadmap, review cadence.

Between sessions, save state and confirm with the user before proceeding. Multi-session is a feature of the DEEP path, not a bug — it lets the firm sleep on its answers and circulate the working document.
