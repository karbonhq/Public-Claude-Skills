# The accounting AI tech stack — Core, Lab, Overlap

This file is the product reference for Stages 3 and 4. Read it when discussing what the firm has and what wedge to recommend.

## Core — the firm's operating system

The Core is the practice management + GL + tax + document management layer. Native AI is increasingly baked in; the cheapest AI is the AI you already own.

### Practice management

- **Karbon** — deepest native AI in the category. Triage (inbox sorting and prioritization), Compose (email and client-comm drafting), AI-generated client briefs, smart assignments, and AI Agents in beta: Bookkeeper Agent, Tax Admin Agent, Fractional CFO Agent, Client Onboarding Agent. Ask Karbon orchestrates across the firm's workflows. For Karbon firms, the Core wedge is almost always "activate what's already there before you buy anything new."
- **Canopy** — GPT-powered email drafting and client communication. Less depth than Karbon but functional.
- **TaxDome** — AI-powered reporting and document automation.
- **Jetpack Workflow** — lighter on AI; good for small firms; recommend pairing with a Lab tool.
- **Pixie, Aero Workflow, Financial Cents** — minimal AI; recommend Core consolidation as a year-one milestone.

### General ledger

- **QuickBooks Online** — Intuit Intelligence launched Dec 2025 with seven role-based agents (accounting, payroll, payments, customer, finance, project, business). High-leverage for small-firm CAS practices.
- **Xero** — JAX (Just Ask Xero) and embedded AI for reconciliation, invoicing, and reporting.
- **Sage Intacct + Sage Copilot** — embedded AI assistant; growing in mid-market.
- **NetSuite** — text enhance, anomaly detection, embedded analytics.

### Tax software

- **UltraTax / Checkpoint Edge** — Thomson Reuters acquired Materia (Oct 2024) and is embedding agentic AI across the platform.
- **CCH Axcess** — integrates Blue J (tax research) and MindBridge (audit).
- **Lacerte / ProConnect** — integrates with TaxGPT, StanfordTax/Soraban/Truss.
- **Drake, ATX, TaxWise** — limited native AI; pair with Lab.

### Document management & audit

- **DataSnipper** — document data extraction; widely adopted.
- **MindBridge** — anomaly detection for audit.
- **Fieldguide** — Series C, $700M valuation; agentic audit workflow.
- **AICPA Dynamic Audit Solution (DAS)** — with AiDa, Extractly.ai, Validis.
- **Caseware** — adding AI features to working papers and audit.
- **SmartVault, Suralink** — secure client portals with AI-assisted document collection (SmartRequest, etc.).

## Lab — the external general-purpose AI layer

The Lab is where firms experiment, sanctioned or not. The goal is a sanctioned, training-data-safe Lab.

### Enterprise general-purpose LLMs (the sanctioned options)

- **Claude for Work / Claude Enterprise** — data not used for training. The April 29 webinar focuses on Claude Projects. Strong for long-document reasoning, drafting, and tax memos.
- **ChatGPT Enterprise** — SOC 2 Type 2; data not used for training. Consumer ChatGPT Plus/Free trains on prompts and is dangerous for client data.
- **Microsoft Copilot M365** — operates inside the firm's Microsoft tenant. Often the safest starting Lab for Microsoft-shop firms because the data stays inside their existing 365 boundary.
- **Gemini Workspace** — for Google Workspace firms; equivalent posture.

### Consumer-tier LLMs (THE BANNED LIST for client data)

- ChatGPT Free / Plus
- Claude Free
- Gemini personal
- Copilot personal / web
- Any general LLM on a personal account

These tiers train on prompts by default. **No client data — ever.** This is the most important single rule in any firm's AI policy.

### AI transcription & meeting tools

- **Fathom, Otter, Fireflies, Vinyl, Ping, Abacor** — meeting transcription and summarization. Most firms already have one.
- **Granola** — Mac-native, popular in product/tech circles.

### Pure-play accounting AI

- **Aiwyn** — Claude integration; engagement letter and client management workflows.
- **Black Ore** — agentic tax workflow; near full automation possible on individual 1040s.
- **Truewind** — bookkeeping and close automation.
- **Numeric** — close management.
- **Vic.ai** — AP automation.
- **Botkeeper** — bookkeeping automation.
- **Booke.ai** — bookkeeping AI for small firms.
- **Keeper** — bookkeeping QA and review.
- **Blue J** — tax research.
- **TaxGPT** — tax research.
- **StanfordTax / Soraban / Truss** — tax workflow.

## Overlap — where Core and Lab connect

The Overlap is where most strategy documents fail and where the biggest leverage hides. The interview must work hard here.

### Common Overlap patterns

- **PM ↔ GL.** Karbon ↔ QBO, Karbon ↔ Xero, Canopy ↔ QBO. If broken or manual, integration is the top Overlap investment.
- **PM ↔ tax software.** Karbon ↔ UltraTax, Karbon ↔ CCH Axcess. Often manual today; high leverage to fix.
- **Email ↔ PM.** AI triage of email into the PM is where Karbon Triage and Compose shine.
- **Documents ↔ extraction.** DataSnipper, SmartVault SmartRequest, Suralink → tax software / GL.
- **Lab ↔ Core.** AI-drafted email in Claude/Copilot lands in Karbon as a draft (via copy-paste today; via API/integration in future state).

### How to recommend an Overlap investment

The wedge from Q4.2 should ideally use one Lab tool + one Core feature, with an Overlap connection between them. Examples:

- "Comms wedge": Claude (Lab) drafts client follow-ups → Karbon Compose (Core) sends them. Overlap = the prompt library and the handoff protocol.
- "Research wedge": Blue J (Lab/Core hybrid) for tax research → tax memos drafted in Claude → reviewed in Word → filed in DMS. Overlap = the research-to-memo template.
- "Close wedge": Truewind (Lab/specialized) drafts close entries → Karbon Bookkeeper Agent (Core) reviews → human sign-off. Overlap = the review checklist.
- "Onboarding wedge": Karbon Client Onboarding Agent (Core) + Suralink (Core) for document collection. Overlap = the onboarding template library.

## Service-line AI suitability — the prioritization map

| Service line | AI maturity | Where it goes in the strategy |
|---|---|---|
| Client comms, email, meeting transcripts | Most mature (77% adoption) | Quick wins; Lab tools (Fathom, Otter, Claude/Copilot) compounding into Core (Karbon Triage/Compose) |
| Internal ops, SOPs, workflow | Advanced & accelerating | Quick wins; Core PM AI |
| Document collection & extraction | Mature, ROI-proven | Core add-on (SmartVault, DataSnipper, Suralink, Dext) |
| Tax research | Mature | Lab→Core (Blue J, Checkpoint+Materia, TaxGPT) |
| Tax prep & compliance | Near full automation possible | Strategic bet (Black Ore, StanfordTax, Aiwyn) |
| Bookkeeping | Full agentic execution emerging | Strategic bet — but highest disruption risk for bookkeeping-only firms |
| Audit & risk | Slow but strategic | Multi-year roadmap (AICPA DAS, MindBridge, Fieldguide, Caseware) |
| Advisory / CAS | The next frontier | Highest-margin growth bet |
| Financial analysis | Underutilized | Biggest gap — only 13% of firms used AI here in 2025 |

## What to recommend by firm profile

- **Solo / 2–10 staff:** Activate Core AI in PM and GL. Sanction one Lab tool (Claude or Copilot). Free or already-paid tiers. One transcription tool. Defer agentic accounting AI. Wedge: comms or document collection.
- **Mid-market 11–50, balanced:** Activate Core AI fully. Sanction one Lab tool + transcription. Add one purpose-built accounting AI (research or close). Wedge: tax research or close.
- **Mid-market 11–50, tax-heavy:** Activate tax-software AI (Materia, Blue J, etc.). Sanction Claude or Copilot for memos. Add Black Ore or Aiwyn for prep. Wedge: 1040 automation.
- **Mid-market 11–50, audit-heavy:** Lead with AICPA DAS / MindBridge / Fieldguide. Treat Lab tools cautiously. Wedge: workpaper drafting under supervision.
- **Mid-market 11–50, CAS-heavy:** Lead with Intuit Intelligence / Karbon Bookkeeper Agent. Add advisory tooling. Wedge: monthly close acceleration.
- **Mid-market 11–50, bookkeeping-heavy:** Read this carefully — bookkeeping is the most-disrupted service line. Sequence the wedge against an explicit advisory-shift workstream. Wedge: parallel — bookkeeping automation + first advisory product.
- **Large 50+:** Add governance, multi-office sequencing, and audit-quality-control branches. Lab posture should be enterprise-tier across the board.
