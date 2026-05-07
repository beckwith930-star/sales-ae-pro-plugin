---
name: post-meeting-processing
description: >
  This skill should be used when the user asks to "process meeting notes", "write up the call",
  "create a follow-up email", "log the meeting", "write a Salesforce note", "brief the team on the call",
  or runs /ae:post-meeting. Applies to any customer or prospect interaction that needs to be
  documented, logged, and acted on.
version: 0.1.0
---

# Post-Meeting Processing

Transform raw meeting notes or a transcript into four ready-to-use deliverables: a Salesforce-ready CRM note, an internal leadership briefing, a follow-up email draft, and an updated qualification checklist.

## Deliverable 1 — Salesforce Activity Note

**Format rules:**
- Date-stamped header: `[YYYY-MM-DD] — [Meeting Type] — [Account Name]`
- Max 200 words
- Written for a CRM audience: concise, factual, scannable
- No editorializing — only what was said or observed

**Structure:**
```
Attendees: [names and titles]
Purpose: [type of meeting]

Key Discussion Points:
• [Point 1]
• [Point 2]
• [Point 3]

Qualification Signals:
• Gate 1 (Value): [what was confirmed or surfaced]
• Gate 2 (Process): [what was confirmed or surfaced]
• Gate 3 (Use case): [what was confirmed or surfaced]

Next Action: [specific action] — Owner: [name] — Due: [date]
Risks/Blockers: [any, or "None noted"]
```

See `references/salesforce-note-format.md` for field-by-field Salesforce logging guidance.

## Deliverable 2 — Internal Leadership Briefing

**Audience**: Manager, VP, or CRO
**Length**: One page maximum
**Tone**: Direct, no hedging, forward-looking

Sections:
1. **Account context**: Company, stage, opportunity size, current close date
2. **What happened**: Narrative summary (2–3 paragraphs) — what was discussed, what shifted, what surprised you
3. **Qualification gate status**: Green / Yellow / Red per gate with specific evidence from the meeting
4. **Competitive intel**: Any mentions of competitors, evaluations, or incumbent vendor status
5. **Risks**: Specific, named risks — not generic concerns
6. **Recommended next steps**: What you're doing and what you need from leadership
7. **Leadership ask** (if applicable): Executive intro, pricing exception, reference customer, resource request

## Deliverable 3 — Follow-Up Email

**Rules:**
- Under 150 words
- No filler: no "Per our conversation", no "I hope this finds you well"
- Opens with the most important agreed-upon point or action
- References any promised materials specifically (not "as discussed")
- Closes with a concrete next step request — date and format specified
- Professional tone, not warm-fuzzy

**Template structure:**
```
[Reference the single most important outcome of the meeting]

[Attach or link promised materials if any]

[Confirm agreed next action with specific ask: "Are you available [date range] for [format]?"]

[Clean sign-off]
```

## Deliverable 4 — Qualification Checklist Update

For each of the three gates, document what was confirmed, what remains open, and what action closes the gap:

| Gate | Status | Confirmed This Meeting | Still Unknown | Action to Close |
|------|--------|------------------------|---------------|-----------------|
| Gate 1: Value | R/Y/G | | | |
| Gate 2: Path | R/Y/G | | | |
| Gate 3: Use Case | R/Y/G | | | |

Any gate still Red after two discovery meetings = deal at risk. Flag and recommend a specific corrective action.
