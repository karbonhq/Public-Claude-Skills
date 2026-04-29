# Compliance Quick Reference

Use this when populating Section 12 of any captured SOP and when writing the Compliance section of the gap report. **Don't make claims the framework doesn't support.** The skill flags whether the firm has the documented controls; it does not opine on whether they would pass an audit.

## IRS Publication 4557 — Safeguarding Taxpayer Data

- **Who must comply:** Anyone with a PTIN. Effectively every tax preparer in the US.
- **What's required:** A written information security plan (WISP), the "Security Six" controls, MFA, encryption, employee training, vendor management.
- **The Security Six:** anti-virus, firewall, two-factor authentication, backup, drive encryption, VPN.
- **Maps to SOPs:** 15.1 (WISP), 15.3 (MFA), 15.4 (Encryption), 15.5 (Incident response), 15.6 (Vendor security), 13.5 (Training).
- **Penalties:** Civil and criminal. IRS Stakeholder Liaison expects 24–48 hour breach notification.

## IRS Publication 5708 — WISP Template

- **Provides** a fill-in-the-blank WISP template the IRS expects firms to complete.
- **Maps to SOPs:** 15.1.
- **The skill should** check whether the firm's WISP exists AND was actually customized (not just a template with `{firm name}` left in). A firm that says "we have a WISP" but can't produce a customized PDF gets axis 3 (Coverage) = 0.

## FTC Safeguards Rule — 16 CFR §314

- **Who must comply:** Any firm with PII for 11+ federal returns OR ~5,000 PII records. Most accounting firms.
- **What's required:**
  - Named program coordinator (an actual person, not "the firm")
  - Documented risk assessment
  - Tested incident response plan
  - Encryption of customer information
  - MFA for all access to systems with customer information
  - Employee training program
  - Vendor oversight
  - Annual report to the board (or owner)
- **Maps to SOPs:** 15.2 (FTC Safeguards program), 15.5 (incident response), 15.6 (vendor mgmt).
- **Penalties:** Up to **$50,120 per violation per day**.
- **Compliance date:** Effective June 9, 2023; major firms long past the grace period.

## SOC 2 (Trust Services Criteria)

- **Who needs it:** Firms whose clients require it (especially venture-backed CAS clients). Optional but increasingly common at Tier 3+.
- **Five criteria:** Security (required), Availability, Processing Integrity, Confidentiality, Privacy.
- **Maps to SOPs:** Most of Domain 15, plus 12.4 (data-flow controls), 13.5 (training), 14.3 (backup/DR).
- **Cost:** Type II audit typically $30K–$80K, plus 6+ months of evidence collection. Don't recommend this lightly to small firms.

## AICPA SSARS Nos. 21–25

- **Governs:** Preparation, compilation, and review engagements (not audits).
- **Documentation requirements:** Engagement letters, management representations, knowledge of the entity, performance procedures, reporting language.
- **Maps to SOPs:** 7.2 (SSARS-compliant compilation/preparation), 1.3 (engagement letter), 10.8 (SQMS documentation).
- **The skill should** flag every monthly-close SOP that doesn't reference its SSARS framework as having a Coverage gap.

## AICPA SQMS No. 1 — Quality Management

- **Replaces** SQCS No. 8.
- **Effective:** December 15, 2025 (current as of skill creation date).
- **Required for:** Firms performing engagements under SSARS or audits.
- **Eight components:** Governance and leadership; relevant ethical requirements; acceptance and continuance; engagement performance; resources; information and communication; monitoring and remediation; risk assessment.
- **Maps to SOPs:** Domain 10 (QC & Review) — full set, especially 10.4–10.8.
- **The skill should** flag any firm at Tier 3+ doing SSARS work without a populated Domain 10 set as having a high-priority SQMS gap.

## State Privacy Regimes (often referenced in WISP)

- **NY SHIELD Act** — Reasonable safeguards for NY residents' private information.
- **CA CCPA / CPRA** — Consumer rights and business obligations for CA residents.
- **MA 201 CMR 17.00** — Comprehensive WISP requirements; pre-dates and exceeds federal in some areas.
- **CO Privacy Act, VA CDPA, CT Data Privacy Act, UT Consumer Privacy Act** — emerging state regimes; consult counsel.

The skill should not opine on multi-state privacy compliance — flag it as "consult counsel" in the gap report.

## Compliance flags in the gap report

When generating the gap report's Compliance section, list every regime above and the firm's documented status against it (from intake Q5 plus the inventory). Use this format:

```markdown
## Compliance Posture

| Regime | Required? | Documented? | Gap |
|---|---|---|---|
| IRS Pub 4557 (WISP) | Yes (any PTIN) | No | 15.1 — high priority |
| FTC Safeguards Rule | Likely yes (>11 returns) | No | 15.2 — high priority, civil penalty exposure |
| AICPA SSARS 21–25 | Yes (preparation engagements) | Partial | 7.2 — engagement letter language not standardized |
| AICPA SQMS No. 1 | Yes (firm performs SSARS) | No | A4 (full set) — high priority |
| SOC 2 | Client-dependent | N/A | None of the firm's clients currently require |
| State privacy | Multi-state — consult counsel | N/A | Recommend legal review |
```

The skill should never write "Compliant" in the "Documented?" column based only on the firm's self-report. Either the firm produces evidence (a customized WISP file, a named coordinator), or the documented column says "No" or "Partial."

## §7216 — Disclosure & Use of Tax Return Information

- **Who must comply:** Any tax-return preparer, including bookkeepers/CAS firms whose work feeds tax returns.
- **What's required:** 