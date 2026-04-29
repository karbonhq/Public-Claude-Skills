# 12-Question Firm Intake Interview

Run this before classifying or scoring anything. Every downstream stage depends on the firm's profile. Without it, the skill cannot tell which "missing" SOPs are real gaps versus correctly out of scope.

## How to run the interview

Group questions naturally. Don't ask all 12 in 12 separate prompts — that feels like a tax form. Aim for 4–6 conversational turns:

- Turn 1: questions 1, 2, 3 (basic firm shape)
- Turn 2: questions 4, 5 (tooling and security posture)
- Turn 3: questions 6, 7 (current SOP state)
- Turn 4: question 8 (pain points — give them room to talk)
- Turn 5: questions 9, 10 (AI and offshore)
- Turn 6: questions 11, 12 (niche and goals)

Use AskUserQuestion for the size band, service-mix tiers, and security-posture state. Use natural conversation for everything else. If the firm gives a partial answer, follow up — don't move on without the data needed for downstream classification.

Save answers to `working/firm-profile.md` as you go. Format like a structured Q&A so later stages can grep it.

---

## The 12 Questions

### 1. Firm shape
"How big is the firm right now? I'm looking for: total headcount, number of partners or owners, and a rough revenue range. The size determines which SOPs you actually need to have — a 3-person bookkeeper has a very different expected set than a 30-person CAS practice."

Capture: `headcount`, `partners`, `revenue_band` (one of: <$500K, $500K–$1M, $1M–$3M, $3M–$10M, $10M+).

Map headcount to a **size tier**: 1–3 / 4–15 / 16–40 / 41–100. This drives `size-tier-expected-sets.md`.

### 2. Service mix
"What's the rough mix of your work? Bookkeeping, monthly close, CAS/advisory, payroll, tax, audit, other? Percentages don't have to be precise — I'm trying to figure out which domains in the framework apply most to you."

Capture: `service_mix` as a list of `{service, percent}`. Common services: bookkeeping, monthly_close, CAS_advisory, payroll, tax_compliance, audit_review, fractional_CFO, sales_tax, other.

Service mix flips entire domains in or out of scope. A firm with 0% payroll plus 0% sales tax marks Domain 8 N/A. A firm with 0% advisory marks Domain 9 N/A or partial-N/A. A firm with 0% tax adjacency marks the year-end portions of Domain 6 N/A.

### 3. Client portfolio
"How many clients are on the books right now, and what's your ideal client profile — industry, revenue range, complexity level? If you concentrate in a niche (vet, dental, restaurants, SaaS, etc.), tell me."

Capture: `client_count`, `ICP_industries`, `ICP_revenue_range`, `niche_concentration` (true/false + which niche).

Niche concentration drives whether Domain 9.13 (industry KPI library) and niche-specific Domain 6/7 entries are in scope.

### 4. Tech stack
"Walk me through your tech stack. I need: GL (QBO/Xero/NetSuite/other), practice management (Karbon/Canopy/Financial Cents/TaxDome/none), AP (Bill.com/Ramp/Relay/none), payroll (Gusto/Rippling/ADP/OnPay/none), expense (Ramp/Brex/Divvy/none), sales tax (Avalara/TaxJar/Anrok/DAVO/none), reporting (Fathom/Jirav/Reach/Spotlight/Syft/LiveFlow/native/none), file share (SharePoint/Drive/Box/Dropbox), e-signature (DocuSign/PandaDoc/Adobe), secure email (Citrix/SmartVault/native)."

Capture each as a structured field. Tech stack drives the `tools` section of every relevant SOP and the AP/AR/payroll workflow scoring.

### 5. Security posture
"Three quick yes/no questions on security:
1. Do you have a documented WISP (Written Information Security Plan)?
2. Have you implemented an FTC Safeguards program with a named coordinator and a written risk assessment?
3. Do any of your clients require a SOC 2 letter from you?"

Use AskUserQuestion with three separate questions, options Yes/No/Don't know. WISP "Don't know" is effectively "No" for scoring.

WISP gap is the single highest-priority compliance flag — flag prominently in the gap report regardless of overall maturity.

### 6. Where SOPs live today
"Where do your existing SOPs actually live? Could be: PM tool work templates (Karbon, Canopy), a wiki or Notion, a Google Drive or SharePoint folder, Loom video library, Scribe documents, or 'mostly in our heads.' List all of them."

Capture: `sop_locations` as a list of strings.

This determines intake mode (Stage 2). 'Mostly in our heads' triggers tribal-knowledge capture during per-gap interviews.

### 7. SOP authorship & review
"Who currently authors SOPs, and who reviews/approves them? Is there a review cadence, or do they only get updated when something breaks?"

Capture: `sop_authors`, `sop_reviewers`, `review_cadence` (quarterly/annually/ad-hoc/never).

A 'never' or 'ad-hoc' cadence drops every existing SOP's Currency score by 1 even if recently edited.

### 8. Top three pain points
"Where do mistakes happen most often? Where do clients churn or get frustrated? Where does work slip through the cracks? Top three places — I want to make sure the gap report addresses these specifically, not just the framework's defaults."

Capture: `pain_points` as a list of free-form strings. These get cited by name in the gap report's roadmap section.

### 9. AI tools in production
"Are you using any AI tools today? Karbon AI Agents, Keeper, Digits, Intuit AI, Aider, Botkeeper, ChatGPT/Claude usage by staff (sanctioned or unsanctioned)? Be honest about the unsanctioned use — that's a policy gap, not a moral failing."

Capture: `ai_tools` as a list, with `sanctioned: true/false` flag.

Unsanctioned AI use → flag in compliance section as policy gap (Domain 16 floor regardless of size tier).

### 10. Offshore / contractor reliance
"How much of the work is done offshore or by contractors versus W-2 employees? This changes the RACI design and the security posture you need."

Capture: `offshore_percent`, `contractor_percent`.

>30% offshore raises the bar on Domain 15 (security, §7216 consent for offshoring) and Domain 12 (IT access provisioning).

### 11. Niche and industry concentration
"Earlier you mentioned [client niche from Q3]. Tell me more — how concentrated are you? If 60%+ of revenue comes from one industry, you should have industry-specific SOPs in Domain J. What industries?"

Capture: `niches` as a list of industry strings.

Concentrated niches with no industry-specific reporting (Domain 9.13) and no industry-specific chart of accounts in production = priority gap.

### 12. Strategic 12-month goal
"Last question. What's the firm trying to do in the next 12 months? Scale (add staff/clients), sell (prep for exit), niche down, add CAS, add AI — or stay the same? This determines which gaps are urgent vs. nice-to-have."

Capture: `strategic_goal` as one of: scale, sell, niche, add_CAS, add_AI, maintain, other.

Strategic goal weights the prioritization formula in the gap report. A 'sell' goal promotes Domain 10 (QC) and Domain 14.5 (succession) gaps. An 'add_AI' goal promotes Domain 16 gaps. An 'add_CAS' goal promotes Domain 9. A 'scale' goal promotes Domain 1 (onboarding) and Domain 11 (workflow).

---

## Output of this stage

`working/firm-profile.md` should be readable as a structured profile. Example:

```markdown
# Firm Profile

## Shape
- Headcount: 8 (3 bookkeepers, 2 seniors, 1 controller, 1 partner, 1 admin)
- Partners: 1
- Revenue band: $1M–$3M
- Size tier: 4–15

## Service Mix
- Bookkeeping: 50%
- Monthly close: 30%
- CAS advisory: 15%
- Payroll: 5%
- Tax: 0%

## Client Portfolio
- Client count: 42
- ICP: $500K–$5M revenue, service-based businesses
- Niche concentration: yes — 65% veterinary practices

## Tech Stack
- GL: QBO
- PM: Karbon
- AP: Bill.com
- Payroll: Gusto
- Expense: Ramp
- Sales tax: none
- Reporting: Fathom
- File share: SharePoint
- E-signature: Ignition
- Secure email: SmartVault

## Security Posture
- WISP: No
- FTC Safeguards program: No
- SOC 2 needed: No

## SOP State
- Locations: Karbon templates (some), SharePoint folder (legacy Word docs), mostly in heads
- Authors: controller and partner
- Reviewers: partner only
- Review cadence: ad-hoc

## Pain Points
1. New client onboarding takes 12+ hours and varies wildly
2. Month-end close blows past day 7 every month
3. Senior bookkeeper is the bottleneck for everything

## AI Tools
- Karbon AI Agents (sanctioned, light 