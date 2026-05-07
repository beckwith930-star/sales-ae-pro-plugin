---
name: prospect-research
description: >
  This skill should be used when the user asks to "research a company", "get intel on a prospect",
  "run prospect research", "tell me about [company]", "build a company brief", or wants to understand
  a target account's fit, leadership, news, competitive landscape, or operations footprint.
  Also triggers when the user runs /ae:prospect or asks for an ICP fit assessment.
version: 0.1.0
---

# Prospect Research

Produce a structured, multi-section intelligence brief on a target company. Adapt the depth of each module to the vertical configured in `config/settings.md` — different verticals weight different evidence (operational metrics for industrial, regulatory and trial data for healthcare, growth and stack signals for SaaS, etc.).

## Core Research Modules

### 1. Company Intelligence Brief
Retrieve: legal name, HQ location, employee count, revenue range (public or estimated), ownership structure (public/private/PE-backed), key markets served, and any recent M&A, funding, or restructuring activity.

Use public sources: company website, LinkedIn, Crunchbase, SEC EDGAR (if public), trade press.

### 2. ICP Fit Assessment
Load ICP definitions and target verticals from `${CLAUDE_PLUGIN_ROOT}/config/settings.md`.

Score fit across four dimensions:
- **Vertical fit**: Does this company operate in one of your `TARGET_VERTICALS`? Which one?
- **Size/complexity fit**: Use the size and complexity criteria from your ICP definition (employee count, revenue range, scale indicators relevant to your vertical)
- **Technology maturity**: Use the tech-stack signals from your vertical pack — current vendor footprint, modernization signals, identifiable displacement opportunities
- **Pain point alignment**: Map observable pain points (from earnings, news, job postings) to your solution's core value propositions

Assign an overall fit rating: **Strong / Moderate / Weak** — one sentence justification.

### 3. Leadership Contact Mapping
Identify 4–6 contacts across the buyer-persona set defined in your vertical pack (typically: a VP-level operational leader, a director-level functional owner, the IT/platform decision-maker, the relevant C-suite executive, and the economic buyer). Reference `references/vertical-frameworks.md` for the typical persona set per vertical.

For each: full name, title, estimated tenure, prior roles (if notable), LinkedIn URL, and a one-line note on why they're relevant to your sale.

### 4. Recent News & Buying Signals
Surface the last 90 days. Prioritize the ICP signals listed in your vertical pack — these vary by industry but typically include:
- Earnings commentary mentioning the pain points your solution addresses
- Capacity / footprint changes (expansions, openings, closures, M&A)
- Technology investment or modernization announcements
- Leadership changes in roles that drive vendor decisions
- Regulatory, competitive, or market events that increase urgency

Flag explicit buying signals with a ⚑ marker.

### 5. Competitive Technology Landscape
Identify known vendors in their current tech stack relevant to your solution category. Use job postings, press releases, vendor case studies, and LinkedIn profiles as signals.

Note: any known competitors already deployed, integration dependencies, displacement difficulty, and any announced competitive RFPs or evaluations.

### 6. Operations & Footprint
Map the operational footprint that's relevant to your sale: physical locations, scale indicators, network or distribution model, and any public operational metrics. The exact data set varies by vertical — see your vertical pack for the relevant fields.

## Vertical Adaptations

See `references/vertical-frameworks.md` for example research packs across SaaS, fintech, healthcare, and industrial. The framework is the same for any vertical — the keywords, metrics, and trade pubs change. Build your own pack inline in `config/settings.md` if your vertical isn't bundled.

## Output Format

Structure as: Executive Summary → Fit Assessment → Leadership Contacts → Recent Signals → Competitive Landscape → Operations Footprint → Qualification Pre-Check.

Keep the executive summary under 100 words. Every section should be skimmable in 2 minutes total.
