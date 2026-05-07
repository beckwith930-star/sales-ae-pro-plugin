---
description: Full outreach package — cold email, LinkedIn, phone, 3-week cadence
allowed-tools: WebSearch, WebFetch, Read, Write, Bash
argument-hint: [company name]
---

Generate a full outreach package for: $ARGUMENTS

Load the outreach-generation skill from `${CLAUDE_PLUGIN_ROOT}/skills/outreach-generation/SKILL.md`.
Load the qualification-framework skill from `${CLAUDE_PLUGIN_ROOT}/skills/qualification-framework/SKILL.md`.
Load user settings from `${CLAUDE_PLUGIN_ROOT}/config/settings.md`.

**Step 1 — Quick Prospect Scan**
Search for recent signals on $ARGUMENTS: news, leadership changes, job postings (especially ops/tech), earnings commentary, or industry pain points. Identify the 1–2 most relevant hooks.

**Step 2 — Identify Primary Contact**
Based on settings ICP definition and vertical fit, identify the single best outreach target at this company. Use public sources (LinkedIn, company website). Note: name, title, likely pain point.

**Step 3 — Cold Email**
Write a cold email under 125 words.
Rules:
- Subject line: specific, no clickbait, references a real signal or outcome
- Line 1: direct relevance hook (not "I hope this finds you well")
- Lines 2–3: one concrete outcome your solution delivers, tied to their context
- Line 4: single, low-friction CTA (15-minute call, not "would love to connect")
- No attachments implied. No feature lists. No company history.

**Step 4 — LinkedIn Connection Request**
Write a LinkedIn connection note under 300 characters.
Rules: Personalized, not a pitch. References something real about them or their company. Ends with a reason to connect, not a meeting ask.

**Step 5 — LinkedIn Follow-Up Message**
Assuming the connection was accepted but no reply. Under 150 words. References the connection request context. Soft pivot to a specific problem your solution addresses. One CTA.

**Step 6 — Phone Talk Track**
Write a 30-second cold call opener.
Structure: pattern interrupt opener → who you are → why you're calling (specific, not generic) → permission ask to continue.
Include a voicemail version (under 25 seconds).

**Step 7 — 3-Week Cadence Plan**
Map a sequenced 3-week outreach cadence using all channels above:
| Day | Channel | Action | Content Ref |
|-----|---------|--------|-------------|
Format it as a calendar-style action plan the AE can execute without modification.
