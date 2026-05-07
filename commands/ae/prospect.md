---
description: Full prospect research package for a target company
allowed-tools: WebSearch, WebFetch, Read, Write, Bash
argument-hint: [company name]
---

Run full prospect research for: $ARGUMENTS

Load the prospect-research skill from `${CLAUDE_PLUGIN_ROOT}/skills/prospect-research/SKILL.md`.
Load the qualification-framework skill from `${CLAUDE_PLUGIN_ROOT}/skills/qualification-framework/SKILL.md`.
Load user settings from `${CLAUDE_PLUGIN_ROOT}/config/settings.md`.

Execute the following research modules in sequence:

**1. Company Intelligence Brief**
Search for current company overview: industry, HQ, employee count, revenue range, ownership structure, recent funding or M&A activity, key markets served.

**2. Fit Assessment**
Using the ICP definition and target verticals from settings.md, score this prospect:
- Vertical fit (which of your `TARGET_VERTICALS` applies, if any)
- Size and complexity fit (employee count, revenue range, scale indicators specific to your vertical)
- Technology maturity (current vendor footprint, modernization signals)
- Pain point alignment (map observable pain points to your solution's core value drivers)
- Overall fit rating: Strong / Moderate / Weak — with one-sentence rationale

**3. Leadership Contacts**
Identify 4–6 key contacts across the buyer-persona set from your vertical pack (typically a VP-level operational leader, a director-level functional owner, the IT/platform decision-maker, and a relevant C-suite executive). For each: name, title, LinkedIn URL if findable, relevant background note.

**4. Recent News & Signals**
Surface the last 90 days of news: earnings calls, expansions, layoffs, new contracts, technology investments, leadership changes, competitive moves. Flag any buying signals.

**5. Competitive Tech Landscape**
Identify known technology vendors in their current stack relevant to your solution category. Note any competitors already deployed. Identify displacement opportunities.

**6. Operations & Footprint**
Map the operational footprint that matters for your sale: physical locations, scale indicators, network or distribution model, and any public operational metrics. The exact data set varies by vertical.

**Qualification Pre-Check**
Run a preliminary qualification check using the three-gate framework from the qualification-framework skill. Flag any gates where data is absent or weak.

Output everything as a structured briefing document. Use clear section headers. Keep the fit assessment and news sections tightest — those are the most action-relevant.
