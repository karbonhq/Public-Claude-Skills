# Taxonomy overview — 16 domains across 5 layers

This is the master index used in Phase 2 (mapping) and Phase 3 (gap analysis). For each domain, this file gives you a one-paragraph summary, anchoring authorities, and a pointer to the layer reference doc with full detail.

When mapping a SOP to a domain, start here, then load the matching layer doc for granular guidance.

---

## Layer 1 — Client value chain

The client-facing operating contract: who you serve, how you collect their data, and how you bill.

### Domain 1 — Client lifecycle
Prospecting through disengagement: ICP scoring, scoping/discovery, proposal and engagement letters, onboarding, ongoing rhythms, change orders, off-boarding. Engagement letters are the highest-leverage SOP — >50% of malpractice claims tie to missing or unclear letters. Onboarding is the second-highest — top firms close it under 30 days vs. industry-average 60. Anchored in AICPA PCPS, CAMICO, CPA.com CAS 2.0, VeraSage, Ron Baker.
**Detail:** `02-layer1-client-value-chain.md`

### Domain 2 — Document & data collection
One source of truth, one secure portal, never email attachments. Required by IRS Pub 4557, FTC Safeguards, and AICPA hosting interpretation §1.295.143. Covers portal selection, PBC list management, retention schedules (AICPA recommends 7 years; IRS varies 3-7+; SAS 103 is 5 years), W-9 refresh.
**Detail:** `02-layer1-client-value-chain.md`

### Domain 3 — Pricing & billing
Sell intellectual capital, not time. Three-tier subscription pricing is the dominant pattern. Operational benchmarks: realization ≥85%, write-off <5%, AR days <30, lockup <45. CAS NCFPP median $156,250 (2024). Anchored in Ron Baker's value pricing, VeraSage, CPA.com CAS Benchmark Survey.
**Detail:** `02-layer1-client-value-chain.md`

---

## Layer 2 — Production

The actual accounting work — where errors hit clients fastest.

### Domain 4 — Transaction processing & bookkeeping
Standardize before you scale. Firm-level master COA (4-digit, 75-account ceiling for SMB). Materiality-driven categorization. Vendor master as control point for 1099/AP/fraud screening (W-9 collection, TIN matching, OFAC/SDN/DMF, B-Notice within 15 days, 24% backup withholding). AP workflows with five-step pattern (capture → match → code → approve → pay).
**Detail:** `03-layer2-production.md`

### Domain 5 — Reconciliations
Reconciliation matches GL to one source; **substantiation** validates ending balance with reviewer signoff. Risk-based balance-sheet substantiation: every account assigned owner, risk rating, cadence. Variance threshold ≥$1,000 or ≥5%. Items aged >60 days escalate. Tools: FloQast, Numeric, BlackLine.
**Detail:** `03-layer2-production.md`

### Domain 6 — Period-end / month-end close
Documented checklist with task owners, dependencies, due dates is the single highest-leverage close intervention. Top performers 1-3 business days; mid-market median 6-7. Soft vs. hard close distinction. 5-day reference close from Keiter/FloQast/Numeric/Karbon. 60-70% of close delays come from missing information (PBC discipline upstream).
**Detail:** `03-layer2-production.md`

### Domain 7 — Financial reporting
GAAP is the floor, insight is the ceiling. Standard 8-element monthly package. **SSARS 27 (effective Dec 15, 2026)** is the most consequential recent SOP development for CAS — clarifies AR-C 70 not required when financial-statement preparation isn't primary objective under CS 100. Tools: Fathom, Spotlight, Jirav, Reach, LiveFlow, G-Accon.
**Detail:** `03-layer2-production.md`

### Domain 8 — Payroll & sales tax intersections
Payroll touchpoints: clearing to zero per pay period, register-to-GL monthly, 941-to-GL quarterly, W-2 totals annually. 1099/W-2 hygiene is monthly not January-sprint. Sales tax: nexus monitoring post-Wayfair ($100k or 200 transactions varies by state); tools include Avalara, TaxJar, Anrok, Kintsugi, Numeral.
**Detail:** `03-layer2-production.md`

### Domain 9 — Advisory & CAS deliverables
The AICPA / CPA.com CAS 2.0® framework is the reference architecture: four pillars (Strategy & Governance, Practice Development, Technology Solutions, Operational Excellence). Trusted Business Advisor framework (Reeb/Cingoranelli). Cadence SOPs: monthly advisory meeting, QBR with traffic-light scorecard. 13-week cash flow forecast as gold standard. Industry-specific KPI dashboards. vCFO standard deliverables.
**Detail:** `03-layer2-production.md`

---

## Layer 3 — Quality

The control system that prevents errors from reaching clients.

### Domain 10 — Quality control & review
**AICPA SQMS Nos. 1-3 became effective December 15, 2025.** SQMS 1 requires 8 components: firm risk assessment, governance/leadership, ethical requirements, acceptance/continuance, engagement performance, resources, information/communication, monitoring/remediation. SQMS 2 governs Engagement Quality Review. SAS 146 covers GAAS engagement-level. SSARS 26 mirrors for SSARS engagements. Four-eyes principle. Tiered review pyramid: Preparer → Reviewer → Manager → Partner/EQR.
**Detail:** `04-layer3-quality.md`

### Domain 11 — Workflow & practice management
Capacity planning: utilization 70-80% target (50-65% partners), 1,750 net available hours/year, every 5% utilization shift = 3-7% margin shift. 13-week rolling capacity forecast. Hire/outsource/raise prices triad. Workflow tools: Karbon (350+ templates, AI Agents launching 2026), Jetpack Workflow, Canopy, Financial Cents, TaxDome, Aiwyn, Pixie, Keeper.
**Detail:** `04-layer3-quality.md`

---

## Layer 4 — Enablement

The infrastructure that makes the work possible.

### Domain 12 — Technology stack & integrations
Hub-and-spoke architecture with GL or practice management at hub. Layered: System of Record (GL), System of Work (PM), System of Engagement (portal), record-adjacent (AP, payroll), reporting layer, close layer, document/DMS, glue (APIs preferred, Zapier/Make fallback). Tech stack archetypes by firm size. SOC 2 Type II as minimum bar. MCP emerging as integration pattern.
**Detail:** `05-layer4-enablement.md`

### Domain 13 — People, training & RACI
"One-firm" orientation beats eat-what-you-kill. SQMS 1 makes HR an attest-quality control. RACI at task level (Numeric pattern) preferred over process level. Career ladders — traditional vs. CAS-specific (CPA.com endorses non-CPA pathways). 40 hrs/yr CPE. Offshoring oversight: IRC §7216 written consent required (no retroactive consent, valid 1 year).
**Detail:** `05-layer4-enablement.md`

### Domain 14 — Internal firm operations
HR handbook essentials. IT operations: MDM, SSO, **3-2-1 backup with immutable copy** for ransomware. BC/DR with BIA → RTO/RPO. **Succession planning is the #1 endemic problem** — 75% retire within 15 years per AICPA, only 44% of multi-owner firms have written plans. Vendor management under FTC §314.4(f). Insurance stack (E&O does NOT cover cyber — both required).
**Detail:** `05-layer4-enablement.md`

---

## Layer 5 — Governance

Risk, compliance, security, and the AI overlay.

### Domain 15 — Risk, compliance & security
**Independence** (AICPA Code §1.200, §1.230, §1.295) is the bedrock for any firm doing both attest and CAS. SKE designation rule. Hosting Services interpretation §1.295.143. **IRS Pub 4557** WISP mandatory for PTIN renewal effective 1/1/2023. **FTC Safeguards Rule** (16 CFR Part 314) — all paid tax preparers are "financial institutions"; small-entity exemption only at <5,000 NPPI consumers; breach notification within 30 days for ≥500 unencrypted. **IRC §7216/§6713** — criminal misdemeanor for unauthorized disclosure. SOC 2 / SSAE 18. AI usage policies. Breach response per NIST 800-61 phases.
**Detail:** `06-layer5-governance.md`

### Domain 16 — AI & agentic workflows
The fastest-evolving SOP domain. **Human-in-the-Loop is the dominant ethos.** HITL Fallacy: rubber-stamping under decision fatigue. Agent oversight tiers (0 Suggestion / 1 Copilot/Draft / 2 Bounded Autonomy / 3 Full Autopilot). Karbon AI Agents (2026): Bookkeeper, Tax Admin, Fractional CFO, Onboarding Specialist with Agent Management System. Prompt libraries as first-class SOP artifacts under SQMS 1. NIST AI RMF (GOVERN, MAP, MEASURE, MANAGE). COSO ICIF for GenAI (2026). Audit trails for AI work (prompt + output + model + timestamp + user + reviewer edits, retention 7+ years).
**Detail:** `06-layer5-governance.md`

---

## Mapping cheat sheet

When mapping an SOP to a domain, ask:

1. **What's the primary deliverable or outcome?** (e.g., reconciled bank account → Domain 5; financial package to client → Domain 7)
2. **Who's the primary actor?** (e.g., bookkeeping staff → Layer 2; firm admin/HR → Layer 4; firm leadership/risk → Layer 5)
3. **What standard governs it?** (e.g., SQMS 1 → Domain 10; FTC Safeguards → Domain 15; CS 100 advisory → Domain 9)
4. **Is it cross-cutting?** Many SOPs touch multiple domains (e.g., a "Year-end 1099 process" SOP spans Domain 4 vendor master, Domain 8 1099 hygiene, and Domain 15 §7216 if any consents are involved). Pick a primary domain and list secondaries.

---

## Domain summary table (for quick reference)

| # | Domain | Layer | Primary actor | Key authority |
|---|---|---|---|---|
| 1 | Client lifecycle | Value chain | Partner/owner, sales | AICPA PCPS, CAMICO |
| 2 | Document & data collection | Value chain | Bookkeeper, admin | IRS Pub 4557, FTC §314 |
| 3 | Pricing & billing | Value chain | Partner/owner | VeraSage, CAS Benchmark |
| 4 | Transaction processing | Production | Bookkeeper | IRS 1099 rules |
| 5 | Reconciliations | Production | Bookkeeper, senior | FloQast/Numeric methodology |
| 6 | Period-end close | Production | Senior, manager | Keiter/FloQast/Numeric |
| 7 | Financial reporting | Production | Manager, CAS lead | SSARS 21-27, FASB ASC |
| 8 | Payroll & sales tax | Production | Bookkeeper | IRS payroll, post-Wayfair |
| 9 | Advisory & CAS | Production | CAS Manager, vCFO | CAS 2.0, TBA framework |
| 10 | QC & review | Quality | Reviewer, partner | SQMS 1-3, SAS 146, SSARS 26-27 |
| 11 | Workflow & practice mgmt | Quality | Operations lead | Boomer Lean Six Sigma |
| 12 | Tech stack & integrations | Enablement | Tech lead, IT | SOC 2 |
| 13 | People, training & RACI | Enablement | Partner, HR lead | IRC §7216 (offshoring) |
| 14 | Internal firm operations | Enablement | Firm admin, partner | FTC §314.4(f), AICPA succession |
| 15 | Risk, compliance & security | Governance | Partner, Qualified Individual | AICPA Code, Pub 4557, FTC §314, IRC §7216 |
| 16 | AI & agentic workflows | Governance | AI Champion, Skills Librarian | NIST AI RMF, COSO ICIF, ISO 42001 |
