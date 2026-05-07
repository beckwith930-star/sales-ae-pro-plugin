---
description: Generate a quarterly business review deck outline and narrative
allowed-tools: Bash, Read, Write, WebSearch
argument-hint: "Q2 2026"
---

Generate a Quarterly Business Review for: $ARGUMENTS

Load the pipeline-hygiene skill from `${CLAUDE_PLUGIN_ROOT}/skills/pipeline-hygiene/SKILL.md`.
Load the presentation-coach skill from `${CLAUDE_PLUGIN_ROOT}/skills/presentation-coach/SKILL.md`.
Load the qualification-framework skill from `${CLAUDE_PLUGIN_ROOT}/skills/qualification-framework/SKILL.md`.
Load settings from `${CLAUDE_PLUGIN_ROOT}/config/settings.md`.

**Step 1 — Pull Quarter's Pipeline Data**
```bash
sf data query --query "SELECT Id, Name, AccountName, StageName, Amount, Probability, CloseDate, IsClosed, IsWon FROM Opportunity WHERE OwnerId IN (SELECT Id FROM User WHERE Name = '~~salesforce-owner') AND CloseDate = THIS_QUARTER ORDER BY IsWon DESC, Amount DESC" --target-org ~~salesforce-org
```

**Step 2 — QBR Deck Outline**
Generate a full QBR deck outline with slide-by-slide content guidance:

Slide 1 — Title: Quarter, your name, date
Slide 2 — Quarter Scorecard: quota, attainment, % to goal, key metrics vs. plan
Slide 3 — Wins: top 3 closed/won deals with one-sentence story each
Slide 4 — Pipeline Health: waterfall chart data, stage distribution, weighted forecast
Slide 5 — Deal Deep Dives (1–3 slides): top open deals with stage, qual status, path to close
Slide 6 — Competitive Landscape: notable competitive wins/losses, intel from the field
Slide 7 — Challenges & Learnings: what didn't work and what was learned (honest, specific)
Slide 8 — Next Quarter Plan: top targets, key initiatives, quota and timeline commitments
Slide 9 — Asks: specific support needed from leadership (exec intros, resources, approvals)

**Step 3 — Slide Content**
For each slide above, write the actual bullet-point content based on pulled data and user context. Keep each slide to 3–5 bullets max. No filler language.

**Step 4 — QBR Narrative**
Write a 2-paragraph executive summary of the quarter — the kind you'd open the QBR with verbally. Honest, direct, forward-looking.

**Step 5 — Presentation Quality Check**
Score the QBR outline against the Talk Like TED framework, with specific focus on:
- Principle 4 (novel insight — are you teaching them something, not just reporting?)
- Principle 7 (brevity — is each slide earning its place?)
- Principle 5 (memorable moments — is there one clear anchor slide?)

Flag any slides that are pure status reporting with no momentum or implication for the audience.
