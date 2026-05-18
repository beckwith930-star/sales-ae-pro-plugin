# Sales AE Pro

Enterprise AE toolkit for B2B technology sales. Covers the full deal cycle: prospect research, call prep, post-meeting processing, pipeline hygiene, outreach generation, business case building, and presentation coaching.

Designed for Account Executives selling complex B2B solutions into enterprise accounts. Vertical-agnostic by design — example research and outreach packs ship for SaaS, fintech, healthcare, and industrial. Configure your specific vertical, ICP, products, and competitors in `config/settings.md`.

A three-gate qualification framework is embedded across all deal workflows. The framework is methodology-agnostic and maps cleanly to MEDDIC, MEDDPICC, BANT, or Challenger.

> **Want this installed and tuned for your team instead of doing it yourself?** See [qualifyr.io](https://qualifyr.io) for concierge packages — $1,500 Starter / $3,500 Growth / $7,500 Enterprise.

---

## Slash Commands

| Command | Usage | Description |
|---------|-------|-------------|
| `/ae:prospect` | `/ae:prospect [company name]` | Full prospect research: company brief, ICP fit assessment, leadership contacts, recent news and buying signals, competitive landscape, operations footprint |
| `/ae:call-prep` | `/ae:call-prep [company] [contact] [meeting type]` | Pre-call package: CRM context brief, discovery questions mapped to qualification gates, opening talk track with pivots, anticipated objections with responses |
| `/ae:post-meeting` | `/ae:post-meeting` then paste notes | Processes meeting notes into four deliverables: Salesforce activity note, internal leadership briefing, follow-up email draft, qualification checklist update |
| `/ae:pipeline` | `/ae:pipeline` | Pipeline hygiene check: stale deal flags, qualification gap matrix, weighted pipeline calculation, prioritized action list |
| `/ae:outreach` | `/ae:outreach [company name]` | Full outreach package: cold email, LinkedIn connection request + follow-up, phone talk track with voicemail, 3-week multi-channel cadence plan |
| `/ae:deck-review` | `/ae:deck-review` then attach deck | Scores a presentation against the Talk Like TED 9-principle framework, identifies weak slides, provides specific improvement recommendations |
| `/ae:business-case` | `/ae:business-case [company name]` | Internal business case built from public data: executive summary, pain mapping with evidence, opportunity sizing, pilot-to-enterprise playbook |
| `/ae:weekly` | `/ae:weekly` | Weekly pipeline review and 1:1 prep document: pipeline snapshot, top deal deep dives, manager talking points, weekly action plan |
| `/ae:qbr` | `/ae:qbr [quarter]` | Full QBR deck outline with slide-by-slide content, executive narrative, and Talk Like TED quality scoring |

---

## Skills

All skills are loaded automatically by the commands above. They can also be triggered conversationally:

- **prospect-research** — company intelligence, ICP fit assessment, leadership mapping
- **discovery-call-prep** — discovery questions, talk tracks, objection handling
- **post-meeting-processing** — CRM notes, briefings, follow-up emails
- **pipeline-hygiene** — staleness analysis, qualification gap scoring, pipeline math
- **outreach-generation** — cold email, LinkedIn, phone, cadence planning
- **business-case-builder** — financial impact sizing, opportunity modeling, pilot playbook
- **presentation-coach** — Talk Like TED framework scoring and slide-level feedback
- **qualification-framework** — three-gate framework, embedded in all deal commands

---

## Installation

```bash
claude plugin marketplace add beckwith930-star/sales-ae-pro-plugin
```

---

## Setup

### Required: Salesforce CLI

All pipeline and CRM commands use the `sf` CLI.

```bash
# Install
npm install -g @salesforce/cli

# Authenticate
sf org login web --alias my-org

# Verify
sf org list
```

Then update `config/settings.md`:
- `SALESFORCE_OWNER_NAME`: Your full name exactly as it appears in Salesforce
- `SALESFORCE_ORG_ALIAS`: Your `sf` org alias (from `sf org list`)

### Optional: Email, Slack, Google Drive

MCP connectors for Gmail, Slack, and Google Drive are pre-configured in `.mcp.json`. Each will prompt for OAuth on first use. Remove any you don't need.

See `CONNECTORS.md` for setup details.

---

## Customization Guide

After installing, open `config/settings.md` and configure it for your company. The more detail you provide, the more personalized every output will be.

### Day-One Configuration

1. **Company & Products** — Set `COMPANY_NAME`, `COMPANY_TAGLINE`, and add your product descriptions with key outcomes. Each product entry includes a name, description, primary vertical, and 2-3 measurable outcomes.

2. **Salesforce Credentials** — Set `SALESFORCE_OWNER_NAME` (must match your Salesforce name exactly) and `SALESFORCE_ORG_ALIAS` (your `sf` CLI alias). Set `QUOTA_CURRENT_PERIOD` and `QUOTA_PERIOD` for pipeline coverage calculations.

3. **ICP Definitions** — Define your Ideal Customer Profile for each target vertical. The bundled examples cover SaaS, fintech, healthcare, and industrial — pick the closest, copy the structure, and edit the values to match your actual ICP. The framework supports any vertical.

4. **Competitor List** — Add your primary competitors with displacement notes. These are used in prospect research, call prep, and business cases to tailor competitive positioning.

5. **Customer References** — Add anonymized customer references with outcomes. Set `approved_for_external: true` only for customers who have approved named references. Use neutral size/segment descriptors for unapproved references.

### Qualification Framework

The plugin uses a three-gate qualification framework embedded across all deal commands:

- **Gate 1 — Value**: Pain confirmed, revenue sized, urgency identified
- **Gate 2 — Path to Scale**: Champion named, buyer identified, process mapped, budget confirmed
- **Gate 3 — Use Case Fit**: Workflow documented, integrations identified, success metrics agreed

Customize gate criteria, thresholds, and blocking rules in `config/settings.md` to match your org's methodology (MEDDIC, BANT, MEDDPICC, Challenger, etc.). See `skills/qualification-framework/references/three-gates.md` for alignment mappings.

### Pipeline Settings

Adjust `STAGE_PROBABILITIES` to match your org's actual win rates by stage. Set `STALE_DEAL_THRESHOLD_DAYS` (default: 7) and `PIPELINE_COVERAGE_TARGET` (default: 3.5x) to match your team's standards.

### Outreach & Cadence

The outreach skill includes email, LinkedIn, and phone templates organized by persona. Customize the templates in `skills/outreach-generation/references/cadence-templates.md` to match your voice, value props, and customer proof points.

---

## Qualification Framework

Every deal command checks three qualification gates and flags gaps:

**Gate 1 — Value**: Is the opportunity worth pursuing? (pain confirmed, revenue sized, urgency identified)

**Gate 2 — Path to Scale**: Do we know who buys and how? (champion named, buyer identified, process mapped, budget confirmed)

**Gate 3 — Use Case Fit**: Does the solution fit the environment? (workflow documented, integrations identified, success metrics agreed)

Gates are assessed as Green / Yellow / Red. Each Red gate generates a specific recommended action.

Blocking rules:
- Gate 1 Red: do not advance to Proposal
- Gate 2 Red: do not submit for discount or approval
- Gate 3 Yellow or below: do not provide pricing

---

## Project Structure

```
sales-ae-pro-plugin/
├── .claude-plugin/
│   └── plugin.json          # Plugin manifest
├── marketplace.json          # Marketplace metadata
├── .mcp.json                 # MCP server configurations
├── config/
│   └── settings.md           # User-configurable settings
├── commands/
│   └── ae/
│       ├── prospect.md       # /ae:prospect
│       ├── call-prep.md      # /ae:call-prep
│       ├── post-meeting.md   # /ae:post-meeting
│       ├── pipeline.md       # /ae:pipeline
│       ├── outreach.md       # /ae:outreach
│       ├── deck-review.md    # /ae:deck-review
│       ├── business-case.md  # /ae:business-case
│       ├── weekly.md         # /ae:weekly
│       └── qbr.md            # /ae:qbr
├── skills/
│   ├── prospect-research/
│   ├── discovery-call-prep/
│   ├── post-meeting-processing/
│   ├── pipeline-hygiene/
│   ├── outreach-generation/
│   ├── business-case-builder/
│   ├── presentation-coach/
│   └── qualification-framework/
├── CONNECTORS.md             # Integration setup guide
├── LICENSE                   # MIT
└── README.md
```

---

## License

MIT — see [LICENSE](./LICENSE).
