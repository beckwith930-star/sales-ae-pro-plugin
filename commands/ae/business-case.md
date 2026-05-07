---
description: Build an internal expansion business case from public company data
allowed-tools: WebSearch, WebFetch, Read, Write, Bash
argument-hint: [company name]
---

Build a full expansion business case for: $ARGUMENTS

Load the business-case-builder skill from `${CLAUDE_PLUGIN_ROOT}/skills/business-case-builder/SKILL.md`.
Load the qualification-framework skill from `${CLAUDE_PLUGIN_ROOT}/skills/qualification-framework/SKILL.md`.
Load user settings from `${CLAUDE_PLUGIN_ROOT}/config/settings.md`.

**Step 1 — Source Public Data**
Search for and retrieve:
- Most recent 10-K or annual report (or equivalent public filing)
- Most recent earnings call transcript or investor presentation
- Any publicly disclosed operational metrics relevant to your sale (varies by vertical — see `skills/prospect-research/references/vertical-frameworks.md` for the metrics that matter per industry)
- Analyst coverage or industry benchmarks for their sector

**Step 2 — Executive Summary**
One paragraph. State the opportunity, the scale, and the core recommendation. Written for a VP or CRO reading in 30 seconds.

**Step 3 — Pain Point Mapping**
Identify 3–5 operational pain points evidenced in public filings or earnings commentary. For each pain point:
- The pain (with a direct quote or data point from source)
- How your solution addresses it
- Estimated impact range (time savings, cost reduction, error rate, throughput gain)

**Step 4 — Solution Fit**
Map your product capabilities (from settings.md) to their stated priorities. Identify the primary use case, secondary use cases, and any gaps or dependencies.

**Step 5 — Opportunity Sizing**
Build a bottom-up opportunity estimate from public scale indicators (sites, seats, accounts, transactions, or whatever unit drives ARR in your sale):
- Total addressable units
- Addressable units that fit your ICP (filter by size, complexity, geography)
- ARR per unit (use ranges: conservative / base / optimistic)
- Total ARR range: addressable units × ARR per unit
- Phased expansion path: pilot → expansion → full deployment

**Step 6 — Competitive Urgency**
Identify any competitors already operating in their space or with known vendor relationships. Articulate why delay has a cost — market window, competitor entrenchment, operational risk.

**Step 7 — Pilot-to-Enterprise Playbook**
Outline a realistic path from pilot to full deployment:
- Pilot scope (1–2 sites, defined success metrics)
- Expansion trigger criteria
- Timeline milestones
- Key dependencies (IT, ops, procurement)

**Step 8 — Qualification Gate Mapping**
Map the business case findings to the three qualification gates. Flag any gate that remains unconfirmed and note what internal data (from a discovery call) would close it.

**Step 9 — Leadership Asks**
List 2–3 specific asks from your leadership team to advance this opportunity: resources needed, executive sponsorship, reference customer introductions, etc.

Output as a clean internal document, structured for a deal review or QBR presentation.
