---
description: Pipeline hygiene — stale deals, qual gaps, weighted forecast, action list
allowed-tools: Bash, Read, Write
argument-hint: (no arguments required)
---

Run a full pipeline hygiene check.

Load the pipeline-hygiene skill from `${CLAUDE_PLUGIN_ROOT}/skills/pipeline-hygiene/SKILL.md`.
Load the qualification-framework skill from `${CLAUDE_PLUGIN_ROOT}/skills/qualification-framework/SKILL.md`.
Load user settings from `${CLAUDE_PLUGIN_ROOT}/config/settings.md`.

**Step 1 — Pull All Open Opportunities**
```bash
sf data query --query "SELECT Id, Name, AccountName, StageName, Amount, Probability, CloseDate, LastActivityDate, NextStep, Description, LeadSource FROM Opportunity WHERE IsClosed = false AND OwnerId IN (SELECT Id FROM User WHERE Name = '~~salesforce-owner') ORDER BY CloseDate ASC" --target-org ~~salesforce-org
```

If Salesforce is unavailable, ask the user to paste their open pipeline as text and proceed.

**Step 2 — Flag Stale Deals**
Identify all opportunities where LastActivityDate is 7 or more days ago. For each stale deal:
- Deal name, stage, amount, days since last activity
- Recommended action (re-engage, reassess, or move to closed-lost)

**Step 3 — Qualification Gap Analysis**
For each open opportunity, assess qualification gate status using the three-gate framework. Use NextStep, Description, and Stage as proxies where direct gate data is absent.

For each deal, output:
| Deal | Stage | Gate 1 | Gate 2 | Gate 3 | Biggest Gap |

Flag any deal missing two or more gates as "At Risk."

**Step 4 — Weighted Pipeline Value**
Calculate:
- Total pipeline (sum of Amount)
- Weighted pipeline (Amount × Probability for each deal, summed)
- Breakdown by stage
- Gap to quota (ask user for current quota if not in settings)

**Step 5 — Prioritized Action List**
Generate a ranked action list of the top 5–8 deals requiring immediate attention. For each:
- Deal name and why it's prioritized
- Specific action recommended
- Suggested deadline

Sort by: (1) close date proximity, (2) deal size, (3) number of red qualification gates.

Output the full hygiene report in a clean table + narrative format. Make it ready to share in a 1:1.
