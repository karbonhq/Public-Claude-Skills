# sop-library-auditor

A Claude skill that audits an accounting/bookkeeping/CAS firm's existing SOP library, scores it against the AI-Ready SOP Framework (16 domains × 5 layers), and conducts interviews to fill the gaps.

## What it does

Given a firm's existing SOPs (in any state — outdated, scattered, partial, or just verbal), the skill:

1. Runs a 12-question intake interview to understand the firm's shape, service mix, tech stack, and goals.
2. Reads the firm's existing SOPs from a folder, individual uploads, or verbal description.
3. Classifies each SOP into one of 16 domains organized across 5 operating layers (Value chain / Production / Quality / Enablement / Governance).
4. Scores each existing SOP across the 15-field anatomy (present / partial / missing per field) and gives every domain a 3-state coverage status (Complete / Partial / Missing / N/A). A 5-axis maturity score (Existence, Currency, Coverage, AI-readiness, Adoption) is computed as a secondary diagnostic accessible per-SOP via the dashboard.
5. Renders an interactive HTML coverage report — clickable 16-domain heatmap, per-SOP anatomy grid, prioritized gap table with 30/60/90/180-day filter pills, and a 5-axis radar drill-down per SOP.
6. Reorganizes the existing library into a clean folder structure mirroring the 5 layers and 16 domains (originals preserved).
7. Conducts per-gap interviews to capture the firm's actual procedure into the 15-field anatomy template — never speculating, never auto-drafting.
8. Produces a written gap report with a prioritized 30/60/90/180-day roadmap.

## Folder structure

```
sop-library-auditor/
├── SKILL.md                         # Main skill instructions for Claude
├── README.md                        # This file
├── references/
│   ├── framework.md                 # Domain A–J taxonomy
│   ├── intake-interview.md          # 12 firm-profile questions
│   ├── scoring-rubric.md            # 5-axis scoring + prioritization formula
│   ├── sop-template.md              # 14-section SOP template
│   ├── ai-readiness.md              # AI-eligibility tagging
│   ├── size-tier-expected-sets.md   # Expected SOPs per firm size
│   ├── sop-interview-bank.md        # Per-domain interview question banks
│   └── compliance-quickref.md       # WISP, FTC Safeguards, SSARS, SQMS
├── assets/
│   ├── dashboard.html               # Self-contained HTML dashboard template
│   └── gap-report-template.md       # Markdown gap report template
└── scripts/
    └── parse_sops.py                # Walks a folder, extracts text from .md/.docx/.pdf/.txt
```

## How a firm uses it

In a Claude session, the firm says any of:

- "Audit our SOPs"
- "Our procedures are a mess and out of date — help us fix them"
- "We have a folder of SOPs but no idea what's missing"
- "Score our SOP maturity and tell us what to document next"

Claude triggers this skill, runs the 7 stages, and produces four artifacts in the firm's working folder:

- `sop-dashboard.html` — interactive coverage report
- `sop-gap-report.md` — written report (or `.docx` on request)
- `SOP-Library/` — reorganized library, with the firm's existing SOPs filed and renamed under the 16-domain taxonomy
- `interview-captures/` — new SOPs captured from per-gap interviews

## Installing the skill

Place the `sop-library-auditor/` folder in any location Claude can read. Two common patterns:

1. **Per-firm install:** drop it into the firm's working folder. Claude reads it automatically when triggered.
2. **Shared install:** drop it into a skills directory the user has set up (e.g., `~/.claude/skills/`). Available across all sessions for that user.

The skill is fully self-contained. Claude does not need internet access to run it; the dashboard's only external dependency is Chart.js loaded from a CDN at view time (firms can swap to a local copy if their security posture requires it).

## Dependencies

The `parse_sops.py` script optionally uses:

- `python-docx` — for `.docx` extraction (`pip install python-docx`)
- `pypdf` — for `.pdf` extraction (`pip install pypdf`)

The script gracefully skips formats whose libraries aren't installed and notes the skip in the output JSON. Markdown and plain text always work.

## What the skill won't do

- It won't write speculative SOP content. Every captured SOP is built from the firm's actual interview answers; sections without interview content are flagged `[NEEDS INPUT]` so the firm sees exactly what's still tribal knowledge.
- It won't render compliance opinions. The skill flags whether documentation exists; the firm's CPA and legal counsel make compliance determinations.
- It won't move or destroy original SOP files. Originals are preserved; reorganization is by copy.

## Source framework

Built on the AI-Ready SOP Framework, which synthesizes:

- CPA.com CAS 2.0 framework and AICPA PCPS benchmarks
- Karbon, Aero, Jetpack Workflow, and Future Firm template libraries
- AICPA SSARS 21–25 and SQMS No. 1
- IRS Pub 4557 (Safeguarding Taxpayer Data) and IRS Pub 57