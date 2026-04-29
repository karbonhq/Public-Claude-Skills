# SOP Coverage Report — {{firm_name}}

**Generated:** {{scoring_date}}
**Size tier:** {{size_tier}} ({{headcount}} headcount, {{partners}} partner(s))
**Service mix:** {{service_mix_summary}}
**Strategic goal (12 months):** {{strategic_goal}}

---

## At a glance

- **Documents inventoried:** {{documents_inventoried}}
- **Procedural SOPs:** {{procedural_sops}} (the rest are reference material, drafts, or archive)
- **Drafts unfinalized:** {{drafts_unfinalized}}
- **Coverage:** **{{coverage_percentage}}%** — {{complete_count}} complete / {{partial_count}} partial / {{missing_count}} missing (of {{in_scope_count}} in-scope domains)
- **Critical compliance gaps:** {{critical_compliance_count}}
- **Stuck-in-draft:** {{stuck_in_draft_count}}
- **Stale (>12 months):** {{stale_count}}

The interactive dashboard at [`sop-dashboard.html`](sop-dashboard.html) shows the same data clickably and includes a per-SOP 5-axis maturity drill-down.

---

## Headline findings

{{headline_findings_paragraph}}

---

## Methodology

This audit applied the AI-Ready SOP Framework — 16 domains organized across 5 operating layers (Value chain, Production, Quality, Enablement, Governance). Each domain receives a single coverage status (Complete / Partial / Missing / N/A) based on the SOPs mapped to it. Each existing SOP is also scored across 15 anatomy fields (present / partial / missing) and as a secondary diagnostic across 5 maturity axes (Existence, Currency, Coverage, AI-readiness, Adoption — each 0–2 for a 0–10 total).

The expected SOP set was tailored to {{firm_name}}'s size, service mix, niche concentration, and strategic goal. Domains irrelevant to the firm (e.g., Domain 9 Advisory at a 0%-advisory firm) are marked N/A and excluded from coverage percentages. Compliance-mandatory SOPs (WISP, FTC Safeguards, SSARS engagement letter language, SQMS for SSARS firms) are scored separately as a hard floor — they are non-negotiable regardless of overall coverage status.

Coverage status is a heuristic for prioritization, not an audit opinion. Compliance determinations are the work of {{firm_name}}'s CPA and legal counsel.

---

## Coverage by layer

| Layer | Domains | Complete | Partial | Missing | N/A |
|---|---|---|---|---|---|
| Value chain | 1, 2, 3 | {{a_complete}} | {{a_partial}} | {{a_missing}} | {{a_na}} |
| Production | 4–9 | {{b_complete}} | {{b_partial}} | {{b_missing}} | {{b_na}} |
| Quality | 10, 11 | {{c_complete}} | {{c_partial}} | {{c_missing}} | {{c_na}} |
| Enablement | 12, 13, 14 | {{d_complete}} | {{d_partial}} | {{d_missing}} | {{d_na}} |
| Governance | 15, 16 | {{e_complete}} | {{e_partial}} | {{e_missing}} | {{e_na}} |

---

## Compliance posture

| Regime | Required for {{firm_name}}? | Documented? | Gap |
|---|---|---|---|
{{compliance_table_rows}}

{{compliance_narrative}}

**Critical:** This skill flags whether documentation exists. It does not opine on whether {{firm_name}} would pass an audit. Engage counsel and your CPA on compliance determinations.

---

## Domain-by-domain findings

{{per_domain_sections}}

Each domain section above includes: status (Complete / Partial / Missing / N/A), the SOPs mapped to it, identified gaps, and any flags (draft, stale, dup, orphan, scope, crit) on existing SOPs.

---

## Recommended starting point

**{{recommended_start_lead}}**

{{recommended_start_body}}

**Lowest-effort win on the same day:** {{recommended_quickwin}}

---

## Prioritized roadmap

Composite priority = Risk + Frequency + Impact + Effort (each 1–3, sum 4–12). Higher = build sooner. Compliance-floor gaps are floored at composite 11.

### 30-day — Compliance floor + highest composite

{{roadmap_30}}

### 60-day — Highest-impact operational gaps

{{roadmap_60}}

### 90-day — Advisory and AI-readiness

{{roadmap_90}}

### 180-day — Maturity and scale

{{roadmap_180}}

---

## Interview captures

The skill captured the following SOPs through structured interviews with {{firm_name}}'s team. Each is in `interview-captures/` and follows the 15-field anatomy template.

{{capture_list}}

Sections marked `[NEEDS INPUT]` indicate tribal knowledge that wasn't fully extracted in the interview — those need a follow-up before the SOP can move from `draft` / `working` status to `active`.

Sections marked `[NEEDS POLICY DECISION]` indicate the firm hasn't yet made the underlying judgment call (e.g., "what's our materiality threshold?"). These are decisions, not documentation tasks.

---

## Maintenance cadence

To keep the library current — what separates a one-time clean-up from a durable knowledge asset:

- **Quarterly reviews** for high-risk SOPs: Domain 15 (security), Domain 6 (close), Domain 8 (payroll), and any SOP with `risk_level: high`. Anchor reviews to the calendar — for a firm with tax exposure, post-tax-season May and post-year-end February work well.
- **Annual reviews** for the rest. One review every 12 months at minimum.
- **Trigger-based updates** any time a regulation changes (new state nexus, IRS Pub 4557 update, SQMS amendment), a tool changes (QBO migration, Karbon-Canopy switch), or any incident occurs. The SOP that was active when the incident happened gets a forced review.
- **Continuous improvement:** every engagement quality review surfaces at least one SOP update. Every AI-agent execution that hit an exception feeds a Field 11 (Exceptions) update.
- **One source of truth.** Pick one repository (Git, SharePoint with versioning, Karbon templates) and stop maintaining duplicates. Drift across two locations is worse than no documentation in one.

---

## Recommended next steps

1. **Read the dashboard.** The clickable view at `sop-dashboard.html` is the easiest way to internalize where {{firm_name}} stands. Send it to the partner group before discussing.
2. **Address the compliance floor first.** WISP, FTC Safeguards, §7216, and SSARS/SQMS gaps are not optional. Even if other gaps are more interesting, these are the legal hygiene.
3. **Run the per-gap interviews you deferred.** During this audit, {{n_deferred_interviews}} gap interviews were deferred. Schedule those as one-hour blocks with each named owner.
4. **Pick one Tier 1 AI candidate.** From the dashboard's automation candidates, choose one Tier 1 SOP (transaction categorization, bank reconciliation, document extraction, etc.) and pilot AI on it. Build the SOP first, AI second.
5. **Establish Domain 16.** If the firm uses any AI tools at all, the AI Usage Policy + Approved Tools List is the unblock for many other SOPs (engagement letter language, §7216 consent, onboarding disclosure).
6. **Schedule the next audit.** Re-run this skill in 6 months. Coverage percentage should climb at least 20 points if the roadmap is followed.

---

## Appendix A — Full inventory

{{full_inventory_table}}

## Appendix B — Caveats and limitations

- This audit reviewed the SOP files and verbal descriptions {{firm_name}} provided. Anything not surfaced during the engagement is outside scope.
- The 16-domain × 5-layer