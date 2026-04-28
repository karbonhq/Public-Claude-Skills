# Karbon Claude Plugins

A curated set of Claude skills built by Karbon for accounting firms.

## What's inside
This plugin is a growing collection of focused, reusable skills for the work accounting firms actually do — AI strategy, SOPs, advisory prep, marketing, and more. Skills are added as Karbon builds and validates them.

## Installation
This plugin is distributed through the Karbon marketplace. To install:

```
/plugin marketplace add karbonhq/public-claude-skills
/plugin install karbon-plugins@karbon-plugins
```

## Skills
- **`firm-ai-strategy`** — Conducts a structured advisor-style interview with an accounting firm owner or partner and produces a written, defensible AI strategy document (`.docx`). Triggers on prompts like "build our AI strategy", "draft an AI policy", or "where do we start with AI".
- **`sop-architect`** — Reviews, organizes, and fills gaps in an accounting/bookkeeping/CAS firm's standard operating procedures. Builds an SOP inventory across 16 domains, identifies gaps, prioritizes what to document next, and writes new SOPs through a guided interview. Triggers on prompts like "review my SOPs", "audit our SOPs", "find gaps in my SOPs", or "interview me to write an SOP".

## How skills work
Each skill lives in its own folder under `skills/` with a `SKILL.md` file. Claude loads the skill automatically when your prompt matches its description. Skills inside this plugin are namespaced as `/karbon-plugins:skill-name`.

## License
MIT — see the repository LICENSE file.

## Contact
byron.patrick@karbonhq.com
