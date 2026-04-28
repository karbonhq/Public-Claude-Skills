# Layer 5 — Governance (Domains 15-16)

Risk, compliance, security, and the AI overlay. Load this when mapping or building SOPs in risk/compliance/security or AI/agentic workflows.

---

## Domain 15 — Risk, compliance & security

### Independence — the bedrock for any firm doing both attest and CAS/bookkeeping

The **AICPA Code's Nonattest Services subtopic (ET §1.295)** governs CAS for attest clients.

**Threats catalogued in §1.210.010:**

- Self-review
- Advocacy
- Adverse interest
- Familiarity
- Undue influence
- Financial self-interest
- Management participation

### Critical independence rules

- A CPA may not assume management responsibilities (§1.295.030)
- Management must designate an individual with **suitable skill, knowledge, and experience (SKE)** to oversee the service
- Bookkeeping, payroll, and disbursement services are **explicitly listed nonattest services subject to safeguards**

### Hosting Services interpretation §1.295.143

Effective July 1, 2019. **If a firm acts as the sole host of a client's financial information system (e.g., GL maintained on firm's servers), independence is impaired.** Copies sent to client do NOT cure it.

### Yellow Book (GAGAS)

Treats financial-statement preparation as **always a significant threat.**

### Unpaid fees §1.230.010

**Significant fees outstanding >1 year impair independence absent safeguards.**

### Cumulative effect

The cumulative effect of multiple nonattest services must be evaluated and documented (peer-review focus).

---

### IRS Publication 4557 — Safeguarding Taxpayer Data

Federal guidance applicable to **all paid tax preparers and PTIN holders.**

**WISP is mandatory for PTIN renewal effective 1/1/2023.**

**Required components:**

- Designate a **Data Security Coordinator**
- **Security Six**:
  1. Anti-virus with auto-update
  2. Firewalls
  3. MFA
  4. Backup software with offline copy
  5. AES-256 drive encryption
  6. VPN
- Strong passwords
- Encrypt sensitive files and emails
- Offline backups
- Final pre-e-file review of direct-deposit info
- Telecommuting policy

**Companion publications:** Pub 5708 (template + sample WISP), Pub 5293, Pub 4524.

**Enforcement:**

- EFIN revocation
- FTC Safeguards penalties up to ~$46,517 per violation per day
- Criminal §7216 referral

---

### FTC Safeguards Rule (16 CFR Part 314)

Under GLBA §501(b), amended Dec 9, 2021, with compliance deadline June 9, 2023, and **breach notification effective May 13, 2024.**

**All paid tax preparers are "financial institutions"** — bookkeeping/CAS firms with tax preparation are squarely covered. Section 314.2(h) lists 13 examples explicitly including tax preparation firms.

### Small-entity exemption (§314.6)

Firms with NPPI on **fewer than 5,000 consumers** are exempt from **four specific requirements only:**

1. Written risk assessment
2. Continuous monitoring/pen testing
3. Written incident response plan
4. Annual board report

**The core obligation and Qualified Individual remain.**

### Nine elements (§314.4)

1. Designate **Qualified Individual**
2. Written risk assessment
3. Safeguards (access controls, data inventory, encryption at rest/in transit, secure development, MFA, secure disposal, change management, activity logging)
4. Regular testing (continuous monitoring or annual pen testing + biannual vulnerability scans)
5. Personnel training and qualified personnel
6. Service provider oversight
7. Periodic update
8. Written incident response plan
9. Annual written report by QI
10. **Breach notification within 30 days** of discovering a notification event (unauthorized acquisition of unencrypted info of ≥500 consumers)

---

### Data security best practices

- **Full-disk encryption** on laptops/mobile
- **TLS 1.2+** in transit
- **AES-256** at rest
- **MFA ranking:** authenticator app > push > SMS > none
- **RBAC** with quarterly access reviews and immediate de-provisioning at termination
- EDR, SIEM logging, automated patching
- Secure portals replacing email attachments

### Free WISP templates

- AICPA "Gramm-Leach-Bliley Act WISP Template"
- IRS Pub 5708 sample
- CAMICO
- Rightworks
- Tech 4 Accountants
- TaxDome

---

### SOC 2 / SSAE 18

A firm needs SOC 2 when it:

- Provides outsourced accounting/CAS to public-company customers
- Is a vendor of regulated industries
- Has enterprise clients requiring it
- Hosts client data (consider §1.295.143 simultaneously)
- Provides shared-services accounting

### Trust Services Criteria

- **Security** (mandatory)
- Availability
- Processing Integrity
- Confidentiality
- Privacy

**Type 1** (point in time) vs. **Type 2** (operating over typically 6-12 months).

**Only licensed CPA firms may issue SOC 2 reports per AICPA AT-C 205.**

---

### Client confidentiality under IRC §7216 and §6713

**Criminal misdemeanor for tax preparers who knowingly disclose return information for any purpose other than preparing the return without consent.**

- **Treas. Reg. §301.7216-2** — defines permitted disclosures
- **Treas. Reg. §301.7216-3** — required consent format:
  - Separate documents for use vs. disclosure
  - Specific recipient or descriptive class
  - Purpose
  - Signature
  - Valid 1 year
  - **No retroactive consent**

State rules (CA, IL, NY) extend confidentiality more broadly.

---

### AI usage policies for firms

Must address:

- **Confidentiality breach** when client data goes into public LLMs (consumer tier may use input to train models)
- **§7216 implications** when AI is used substantively to prepare returns (boilerplate consent likely insufficient)
- **AICPA Code §1.700** (Confidential Client Information) and **§1.400** (Acts Discreditable) implications
- **Hallucination / quality control** under SQMS 1

CAMICO has published a sample Generative AI Chatbot Usage Policy.

### Standard SOP components for AI usage policies

- Authorized vs. limited vs. prohibited use categories
- **Approved tool list** (Microsoft Copilot in M365 tenant or OpenAI Enterprise tier preferred)
- Prohibition on inputting **PII/SSNs/financial account numbers** into consumer tools
- Mandatory human review of AI output before client delivery
- Documentation of AI use in workpapers
- Training and attestation
- Client disclosure language
- **Vendor vetting** (SOC 2, data residency, no-training contractual provisions)
- Periodic policy review

---

### Breach response SOPs (required by §314.4(h))

Aligned to **NIST SP 800-61 phases:**

1. **Detection / identification**
2. **Containment**
3. **Eradication / investigation** (forensic engagement)
4. **Recovery** (validate clean systems)
5. **Notification:**
   - FTC within 30 days for ≥500 consumers unencrypted
   - State AG and consumer notification per state law (30-90 days)
   - IRS Stakeholder Liaison
   - Affected clients
   - Cyber insurer
   - FBI IC3
   - Treasury/FinCEN if wire fraud
6. **Post-incident lessons learned and WISP update**

### Common gaps in Domain 15

- No written WISP
- No designated Qualified Individual
- No annual QI report
- §1.295.143 hosting violation (firm hosts client GL with no copy back)
- Offshore work without §7216 consent
- Public LLM use with client data
- No incident response plan tested
- Unpaid fees >1 year on attest clients

---

## Domain 16 — AI & agentic workflows

The **most consequential and fastest-evolving SOP domain.**

Karbon's State of AI 2025: 85% of accounting professionals are excited about AI but only 37% of firms invest in AI training. The 2026 update: 98% using AI in some capacity, 55% several times daily, with mid-sized (21-50) and large (200+) firms leading. Firms saved an average of **18 hours per employee per month** automating routine tasks.

CPA.com 2025 AI in Accounting Report (with Caseware): the shift is from "isolated efficiency plays" to "smarter structures: rethinking roles, redefining value, and rewiring workflows for a digital-first, insight-led model."

### Human-in-the-Loop (HITL) — the dominant ethos

- KPMG's Aisha Tahirkheli: "everyone in our firm serves as a human in the loop."
- RSM's Sergio de la Fe: "any AI output is traceable to a specific professional, who takes ownership of whatever the AI produces."
- Armanino's OJ Laos cautions that HITL has become a generic term and accountability must be embedded in every user, not delegated to oversight people.

### HITL checkpoint patterns to encode in SOPs

| Pattern | Description |
|---|---|
| **Approval gates** | AI must request human sign-off before executing certain actions (posting JEs above a threshold, sending a client email, paying a vendor) |
| **Confidence-based routing** | AI confidence below threshold (e.g., transaction categorization <95%) routes to human; above auto-executes and logs |
| **Exception-only review** | Humans only review anomalies; AI auto-handles the rest (Truewind, Numeric, Vic.ai pattern) |
| **Pre-delivery review** | Any client-facing output requires named professional review before release |
| **HOTL ("Human-On-The-Loop") periodic sampling** | Humans audit a statistical sample and watch for drift in high-volume autonomous workflows |

### The "HITL Fallacy" — a critical caution

When humans review hundreds of AI outputs daily, decision fatigue produces rubber-stamping; oversight becomes symbolic.

**SOPs must:**

- Right-size review burden
- Embed materiality thresholds
- Rotate reviewers

### Agent oversight tiers

| Tier | Description | Example |
|---|---|---|
| **Tier 0 — Suggestion** | AI proposes; human always acts | Karbon AI smart task suggestions |
| **Tier 1 — Copilot/Draft** | AI produces a first draft; human reviews and finalizes | Karbon AI email drafts, Numeric Flux Agent variance commentary, Truewind morning-queue journal entries |
| **Tier 2 — Bounded Autonomy** | AI executes within tight rules and materiality thresholds; human reviews exceptions | Truewind anomaly detection; Numeric auto-submit reconciliations within materiality with 30-day aging escalations |
| **Tier 3 — Full Autopilot** | AI executes end-to-end with periodic human sampling, drift monitoring, and audit logs | Vic.ai Autopilot, Botkeeper+Vic.ai integrated AP — Diesel Direct hit 99% invoice coding accuracy and 84% no-touch processing |

### Karbon AI Agents (launching 2026)

Agents "modeled after roles that already exist inside an accounting firm":

- **Bookkeeper Agent** — workpapers, reconciliations, document follow-ups
- **Tax Admin Agent**
- **Fractional CFO Agent** — forecasts, what-if
- **Client Onboarding Specialist Agent**

The **Karbon AI Agent Management System** lets firms:

- Enable/disable specific agents and capabilities
- Control what data each agent can access
- Review a complete audit trail of every agent decision with approve/edit/reject training over time

"Ask Karbon" (planned 2026) is a natural-language orchestration interface.

### Specific AI tools and SOP impact

| Tool | What it does | SOP impact |
|---|---|---|
| **Karbon AI** (Microsoft Azure OpenAI Service) | Email triage, summarization, drafted replies, urgency/sentiment scoring, smart task assignment, meeting transcripts | Triage SOPs assume AI prioritization with human override |
| **Numeric** | AI Flux Agent first-draft variance/flux explanations; smart subledgers; auto-submit reconciliations within materiality; 90%+ matching | Close calendars become RACI at task level with AI-assisted recs and AI-drafted flux memos |
| **Truewind** | Digital staff accountant — categorizes on historical patterns, auto-creates prepaid schedules and journal entries, identifies accrued expenses, anomaly detection | Bookkeeping SOPs shift from data-entry-then-review to AI-prepares-then-reviewer-approves-exceptions |
| **Vic.ai** | Trained on 500M+ live accounting documents; vendor identification, line-item GL coding | No template/no rule AP coding |
| **Botkeeper** | AI + human accountants service model; Botkeeper Operating System hub | Hybrid service model |
| **Aiwyn** | Four-component platform (Payments, Practice, Experience, Tax) with AI billing automation | 800+ firms |
| **Caseware AiDA** | Citation-linked outputs and PDF source highlighting | Audit-trail by design |
| Others | **Trullion**, **Blue J** (RSM), **RSM Atlas**, **"Ask Luca"** (RSM audit assistant) | |

### Prompt libraries — first-class SOP artifacts

Per Caseware: "a collection of proven prompt templates can help your team complete recurring accounting tasks with greater speed, accuracy, and consistency."

**Best practices:**

- Organize by task type or tool
- Use **STAR** methodology (Situation-Task-Action-Refine)
- Capture firm-specific style (tone, jurisdiction, citations, framework, period, lens)
- Decompose complex prompts into stepwise sequences (mirrors token-by-token generation, reduces hallucination)
- Pair with **RAG** (retrieval-augmented generation) anchored to authoritative knowledge bases
- Treat prompts as controls — Trullion: "your words are the controls. Treat them like working papers: clear, precise, and ready for someone else to follow and review"

**Library lifecycle:**

- Junior staff contribute and refine
- Senior staff draft expert templates
- Versioned in Notion/Confluence/Git
- Tested before promotion (golden test cases)
- Deprecated when models change
- Re-validated quarterly
- Owned by a **"Skills Librarian" or AI Champion**

### AI risk frameworks

#### NIST AI RMF 1.0 (Jan 2023; AI RMF 2.0 Feb 2024; AI 600-1 GAI Profile Jul 2024)

**Four core functions: GOVERN, MAP, MEASURE, MANAGE.**

**Seven trustworthy AI characteristics:**

1. Valid & Reliable
2. Safe
3. Secure & Resilient
4. Accountable & Transparent
5. Explainable & Interpretable
6. Privacy-Enhanced
7. Fair with Harmful Bias Managed

**Maps onto SOP design:**

- GOVERN → policy/committee/vendor
- MAP → tool inventory and regulatory mapping
- MEASURE → validation testing and drift
- MANAGE → prioritization and incident response

#### COSO Internal Control-Integrated Framework for Generative AI (2026)

AICPA is supporting org. Applies the ICIF five components to GenAI with a **capability-first taxonomy of eight types:**

1. Ingestion
2. Transformation
3. Posting
4. Orchestration
5. Judgment
6. Monitoring
7. Regulatory intelligence
8. Human-AI interaction

Each with tailored controls, illustrative metrics, risk matrices, and testing procedures.

#### ISO/IEC 42001

AI management system standard.

#### AICPA AI governance checklist

- Complete tool inventory
- Mapping to PCAOB/SEC/AICPA
- Explainable outputs meeting AS 1105 audit evidence standards
- Documentation of model logic, data, outputs, changes
- Sensitivity-classified inputs
- Encryption + RBAC + audit logs
- Staff training
- Periodic compliance reviews

#### State law landscape

- **Texas Responsible Artificial Intelligence Governance Act (HB 149)** — effective Jan 1, 2026
- **Utah SB 226**
- **EU AI Act Article 14** — mandates HITL design for high-risk AI systems

### Cautionary precedents

- ***Mata v. Avianca*** — sanctioned attorneys for non-existent ChatGPT case citations
- Academics retracting AI-fabricated case studies

**AI output must be independently verified; accountability sits with humans signing off.**

### Audit trails for AI-assisted work

Capture:

- Prompt + output + model version + timestamp + user
- Human edits and accept/reject decisions
- Tag deliverables disclosing AI involvement where required
- Outputs meet AS 1105 audit-evidence standards
- **Preserve logs for the same retention period as supporting workpapers (often 7+ years)**

### How SOPs change shape when AI does first-draft work

They become **control frameworks, not procedures.** Standard new structure:

1. **Prep step** — gather inputs, stage for AI
2. **AI step** — model/tool, versioned prompt, parameters, prohibitions
3. **Review/edit step** — factual accuracy, tone, compliance, citations (checklist not vibe)
4. **Sign-off step** — named accountable professional
5. **Logging step** — prompt, output, edits, reviewer, timestamp
6. **Feedback step** — errors feed back into prompt library or fine-tuning

### Firms publicly leading on AI

- BDO USA ($1B+ five-year AI investment, RAID team, AI Ambassadors)
- RSM US (Atlas, Ask Luca, Blue J, R&D credit AI assistant)
- KPMG (Trusted AI, KPMG PrivateBlok)
- Aprio ($300M five-year commitment, Charlesbank Capital Partners-backed)
- Withum, Armanino (AI Lab)
- EisnerAmper and Frank Rimerman (early Truewind partners)
- Innovative small firms: Books LA, Blumer & Associates

### Common gaps in Domain 16

- No written AI usage policy
- No approved/prohibited tool list
- No prompt library (every staff member uses different prompts)
- No oversight tier defined per AI use case
- No audit-trail capture for AI-assisted work
- No AI Champion or Skills Librarian
- No vendor vetting process for AI tools
- No client disclosure language
- HITL Fallacy (rubber-stamping due to volume)
