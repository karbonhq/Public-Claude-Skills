# Accounting compliance frame — what the strategy must address

The strategy document must address six accounting-specific risk vectors that don't appear in generic enterprise AI frameworks. Read this file before any Stage 5 question. Every rule below should be explainable to a non-technical firm owner in one plain-English sentence before the question is asked.

## The six risk vectors

### 1. IRS §7216 — tax return information disclosure

**What it is:** §7216 makes it a misdemeanor for a tax return preparer to disclose tax return information for any non-return-prep purpose without consent. The definition of "tax return information" is extremely broad — it includes anything the preparer received in connection with preparing the return, not just the return itself.

**Penalty:** up to $1,000 fine per violation, up to $100,000 if linked to identity theft, plus up to 1 year imprisonment.

**Why it matters for AI:** pasting any client tax data — a 1099, a W-2, a K-1, an income figure, a Social Security Number, even an income-related question framed with client specifics — into a free or personal-tier ChatGPT, Claude, Gemini, or Copilot is potentially a §7216 violation. Consumer tiers train on user prompts by default. That's the disclosure.

**What the strategy must do:** name a sanctioned-tool list. Anything not on the list is banned for client data. Get §7216 consent language in engagement letters before using AI vendors that store or process tax return information. Confirm vendor SOC 2 / training-data terms before approval.

**Plain-English version for the interview:** "If a staff member pastes a client's W-2 into the free version of ChatGPT, that's potentially a federal misdemeanor. The free tiers train on what you type. So part of the strategy is making sure that doesn't happen — and the way you do that is by naming the tools your team is allowed to use, and the ones they aren't."

### 2. FTC Safeguards Rule (GLBA) — the Written Information Security Plan

**What it is:** every tax preparer is required by the FTC Safeguards Rule (an extension of GLBA) to maintain a Written Information Security Plan (WISP), designate a Qualified Individual to oversee it, encrypt client data at rest and in transit, enforce multi-factor authentication, oversee third-party vendors, and report breaches affecting ≥500 consumers to the FTC within 30 days.

**As of the 2026 PTIN renewal:** the IRS now requires preparers to attest they have an active WISP.

**Why it matters for AI:** every AI vendor is a third-party data processor. The WISP must include the AI vendor inventory, the data-handling terms, the breach-response plan, and the encryption posture for AI-routed data. Shadow AI tools sit outside the WISP entirely — that's the breach.

**What the strategy must do:** include a vendor-vetting checklist (SOC 2 Type 2, encryption posture, training-data terms, data residency, sub-processors). Update the WISP to reflect AI vendors. Build incident response steps for AI-specific incidents (hallucinations on deliverables, prompt-injection, data exfiltration via Lab tools).

### 3. AICPA Code of Professional Conduct + revised SSTS (effective Jan 1, 2024)

**What it is:** Rule 1.700 (confidentiality), Article V (due care), and Article III (integrity) all apply to AI use. The revised Statements on Standards for Tax Services (SSTS), effective January 1, 2024, now explicitly define "tools" to include "artificial intelligence." This means tax practitioners must "engage, supervise, train, and evaluate" AI tools as if they were staff.

**Why it matters for AI:** hallucinations are not a vendor problem — they are a due-care problem. The Deloitte Australia 2025 incident (refund issued for a government report containing AI-fabricated citations) is the canonical case study. Any tax memo, client deliverable, or workpaper drafted with AI assistance and not verified by a competent reviewer is a potential SSTS / due-care issue.

**What the strategy must do:** define the human-in-the-loop pattern. Name the reviewer for each AI-assisted deliverable type. Define the workpaper retention standard for AI-touched work (what was the prompt, what model, what output, what changed in review). Train staff on the difference between "AI assists me" and "AI replaces me."

### 4. Circular 230 (§§10.22, 10.33, 10.35, 10.37)

**What it is:** Circular 230 governs practice before the IRS. §10.22 (diligence), §10.33 (best practices), §10.35 (competence), §10.37 (written advice standards) all apply to AI-assisted tax practice. Practitioners are responsible for the work product even when AI generated it.

**What the strategy must do:** affirmatively state that AI-generated tax advice and written advice undergoes preparer review before delivery to client, and that the preparer signing the return remains accountable for everything in it.

### 5. Independence under ET 1.295

**What it is:** ET 1.295 creates a self-review threat when an AI tool generates content (e.g., a workpaper, an analysis, a memo) that the auditor then audits.

**Why it matters for AI:** as agentic audit tools mature (AICPA DAS, MindBridge, Fieldguide, Caseware AI, Auditoria.AI), the boundary between "AI helped me audit" and "AI did the audit and I reviewed it" becomes the independence question.

**What the strategy must do (audit firms):** for any client where the firm provides both an attest service and an AI tool that produces content the firm subsequently audits, document the safeguards. Treat Lab-tool use in audit engagements with extra caution. Sequence AI rollout in audit around AICPA DAS and peer-review readiness.

### 6. Professional liability — CAMICO, AON, AICPA member program

**What it is:** professional liability insurers (CAMICO, AON administering the AICPA member program) now distinguish between AI used under supervision (lower exposure) and autonomous AI advice (heightened controls required). Several insurers have begun adding AI questions on renewal applications.

**Why it matters for AI:** an undisclosed AI-driven incident may impair coverage. Engagement-letter language disclosing AI use is now best practice.

**What the strategy must do:** include a 30-day task to (a) review the firm's E&O coverage for AI exposure language, (b) update engagement letters to include AI disclosure language, and (c) reach out to the carrier with a one-paragraph summary of AI policies and tooling.

## Bonus context — state board and CPE

No state board has issued binding AI-specific regulations as of April 2026, but Virginia, Texas, and several other states have approved AI-ethics CPE. If the firm is in a regulated state, flag the CPE opportunity and add a roadmap line for staff CPE on AI ethics.

## Anti-pattern: the seven mistakes accounting firms actually make

Synthesizing CAMICO, Karbon, Inside Public Accounting, Netgain, Jason Staats, BlackFog, KPMG, IBM. The strategy must design *against* each of these — not for any of them.

1. **Shadow AI** — 49% of workers use AI without employer approval; 1 in 5 organizations had a shadow-AI breach in IBM's 2025 cost-of-breach data, adding ~$670K per incident. In an accounting firm this is direct regulatory exposure, not an HR irritant.
2. **Policy without practice** — Netgain calls it the assumption that "access equals progress."
3. **Tool collector syndrome** — subscribing to many products, deploying none.
4. **The two-camps split** — early adopters race ahead while skeptics dig in, fragmenting workflows along generational and role lines.
5. **Partner buy-in failure** — only 47% of senior leaders are comfortable using AI (ICAEW).
6. **Inputting client data into consumer AI tiers** — simultaneously breaches §7216, GLBA, and AICPA confidentiality.
7. **Hallucination / quality failures** — Deloitte Australia 2025 is the cautionary tale; applies to any tax memo or audit workpaper drafted by AI without verification.

## What to put in the strategy's governance section

For SHORT path: a one-page interim policy (use `assets/policy-template.md`) with the sanctioned-tool list, the red lines, and the §7216 / GLBA / AICPA confidentiality reminder.

For DEEP path: a full governance section with:

- Written AI policy (or pointer to existing one)
- Sanctioned-tool list with rationale per tool
- Vendor-vetting process (SOC 2, training-data terms, sub-processors)
- Engagement-letter language (sample clause)
- §7216 / GLBA / SSTS / Circular 230 / independence treatment
- Workpaper standards for AI-assisted work (prompt log, model, reviewer)
- Incident response plan (what happens when AI gets something wrong on a client deliverable)
- E&O carrier conversation (what was disclosed, when, with what response)

When in doubt, err on the side of more governance for tax-heavy and audit-heavy firms, less for bookkeeping/CAS-heavy firms (but never zero).
