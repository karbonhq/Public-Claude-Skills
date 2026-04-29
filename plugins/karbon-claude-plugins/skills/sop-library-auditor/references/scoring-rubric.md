# Scoring Rubric

The skill uses **two scoring views**, both computed at the same time. The 3-state coverage view is the headline. The 5-axis maturity view is a drill-down detail accessible per-SOP and per-domain.

## View 1 (headline) — 3-state coverage + 15-field anatomy

Every domain (1–16) gets a single status:

- **Complete (green)** — domain has at least one SOP scoring ≥ 12/15 anatomy and there are no compliance-floor gaps within the domain. Covered well enough that the firm can run the work without tribal knowledge.
- **Partial (yellow)** — domain has at least one SOP scoring ≥ 7/15, but with material gaps (missing exceptions, RACI, controls, AI usage tagging, etc.) OR has multiple SOPs averaging Partial.
- **Missing (red)** — no SOP exists for the domain, OR every SOP in the domain scores < 7/15 anatomy, OR a compliance-floor gap is present.
- **N/A (grey)** — domain not in scope for this firm (e.g., Domain 9 Advisory at a firm doing 0% advisory; Domain 8 sales-tax components at a firm with no sales-tax obligations).

The dashboard headlines coverage as: *"X complete / Y partial / Z missing"* with a percentage. The percentage = `complete_count / (complete + partial + missing)` — N/A excluded.

### 15-field anatomy

For every existing SOP, score its completeness across these 15 fields (each 0/1/2):

1. **Title and ID** — Has a clear title and a stable identifier
2. **Purpose** — Why it exists, what business outcome, cost of getting it wrong
3. **Scope (and exclusions)** — What it covers AND what it doesn't
4. **Owner (Accountable)** — Single named owner (a person, not "the firm")
5. **Performers (RACI)** — Who's Responsible / Accountable / Consulted / Informed per step or step-bucket
6. **Frequency / trigger** — When it fires (calendar / event / on-demand)
7. **Inputs** — Typed list of artifacts needed before starting
8. **Outputs** — Named artifacts produced, with destinations
9. **Step-by-step procedure** — Discrete steps a junior or LLM can execute
10. **Controls (with materiality thresholds)** — Decision logic with explicit numbers (e.g., "$10," "30 days," "5% variance")
11. **Exceptions and escalation** — Enumerated edge cases, each with detection rule + handler + escalation path
12. **Tools, templates, prompts** — Named tools, file paths to templates, exact prompt strings if AI-assisted
13. **Authority / standard references** — IRS Pub 4557, SSARS 21–25, FTC Safeguards, AICPA SQMS, internal policy
14. **Review cadence and change log** — Stated review frequency + a populated changelog with dated entries
15. **AI usage** — If AI is used: which model, exact prompts, prohibited uses, human checkpoints. If not: stated explicitly that AI is not used.

Scoring within each field:
- **2 (●)** — Present and substantive
- **1 (◐)** — Present but partial (e.g., owner named but no RACI; controls listed but no thresholds)
- **0 (○)** — Missing entirely

Anatomy total: 0–30, displayed as `N/30` and also as `N×(15/30)/15` for a simpler "X out of 15" sense.

The 15-field grid in the dashboard renders one row per existing SOP, one column per field, color-coded ● ◐ ○ at a glance.

## View 2 (secondary) — 5-axis maturity score

Kept from the original framework. Computed per-SOP. Surfaced as a drill-down detail (radar chart in the per-SOP detail panel; per-domain rollup in the secondary view tab). Useful when the firm wants to understand *why* a Partial domain is partial — is it a Currency problem? An Adoption problem? An AI-readiness problem?

Five axes, each 0–2:

- **Existence** — 0 none / 1 informal / 2 formal document
- **Currency** — 0 >24 months or unknown / 1 12–24 months / 2 within 12 months
- **Coverage** — 0 narrative only / 1 some structure / 2 full structure (RACI, decision logic, I/O)
- **AI-readiness** — 0 no metadata / 1 some metadata / 2 SKILL.md-loadable
- **Adoption** — 0 shelfware / 1 sometimes / 2 templated and QC-checked

Total per SOP: 0–10. Domain rollup: average of in-scope SOPs.

| Range | Band |
|---|---|
| 0–3 | Crisis |
| 4–6 | Baseline |
| 7–8 | Mature |
| 9–10 | AI-Native |

The 5-axis view is intentionally less prominent than the coverage view — it's there for diagnosis, not for the at-a-glance read. Most firms don't need to internalize the 5-axis breakdown; they need to know which domains are red.

## Cross-walk between the two views

The two views are not orthogonal. Roughly:

| 3-state coverage | Typical 5-axis range |
|---|---|
| Complete | 8–10 (Mature / AI-Native) |
| Partial | 4–7 (Baseline / borderline) |
| Missing | 0–3 (Crisis) |

But they can diverge — an SOP can be Partial coverage with an AI-readiness score of 0 (good content, no metadata), or be Complete coverage with a low Adoption score (well-written shelfware). The drill-down exists for exactly these cases.

## Composite priority score (gap prioritization)

For every gap (a missing SOP, OR an existing SOP < 7/15 anatomy, OR an SOP flagged `crit`), compute a composite priority:

```
composite = risk + frequency + impact + effort
```

All four are 1–3:

- **Risk (1–3)** — Regulatory/financial exposure if absent. 1 = low, 3 = high (compliance floor, civil-penalty exposure).
- **Frequency (1–3)** — How often the work happens. 1 = annual or rare, 3 = daily/weekly.
- **Impact (1–3)** — Business value of getting it right (revenue tied, churn risk, reviewer-time saved). 1 = nice-to-have, 3 = core.
- **Effort (1–3)** — *Inverted scale.* 3 = low effort to fix (under one day), 2 = moderate (1–5 days), 1 = high (>1 week or needs policy decisions). Higher number = quicker win.

Composite range: **4–12**. Higher = build sooner.

Compliance-floor gaps (WISP, FTC Safeguards, SSARS engagement letter language, SQMS for SSARS firms) get a hard floor of composite = 11 regardless of formula. They are non-negotiable and the dashboard always surfaces them in the Immediate filter.

### Roadmap buckets — 30 / 60 / 90 / 180 day

The composite score buckets gaps into four time-horizons in the gap report and as filter pills on the dashboard:

| Bucket | Composite range | What goes here |
|---|---|---|
| **30-day** | 11–12 | Compliance floor + highest composite. Stop everything else if these are missing. |
| **60-day** | 9–10 | Highest-impact operational gaps. Where pain is felt monthly. |
| **90-day** | 7–8 | Advisory and AI-readiness. Strategic for the firm's 12-month goal. |
| **180-day** | 4–6 | Maturity and scale. Important but not urgent. |

A gap can be promoted up a bucket by the firm's strategic-goal weight (intake Q12):

- Goal `add_AI` → Domain 16 gaps promoted up one bucket
- Goal `add_CAS` → Domain 9 gaps promoted up one bucket
- Goal `scale` → Domain 1 (onboarding) and Domain 11 (workflow) gaps promoted up
- Goal `sell` → Domain 10 (QC) and Domain 14.5 (succession) gaps promoted up
- Goal `niche` → Domain-specific niche SOPs (under whatever domain houses them) promoted up

## SOP flags

Independent of coverage and anatomy scoring, every existing SOP gets zero or more flags that show up as colored tags in the dashboard:

- **`draft`** — Sitting in a Drafts folder or named "WIP" / "v3" / "DRAFT"
- **`stale`** — Last modified > 12 months ago, OR references tools/regs no longer current (e.g., "QBO Desktop," "Asana" if the firm migrated)
- **`stale-risk`** — Stale AND covers regulated material (close, payroll, tax, security)
- **`dup`** — Duplicate of another SOP (same content, different file)
- **`orphan`** — Lives outside the canonical SOP location (Misc folder, Sarah's Notes, an email thread)
- **`scope`** — Scope-mismatch — single document covers multiple domains and should be split
- **`crit`** — Critical compliance exposure (WISP missing, deprecated reviewer checklist still referenced, wrong threshold, etc.)

Flags drive the "Stuck-in-draft," "Stale (>12 mo)," and "Critical compliance gaps" stat cards on the dashboard.

## Saving scores

`working/sop-inventory.json` carries the full scored inventory. Schema:

```json
{
  "firm_name": "Acme CPAs",
  "size_tier": "4-15",
  "scoring_date": "2026-04-29",
  "coverage": {
    "complete": 1,
    "partial": 7,
    "missing": 8,
    "na": 0,
    "percentage": 6.25
  },
  "stats": {
    "documents_inventoried": 19,
    "procedural_sops": 13,
    "d