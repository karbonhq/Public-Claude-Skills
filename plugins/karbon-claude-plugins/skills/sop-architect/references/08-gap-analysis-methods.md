# Gap analysis methods

Load this in Phase 3 (gap analysis). These are the methodologies for systematically finding what's missing.

---

## Process mapping and gap analysis (the standard sequence)

1. **Inventory** every recurring service line and supporting process
2. **Map current state** with flowchart, swim lane, or BPMN
3. **Define future state** at target maturity
4. **Gap = future minus current**
5. **Prioritize** by risk × frequency × impact
6. **Action plan** with owner and milestones
7. **Monitor** with KPIs

---

## Value Stream Mapping (VSM)

From Toyota Production System / Lean Six Sigma. Distinguishes value-added from non-value-added activities.

PwC research suggests **80-90% of tasks in typical business processes are wasteful.**

### DOWNTIME — the waste taxonomy

| Letter | Waste | Example in accounting |
|---|---|---|
| D | Defects | Re-work due to coding errors |
| O | Overproduction | Generating reports nobody reads |
| W | Waiting | Waiting for client docs / approvals |
| N | Non-utilized talent | Senior doing data entry |
| T | Transportation | Moving documents between systems |
| I | Inventory | WIP sitting in queue |
| M | Motion | Switching between apps to find data |
| E | Extra processing | Steps that add no client value |

### VSM integration with DMAIC

**DMAIC = Define, Measure, Analyze, Improve, Control.**

For accounting, VSM applies cleanly to:

- Tax return cycle
- Monthly close
- Audit fieldwork
- CAS onboarding

### Kaizen events

3-5 day focused improvement projects.

**Boomer offers Lean Six Sigma Green Belt certification** for accounting firms.

---

## Risk-based prioritization

Not every process needs a formal SOP. Prioritize by:

1. **Significance / impact**
2. **Frequency** (monthly close > one-time event)
3. **Variability / error rate**
4. **Compliance exposure**
5. **Dependence on individuals** — bus factor of one = critical
6. **Onboarding leverage** — does this SOP help a new hire ramp?

### Common starting set (for a typical firm)

- Month-end close
- AP
- AR
- Bank reconciliation
- Expense management
- Audit prep
- Client onboarding
- Engagement acceptance
- Tax return workflow

---

## "Knowledge audit" approach

Surface tribal knowledge before it walks out the door:

1. **Survey staff** with: "what do you do that no one else can?"
2. **Map key-person dependencies** (the bus factor exercise)
3. **Conduct shadow / observation sessions** recorded with Glitter AI, Scribe, or Tango
4. **Compare process inventory against documented SOPs**
5. **Track recent errors and client complaints** back to undocumented processes

---

## Gap-signal triggers

These are the situations that often reveal SOP gaps. When the user mentions any of them, treat it as evidence of a gap:

- High turnover or recent departure of a key knowledge holder
- Onboarding pain (new hires take too long)
- Recurring errors (duplicate payments, miscategorizations, missed deadlines)
- Client complaints about consistency, timeliness, or communication
- Missed filing/close deadlines
- Cycle-time degradation
- M&A or PE due diligence requiring documented processes
- Regulatory change exposing undocumented assumptions
- Scaling pain (partners drowning in detail)
- Audit findings
- Tool migrations breaking workarounds
- AI adoption creating new gaps (review, audit-trail, data privacy, prompt-quality)

---

## Common blind spots in accounting firms

Synthesized across Glitter AI, AccountingWEB, INAA, Karbon, Aiwyn, Boomer, and CPA.com. **These are the most common SOP coverage gaps** — when running gap analysis, check each of these explicitly:

| Blind spot | Why it's missed | Domain |
|---|---|---|
| **Client onboarding** (intake, KYC/AML, engagement letter, system access, first-90-day comms) | "It's obvious" | 1, 2 |
| **Engagement acceptance and continuance** (conflict check, risk scoring) | Treated as partner judgment | 1, 10 |
| **Capacity / workload management** (no SOP for saying "no" or escalating overload) | Cultural — admitting overload feels like failure. Jason Blumer's M.E.L.T framework addresses this. | 11 |
| **Knowledge transfer / off-boarding when a manager leaves** | Departures are emotional and rushed | 13 |
| **Internal communication norms** | "Everyone just knows" | 11 |
| **Pricing and proposal generation** | Often partner-by-partner intuition | 3 |
| **Billing and AR** | Aiwyn cites partners waiting **100 days to bill** | 3 |
| **Client off-boarding / disengagement** | Avoided due to discomfort; creates ongoing liability | 1 |
| **AI usage** (approved tools, prohibited data, review and logging) | Too new; firms haven't caught up | 16 |
| **Data security incidents and breach response** | "It won't happen to us" | 15 |
| **Software / tool decommissioning** | Tools accumulate; nothing dies | 12 |
| **Tax notice handling** | Each notice feels unique | 8, 15 |
| **Estimate-to-actual review for fixed-fee engagements** | Reveals bad pricing decisions | 3 |
| **Quality control review at engagement close** | Squeezed by deadline pressure | 10 |
| **Year-over-year process refresh** | "We did this last year" | 6, 11 |
| **Vendor / tool evaluation** | Decisions made by whoever shopped | 12 |
| **Cross-training and backup-coverage** | Specialization breeds key-person risk | 13 |
| **Remote-staffing / offshore handoffs** | §7216 consent gap is common | 13, 15 |

---

## How to apply gap analysis in Phase 3

For each of the 16 domains:

1. Look at what SOPs are inventoried in that domain (from Phase 2 mapping)
2. Compare against the **expected SOPs at this firm's maturity level** (per `07-maturity-models.md`)
3. Compare against the **common blind spots** in this file
4. Compare each existing SOP against the **15-field anatomy** (per `00-sop-anatomy.md`) — flag anatomy gaps even if the SOP nominally exists
5. Classify: Complete / Partial / Missing / N/A
6. For Partial and Missing, capture: what's missing, risk, frequency, dependencies
7. Score per the prioritization rubric in `07-maturity-models.md`

---

## Anti-patterns in gap analysis

Watch out for these failure modes when running gap analysis:

- **Counting volume over substance** — "we have 47 SOPs!" but they're all stale or anatomy-incomplete
- **Cargo-cult mapping** — assuming a domain is covered because the firm has *something* labeled with that domain's name
- **Ignoring dependencies** — writing an advisory SOP before the close SOP exists; the advisory SOP depends on close outputs
- **Missing the cross-cutting SOPs** — onboarding touches 5+ domains; treating it as a single-domain SOP misses gaps
- **Treating compliance gaps as effort decisions** — Pub 4557 WISP is non-negotiable; you don't trade it off against effort
- **Confusing checklists with SOPs** — a checklist without owner, controls, escalation, and authority is not an SOP
