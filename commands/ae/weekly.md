---
description: Weekly pipeline review + 1:1 prep document
allowed-tools: Bash, Read, Write, WebSearch
argument-hint: (no arguments required — optionally add notes for the week)
---

Generate this week's pipeline review and 1:1 prep document.

Additional context from user (if any): $ARGUMENTS

Load the pipeline-hygiene skill from `${CLAUDE_PLUGIN_ROOT}/skills/pipeline-hygiene/SKILL.md`.
Load the qualification-framework skill from `${CLAUDE_PLUGIN_ROOT}/skills/qualification-framework/SKILL.md`.
Load settings from `${CLAUDE_PLUGIN_ROOT}/config/settings.md`.

**Step 1 — Pull Current Pipeline**
```bash
sf data query --query "SELECT Id, Name, AccountName, StageName, Amount, Probability, CloseDate, LastActivityDate, NextStep FROM Opportunity WHERE IsClosed = false AND OwnerId IN (SELECT Id FROM User WHERE Name = '~~salesforce-owner') ORDER BY CloseDate ASC" --target-org ~~salesforce-org
```

**Step 2 — Week-over-Week Pipeline Summary**
Produce a concise pipeline snapshot:
- Total pipeline value (weighted and unweighted)
- Deals by stage
- Deals advancing this week vs. stalled
- New opportunities added
- Any deals slipped or lost

**Step 3 — Top 3 Deals Deep Dive**
For the three highest-priority deals (by close date × deal size × qualification completeness):
- Account, stage, amount, close date
- Qualification gate status (R/Y/G per gate)
- What happened this week
- Next action with owner and date
- Risk factors

**Step 4 — 1:1 Prep**
Structure talking points for a manager 1:1:
- Wins and momentum this week (be specific)
- Blockers requiring manager support
- Deals needing executive attention or escalation
- Asks: introductions, approvals, resources
- Personal development note (optional — remove if not relevant)

**Step 5 — This Week's Action Plan**
Top 5 highest-leverage actions for the coming week, ranked by impact. Each action: account name, specific action, why it's the priority.

Format the full output as a document you can drop directly into a 1:1 or team meeting.
