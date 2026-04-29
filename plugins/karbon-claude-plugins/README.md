# Karbon Claude Plugins

A curated set of Claude skills built by Karbon for accounting firms.

## What's inside
This plugin is a growing collection of focused, reusable skills for the work accounting firms actually do — AI strategy, SOPs, advisory prep, marketing, and more. Skills are added as Karbon builds and validates them.

## Installation
This plugin is distributed through the Karbon marketplace. To install:

```
/plugin marketplace add karbonhq/public-claude-skills
/plugin install karbon-claude-plugins@karbon-claude-plugins
```

## Skills
- **`firm-ai-strategy`** — Conducts a structured advisor-style interview with an accounting firm owner or partner and produces a written, defensible AI strategy document (`.docx`). Triggers on prompts like "build our AI strategy", "draft an AI policy", or "where do we start with AI".
- **`sop-library-auditor`** — Audits, organizes, scores, and fills gaps in an accounting/bookkeeping/CAS firm's existing SOP library. Produces an interactive HTML coverage report with a 16-domain heatmap, a written gap report, a reorganized library folder, and interview-driven captures for missing SOPs. Triggers on prompts like "audit our SOPs", "review our procedures", "find SOP gaps", "score our SOP coverage", or when a firm hands over an existing folder of SOPs.
- **`payroll-journal-entry-skill-builder`** — A meta-skill that builds a reusable, client-specific payroll journal entry skill from a real payroll register. Asks a short set of allocation questions, validates the math, and produces a `SKILL.md` any team member (or Claude) can use next pay period to book the JE consistently. Triggers on prompts like "create a payroll JE skill for [client]", "codify how we book [client]'s payroll", or "build a payroll journal entry skill".

## How skills work
Each skill lives in its own folder under `skills/` with a `SKILL.md` file. Claude loads the skill automatically when your prompt matches its description. Skills inside this plugin are namespaced as `/karbon-claude-plugins:skill-name`.

## License
MIT — see the repository LICENSE file.

## Contact
byron.patrick@karbonhq.com
