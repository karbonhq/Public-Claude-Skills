# Layer 4 — Enablement (Domains 12-14)

The infrastructure that makes the work possible. Load this when mapping or building SOPs in tech stack, people/RACI, or internal operations.

---

## Domain 12 — Technology stack & integrations

### Architecture pattern: hub-and-spoke

GL or practice management at the hub. Layered architecture:

| Layer | Examples |
|---|---|
| **System of Record (GL)** | QBO, Xero, Sage Intacct, NetSuite |
| **System of Work (Practice Management)** | Karbon, Canopy, TaxDome, Jetpack, Financial Cents |
| **System of Engagement (client portal)** | Liscio, Karbon, TaxDome |
| **Record-adjacent — AP** | Bill, Ramp, Brex |
| **Record-adjacent — payroll** | Gusto, Rippling, ADP, Paychex |
| **Reporting layer** | Fathom, Jirav, LiveFlow, Spotlight |
| **Close layer** | FloQast, Numeric, BlackLine |
| **Document/DMS** | SmartVault, Karbon, ShareFile |
| **Glue** | Native APIs preferred, Zapier/Make as fallback, Workato/Tray for large firms |

### Tech stack archetypes by firm size

**Small bookkeeping firm (1-10):**
QBO/Xero + Jetpack or Financial Cents + Bill or Ramp + Liscio + Fathom or LiveFlow + SmartVault, optionally Keeper for QC.

**Mid CAS firm (10-50):**
QBO/Xero/Intacct + Karbon Business or Canopy + Bill + Ramp + Liscio + Fathom or Jirav + SmartVault + FloQast or Numeric + Botkeeper/Truewind for AI bookkeeping leverage.

**Large firm (50+):**
NetSuite/Intacct + Karbon Enterprise or CCH Axcess or Aiwyn + Numeric/FloQast/BlackLine + Ramp/Bill + Jirav + SmartVault/iManage + Snowflake data warehouse + Workato iPaaS + Karbon AI Agents pilot.

### Emerging integration patterns

**MCP (Model Context Protocol)** — Numeric exposes MCP for AI-agent orchestration. This is becoming the standard interface for AI agents to talk to firm tooling.

### Vendor security baseline

**SOC 2 Type II should be a minimum bar** for all data-touching vendors. Verified at: TaxDome, SmartVault, Karbon, Truewind, Numeric.

### Common gaps in Domain 12

- App fatigue and rekeying
- No defined System of Record per data type (contact data drifts across CRM/PM/GL)
- One-way integrations masking data quality issues
- Underestimated implementation timelines (FloQast 1.3-month average, vendor-reported)
- Inconsistent security posture across vendors
- AI tools deployed without review controls (violates SQMS 1)

---

## Domain 13 — People, training & RACI

**Core principle:** "one-firm" orientation beats eat-what-you-kill (Marc Rosenberg). Under SQMS 1, firms must identify quality risks tied to "resources" (human, technological, intellectual) — **HR is now an attest-quality control.**

### RACI standards

Each task has one Accountable owner; every important task has at least one Responsible party.

**Critical processes that require explicit RACI:**

- Client onboarding
- Engagement-letter issuance
- Independence checks
- Billing/collections
- IT provisioning
- Security incidents
- Vendor approval
- Partner admission

**Numeric's pattern** — applying RACI at *task level* rather than *process level* — is best practice for AI-augmented work. When a step involves AI, RACI must explicitly identify which substeps the AI handles vs. the human.

### Career ladders

**Traditional public accounting:**
Intern → Staff (0-2 yrs) → Senior (3-6) → Manager (5-7) → Senior Manager (8-12) → Director/Principal → Partner (typically 10-17+ yrs; only ~1 in 50 makes partner per AICPA data cited by Prosple)

**CAS-specific track (CPA.com, CohnReznick):**
Bookkeeper → Senior Bookkeeper → CAS Accountant → CAS Manager/Controller → Outsourced/Fractional Controller → Outsourced/Fractional CFO → CAS Practice Leader

CPA.com explicitly endorses non-CPA pathways. Intuit's CAS Foundations Pathway provides skills-based curriculum.

### Training program requirements

- **Onboarding** — firm tour, ethics/Code of Conduct, mandatory WISP/security training under §314.4(e), confidentiality, software stack
- **CPE** — 40 hrs/yr typical
- **CAS curriculum** — CPA.com CAS 2.0 Methodology, Intro to CAS 4-CPE Workshop, CAS Roadmap Workshop
- **Soft skills** — client conversations, advisory framing, listening, change management (emphasized by Upstream Academy and ConvergenceCoaching)

### Offshoring oversight (critical and frequently mishandled)

AICPA 2023 MAP survey: 30% of firms outsource domestically, 25% offshore, another 12% planning offshore.

**Top destinations:** India, Philippines, Vietnam, Mexico, Brazil.

### Mandatory legal gating — IRC §7216

**Criminal misdemeanor up to $1,000 + 1 yr imprisonment; up to $100,000 under §6713 for ID theft cases.**

**Written taxpayer consent is required** before disclosing tax return information to any preparer outside the U.S.

**Treas. Reg. §301.7216-3** specifies the required elements:

- Identify taxpayer and preparer
- Identify recipient
- Identify purpose
- Dated signature
- Statement that information will be disclosed to preparers located abroad

**Valid 1 year. No retroactive consent.**

### Operating SOPs for offshoring

- Written job descriptions tailored to offshore role
- Documented review workflow
- Secure VDI access (no local download)
- MFA
- NDA + background checks
- Data residency clauses
- SOC 2 from BPO
- Quarterly QC sampling
- Cultural and process onboarding

### Performance management

Goal areas span: production, role fulfillment, strategic non-production goals, intangibles (mentoring, teamwork), client service quality.

**Cadence:** annual goal setting, mid-year check, year-end review, plus engagement-level evaluations.

### Compensation philosophy

12 systems exist; compensation committee dominates at 8+ partner firms. Multiple-of-compensation method common for partner buyouts (~2.4× average comp at 80% of revenue per 2012 Rosenberg MAP, with PE-driven multiples now higher).

### Common gaps in Domain 13

- No documented RACI for critical processes
- No SQMS 1 resources assessment
- Offshoring without §7216 consent (criminal exposure)
- No mandatory WISP/security training
- No CPE tracking system
- Unwritten compensation rules (partner-by-partner intuition)

---

## Domain 14 — Internal firm operations

Operations enable the professional services and map back to SQMS 1's Resources component.

### HR handbook essentials

- At-will employment
- EEO
- Anti-harassment
- ADA, FMLA
- PTO
- Jury duty
- Expense reimbursement
- Remote/hybrid policy
- Technology acceptable use
- Confidentiality (linked to AICPA §1.700 and §7216)
- Conflicts of interest
- Outside employment
- Social media
- Whistleblower
- Non-solicitation
- Progressive discipline
- Termination and data-access revocation
- CPE reimbursement
- Mandatory training acknowledgments

### IT operations

- **MDM** — Intune, Jamf
- **Standard-build images**
- **Full-disk encryption**
- **Auto-patching**
- **Lost-device wipe**
- **Centralized SaaS inventory** and SAM compliance
- **BYOD with containerization**
- **SSO** (Azure AD/Okta) with conditional access
- **Privileged access management**
- **3-2-1 backup rule with at least one immutable/offline copy** for ransomware resilience

References: Right Networks (accounting-firm-specific security guides), Practice Protect (IAM).

### Business continuity / disaster recovery

**Process:**

1. Business Impact Analysis
2. Critical systems with **RTO and RPO per system**
3. Alternate worksite plan
4. Vendor outage playbook (CDK 2024 incident is the cautionary reference)
5. Communications plan
6. **Annual tabletop and a live restore test**

**Distinction:**

- **IR Plan** handles adverse events
- **DR Plan** handles tech recovery
- **BC Plan** handles broader operational continuity

The **AICPA Disaster Relief Resource Center** provides templates.

### Succession planning — THE #1 endemic problem

AICPA PCPS 2016 survey:

- **75% of CPAs plan to retire within 15 years**
- Only **44% of multi-owner firms have written succession plans**
- Only **7% of solo firms have practice continuation agreements**

### Three primary succession paths

1. **Internal transition** — current best-practice goodwill ~78% of revenue per Rosenberg, with PE-driven CAS/advisory firms now at 1.5x-2.5x revenue per Madras Accountancy 2024
2. **M&A or external sale**
3. **Practice continuation agreement**

### Buyout structure (Rosenberg Multiple of Compensation)

- Retiring partner's avg comp × ~2.4 multiplier
- Payout 5-10 years
- Deferred compensation tax treatment

**Mandatory retirement age 65-67** with year-by-year extensions recommended.

### Transition runway (2-3 years)

| Year | Retiring partner activity |
|---|---|
| 1 | Reduces 20-30% |
| 2 | 50/50 |
| 3 | Advisory only |

### Vendor management under FTC §314.4(f) and SQMS 1

- Tier vendors by data sensitivity
- SOC 2 Type 2 review
- Financial stability check
- Security questionnaire (CAIQ or SIG-Lite)
- Insurance certificates
- Data residency

### Vendor contract requirements

- Confidentiality
- Security requirements
- **Breach notification 24-72 hrs**
- Audit rights
- Data destruction
- Subcontractor controls
- Indemnification

**Cadence:** Annual reassessment, quarterly review of Tier 1.

### Insurance stack

| Policy | Purpose |
|---|---|
| Professional liability / E&O | CAMICO largest CPA-specialized carrier; Tokio Marine HCC up to $3M/$3M |
| Cyber liability | First- and third-party (avg data-breach cost $4.88M per IBM 2024) |
| General liability | Standard |
| Workers' comp | Per-state |
| EPLI | Employment practices |
| Fidelity bond | Theft/embezzlement |
| D&O | Larger firms |
| Business interruption | Operational losses |
| Umbrella/excess | Layered coverage |

**Critical: E&O typically does NOT cover cyber events. Both required.**

### Common gaps in Domain 14

- No written WISP (direct violation of FTC Safeguards)
- 3-2-1 backup not implemented (ransomware exposure)
- No tested IR/DR/BC plan (most firms have plans they've never tested)
- No succession plan (most firms — 56% of multi-owner, 93% of solo)
- No vendor management cadence
- E&O without cyber coverage
- IT decisions made without documented review
