---
name: discovery-call-prep
description: >
  This skill should be used when the user asks to "prep for a call", "get ready for a meeting",
  "prepare discovery questions", "build a pre-call brief", "create a talk track", or runs
  /ae:call-prep. Applies to first discovery calls, multi-stakeholder demos, EBC sessions,
  and any customer or prospect meeting requiring structured preparation.
version: 0.1.0
---

# Discovery Call Prep

Produce a complete pre-call package: CRM + email context brief, tailored discovery questions mapped to qualification gates, an opening talk track with pivots, and anticipated objections with responses.

## Pre-Call Briefing Structure

Synthesize available data into a single-page brief covering:
- **Account status**: stage, deal size, last activity, open opportunities from CRM
- **Contact profile**: title, tenure, prior companies, known interests or stated priorities, any shared history
- **Pending questions**: open items from prior interactions that this meeting should resolve
- **Meeting objective**: one specific outcome that advances the deal (not "have a good meeting")

## Discovery Questions — Qualification Gate Mapping

Load the qualification framework from `${CLAUDE_PLUGIN_ROOT}/skills/qualification-framework/SKILL.md`.

Map questions to the three qualification gates. Each question should be:
- Open-ended (never yes/no)
- Designed to surface data for a specific gate
- Paired with a follow-up or "pivot" if the contact deflects

### Gate 1 Questions (Value Sizing)
Focus: pain point depth, quantified business impact, urgency, budget awareness.
- "Walk me through your current [process]. Where does it break down?"
- "When that happens, what's the operational and financial impact?"
- "Is this on your leadership's priority list for this year — and what's driving that timing?"

### Gate 2 Questions (Path to Scale)
Focus: champion vs. buyer, internal process, budget cycle, timeline.
- "Who else needs to be part of this conversation before you could move forward?"
- "When decisions like this get made at [company], what does the process typically look like?"
- "Do you have budget allocated, or would this need to go through an approval cycle?"

### Gate 3 Questions (Use Case & Workflow Fit)
Focus: current workflow, bottlenecks, integration dependencies, security/compliance.
- "Take me through how [relevant workflow] works today — start to finish."
- "What systems does this touch? ERP, CRM, identity, observability, or other core dependencies?"
- "Have you evaluated anything else in this space? What did you learn?"

## Talk Track Structure

### Opening (under 90 seconds verbal)
1. Acknowledge the meeting context (referral, prior research, specific signal)
2. One-sentence company positioning — outcome-focused, not feature-focused
3. Bridge to discovery: "The reason I wanted to spend time with you today…"

### Pivot Statements
Prepare for 3 common early deflections:
- "We're already working with [competitor]" → acknowledge, pivot to what's not covered
- "Send me some information first" → offer to tailor it, ask one clarifying question
- "We're not really looking right now" → ask about their current pain level and timeline

## Objection Prep

See `references/objection-library.md` for a categorized library of common objections and responses by stage and persona.

For each call, identify the 4–5 most likely objections given the contact's role and meeting type. Format each as: **Objection → Direct Response → Follow-Up Question**.

## Meeting Type Adaptations

| Meeting Type | Primary Goal | Key Qualification Focus |
|---|---|---|
| Cold discovery | Surface pain and urgency | Gate 1 and 3 |
| Multi-stakeholder discovery | Map the buying committee | Gate 2 |
| Technical deep-dive | Confirm integration fit | Gate 3 |
| Executive briefing | Build strategic urgency | Gate 1 and 2 |
| Renewal/expansion | Quantify current value + expand scope | All three gates, expansion framing |
