# Layer 2 — Production (Domains 4-9)

The actual accounting work — where errors hit clients fastest. Load this when mapping or building SOPs in transactions, recs, close, reporting, payroll/sales tax, or CAS deliverables.

---

## Domain 4 — Transaction processing & bookkeeping

**Core principle:** standardize before you scale. A firm-level master Chart of Accounts with allowable client-level overrides is foundational.

### Chart of Accounts standard

- **4-digit numbering**
- **75-account ceiling** for SMB clients
- Allowable client-level overrides only with documented rationale
- "Ask My Accountant" account banned as a permanent dumping ground

### Materiality-driven categorization

| Transaction size | Treatment |
|---|---|
| <$25 | Auto-coded |
| $25-$1,000 | Preparer reviews |
| >$1,000 | Source document required |

### Vendor master (control point for 1099, AP, fraud)

The vendor master SOP must require:

- **W-9 collection before first payment**
- **Annual W-9 refresh**
- **TIN matching** via IRS e-Services or Sovos
- **OFAC/SDN and DMF screening**
- **B-Notice response within 15 business days**
- **24% backup withholding via Form 945** if no response in 30 days

IRS penalties for 1099 errors run **$60-$340 per form**, **$680+ for intentional disregard with no cap.**

### AP workflow standard pattern (Bill, Ramp, Brex, Divvy/BILL Spend & Expense)

1. Capture (OCR)
2. 2-way / 3-way PO match
3. Coded GL/dimension
4. Multi-tier approval
5. Payment

**Required controls:**

- Segregation of duties (preparer ≠ approver ≠ payer)
- Approval thresholds (typical: <$1k auto, $1k-$10k manager, >$10k partner)
- Dual-factor on payment release
- One-way vs. two-way sync configuration documented (Ramp KB warns about duplicate bills when migrating from Bill.com)

### AI-assisted categorization

Botkeeper, Vic.ai, Truewind, Booke, Docyt, Keeper. **Auto-post only above a confidence threshold; surface exceptions for human review.** Never blind auto-post.

### Common gaps in Domain 4

- COA bloat (200+ overlapping accounts, "Ask My Accountant" dumping ground)
- No tolerance policy
- Deferred 1099 cleanup creating CP2100 storms
- Bank rules without governance
- Over-trust in AI without confidence gating

---

## Domain 5 — Reconciliations

**Core principle:** reconciliation is not substantiation. **Reconciliation** matches GL to one source. **Substantiation** also validates completeness and accuracy of the ending balance with reviewer sign-off.

### Risk-based balance-sheet substantiation program

Every account assigned: **owner**, **risk rating**, **reconciliation cadence**. Reconcile "to the lowest level of detail" (Yale, UMN, UPenn balance-sheet policies).

### Standard reconciliation template (FloQast/Numeric/BlackLine pattern)

- GL trial-balance figure (auto-pulled)
- Supporting documentation source and figure
- Aged reconciling items with expected clearance dates
- Variance analysis vs. prior period
- Preparer signature/date
- Reviewer signature/date

### Variance and aging thresholds

- **Variance ≥$1,000 OR ≥5% movement** triggers a narrative
- **Reconciling items aged >60 days** require partner escalation
- Stale items >90 days carried indefinitely is a control failure

### Cadence by account type

| Account type | Cadence |
|---|---|
| Bank | Monthly minimum (weekly mid-market, daily high-volume) |
| Credit card | Monthly with statement |
| Loans | Monthly to amortization schedule |
| Merchant accounts | Daily-weekly settlement |
| Intercompany | Monthly with elimination matrix |
| Payroll clearing | Each pay period |
| AR/AP sub-ledger | Monthly |
| Inventory | Monthly perpetual roll-forward |
| Prepaids / deferred revenue | Monthly waterfall |
| Fixed assets / ASC 842 ROU | Monthly |

### Tools

- **FloQast** — Reconciliation Management, centralized status, automated transaction matching
- **Numeric** — AI-native, auto-population, many-to-many matching, auto-submit below materiality
- **BlackLine** — enterprise SAP-aligned
- **Trintech Cadency/Adra** — mid-market

### Common gaps in Domain 5

- "Done = balanced" with no aging of reconciling items
- Preparer = approver (control failure)
- No fraud lens on bank recs
- Recons performed after close instead of integrated
- Spreadsheet-only with no version control
- Stale items >90 days carried indefinitely
- Skipping low-balance accounts

---

## Domain 6 — Period-end / month-end close

**Core principle:** a documented checklist with task owners, dependencies, and due dates is the single highest-leverage close intervention.

### Days-to-close benchmarks

| Tier | Days |
|---|---|
| Top performers | 1-3 business days |
| High performers | 3-5 |
| Mid-market median | 6-7 |
| Acceptable | 5-10 |
| Small outsourced engagements | 10-15 |

Eagle Rock CFO research: **60-70% of close delays come from missing information** — making PBC discipline (Domain 2) the upstream control.

### Reference 5-day close (Keiter, FloQast, Numeric, Karbon)

| Day | Activities |
|---|---|
| 0-1 | Lock inputs, run preliminary cleardown |
| 1-2 | Reconcile cash, AR, AP |
| 3 | Process accruals/deferrals/intercompany |
| 4 | Balance-sheet substantiation and flux narrative |
| 5 | Reviewer/partner sign-off, generate package, lock period |

### Soft vs. hard close

- **Soft close** — finalizes operational accruals for management financials. Typical monthly CAS standard.
- **Hard close** — substantiates every balance-sheet account with full GAAP accruals and tax provision. Typical quarterly/annual.

### Tools

- **FloQast** — avg 1.3-month implementation, ~3 days off close (vendor-reported)
- **Numeric** — AI-native with flux agent
- **BlackLine** — enterprise
- **Karbon** — workflow-level checklists with role-based tasks

### Common gaps in Domain 6

- No documented checklist (tribal knowledge collapses on turnover)
- Rubber-stamp reviews
- Period not locked
- No flux/variance analysis
- Single-day close attempts without dependency mapping

---

## Domain 7 — Financial reporting

**Core principle:** GAAP is the floor; insight is the ceiling. Reporting is a service, not a deliverable.

### Standard 8-element monthly management package

1. Cover / executive summary with 3-5 bullet insights and traffic-light scorecard
2. Income statement (current month vs. budget vs. PY vs. TTM, both $ and % variances)
3. Balance sheet with key ratios
4. Cash flow statement (indirect for GAAP, direct for short-horizon forecasts)
5. Industry-specific KPI dashboard
6. Variance narrative with materiality thresholds (typically the greater of 5% or a dollar floor)
7. AR/AP aging summaries
8. Rolling 13-week or 12-month cash forecast

### Audience-tailored variations

- **Board packages** — 5-8 strategic KPIs at higher altitude (per ClearPoint Strategy)
- **Nonprofit packages** — functional-expense views (FASB ASC 958 / Form 990); link variance explanations to mission and strategy
- **Lender packages** — emphasize covenants

**Jason Blumer's pattern:** condense every client P&L to 12-14 standardized lines mapped to internal benchmarks. Useful AI normalization template.

### SSARS 27 — most consequential recent SOP development for CAS

**Issued April 7, 2025; effective Dec 15, 2026.** Clarifies that **AR-C 70 (Preparation of Financial Statements) is NOT required when financial-statement preparation is not the primary objective of an engagement performed under CS 100 (Consulting Services).**

Many firms had been incorrectly applying AR-C 70 because their engagement letters disclaimed financial-statement preparation; SSARS 27 forces a clean elect/document path.

**Required SOP actions:**

- Every CAS engagement letter affirmatively elects or disclaims under SSARS
- Document the SKE designation per ET §1.295
- Follow the *1136 Tenants* CAMICO-cited rule of explicit scope

CPA.com published a SSARS Standard Clarification FAQ (August 2025) with a SSARS-vs-CS-100 decision-tree flowchart.

### Reporting tools

| Tool | Strength |
|---|---|
| Fathom | Backward-looking management reporting, KPI library, portfolio benchmarking, consolidations up to ~300 entities |
| Spotlight Reporting | Industry templates, comparative reports |
| Jirav | Driver-based 3-statement FP&A, scenario planning |
| Reach Reporting | Excel-like template library |
| LiveFlow | Google Sheets/Excel-native QBO dashboards |
| G-Accon | Bidirectional data pipe |

### Common gaps in Domain 7

- One-page P&L delivered without context (clients perceive "I just get a P&L by email")
- No flux narrative
- No KPI dashboard
- SSARS 27 misapplication
- Inconsistent format across clients (no firm template)

---

## Domain 8 — Payroll & sales tax intersections

### Payroll touchpoints (GL impact is material)

The SOP must:

- Reconcile **payroll clearing to zero** each pay period
- Tie **payroll register to GL monthly**
- Tie **941 to GL** wages and tax expense quarterly
- Tie **W-2 totals to GL** annually

**Common errors:**

- Booking net pay instead of gross (understates expense, breaks 941 tie-out)
- Missing Gusto Auto-Adjust FICA reconciliations at quarter-end
- Year-end W-2s not tied before issuance

### Year-end 1099/W-2 hygiene (monthly, not January sprint)

- Every new vendor flagged for W-9 and 1099 eligibility
- Vendors approaching $600 flagged
- CC-paid vendors excluded (1099-K issuer responsibility)
- November preliminary list pull
- December TIN match and SDN/DMF screening
- January 31 e-file by IRS deadline

### Sales tax SOP elements

- Connect sales channels to both accounting system and sales-tax tool (Avalara AvaTax, TaxJar, Anrok, Kintsugi, Numeral)
- Reconcile sales-tax liability GL to tool reports monthly
- Nexus dashboard review quarterly
- Standardized nexus questionnaire on onboarding
- Documented hand-off to a SALT specialist when complexity exceeds firm capability

**Post-Wayfair economic-nexus thresholds:** typically $100k or 200 transactions, varies by state. Continuous monitoring required.

### Common gaps in Domain 8

- Booking net pay instead of gross
- 1099 cleanup deferred to January
- No sales-tax nexus monitoring
- No documented SALT-specialist handoff trigger

---

## Domain 9 — Advisory & CAS deliverables

**Core principle:** the AICPA / CPA.com **CAS 2.0® framework** is the reference architecture. Four pillars:

1. **Strategy & Governance**
2. **Practice Development**
3. **Technology Solutions**
4. **Operational Excellence** (explicitly identifies "methodology blueprinting" and "process and procedure documentation" as requirements)

CAS Service Maturity Model: Financial CAS → Business Insights CAS (non-financial data, industry-specific KPIs, year-round advisory dialogue).

### 2024 CAS Benchmark Survey — leading-firm pattern

- **17% median CAS revenue growth**
- **$1.6M median CAS revenue**
- **$156,250 NCFPP median (+29%)**
- 78% of practices have dedicated CAS-only staff
- Firms with formal CAS business plans earn ~$10K more revenue per client
- **Niche-defined practices earn 38% higher median CAS revenue and 51% higher net revenue per client**
- Firms with significant CFO/business-insights revenue post >30% higher monthly recurring revenue

### Trusted Business Advisor (TBA) framework

Bill Reeb and Dom Cingoranelli (Succession Institute, AICPA PCPS): ask diagnostic questions, listen, "uncover critical client needs in 10 minutes or less," help clients prioritize and quantify the value of solving each issue.

**Tom Hood T-shaped model:** deep technical expertise + wide boundary-crossing competencies (digital, business, leadership, communication, ethics, agile).

### Cadence SOPs

- **Monthly advisory meeting** — 60-90 min, post-close, 10-15 min on the package then variance and forward look
- **Quarterly Business Review** — 48-hour pre-read, traffic-light KPI scorecard, decisions-required section, 3-5 next-quarter priorities
  - **81% of assigned KPI owners never update metrics** — QBRs are the accountability mechanism
- Cash conversations exceed monthly when clients are hiring, expanding, or runway-constrained

### Forecasting and budgeting

- Annual budget kicked off **8-12 weeks before fiscal year-end** with driver-based build
- Rolling forecasts (only 19-25% of companies use them — CAS differentiator)
- **13-week cash flow forecast** as the gold standard for short-horizon liquidity

### 13-week cash flow forecast SOP

- Direct method
- Three sections (operating / investing / financing)
- Rolling weekly updates with actuals
- EBITDA-to-cash reconciliation
- Scenario rows
- Minimum-cash floors
- Auto-alerts when runway drops below 8 weeks

### Industry-specific KPI dashboards

| Industry | Key KPIs |
|---|---|
| SaaS | MRR, ARR, NRR, CAC payback, LTV:CAC, Rule of 40, SaaS Quick Ratio, gross margin >75-80% |
| Restaurant | Prime cost ≤60%, average ticket, sales per labor hour |
| Nonprofit | Program expense ratio ≥85%, fundraising efficiency, months of operating cash, restricted vs. unrestricted net assets |
| Construction | WIP schedule (over/under-billings), gross profit per job, days in retainage |
| Healthcare | RVUs, days in A/R, payer mix |

### Virtual/Fractional CFO standard deliverables

- Monthly three-statement package within **5-10 business days of close**
- Rolling 13-week cash forecast
- KPI dashboard
- Budget-vs-actual with reforecast
- 60-90-min monthly strategy call

**Quarterly:** annual budget build, board-ready QBR, scenario plans, debt covenant tracking, fundraising prep.

**Project add-ons** (typically $15K-$50K each): Series A/B fundraising, M&A diligence, ERP selection, system migration.

**Engagement scope:**

| Tier | Hours/mo | Fee/mo |
|---|---|---|
| Hourly | varies | $175-$450/hr |
| Early-stage | 8-10 | $1,400-$2,800 |
| Mid-tier | varies | $5,000-$12,000 |
| Premium | varies | $12,000-$20,000+ |

### Common gaps in Domain 9

- Leadership misalignment on what CAS is
- Trying to serve every industry
- Owner-delivered advisory creating a $1M-$1.5M revenue ceiling (Blumer's bottleneck)
- No formal CAS business plan
- Treating CAS as back-office
- SSARS-27 misapplication
- Inconsistent meeting cadence
- No defined KPIs in the engagement letter
- Tech-stack sprawl without methodology blueprinting
