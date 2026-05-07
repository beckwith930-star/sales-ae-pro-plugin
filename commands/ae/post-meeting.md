---
description: Process meeting notes into CRM note, briefing, follow-up email, and qual update
allowed-tools: Bash, Read, Write, WebSearch
argument-hint: (paste meeting notes or transcript after running command)
---

Process the following meeting notes into all post-meeting deliverables.

If no notes are appended to this command, prompt the user: "Paste your meeting notes or transcript below, then re-run."

Meeting notes/transcript:
$ARGUMENTS

Load the post-meeting-processing skill from `${CLAUDE_PLUGIN_ROOT}/skills/post-meeting-processing/SKILL.md`.
Load the qualification-framework skill from `${CLAUDE_PLUGIN_ROOT}/skills/qualification-framework/SKILL.md`.
Load user settings from `${CLAUDE_PLUGIN_ROOT}/config/settings.md`.

**Deliverable 1 — Salesforce Activity Note**
Format: Date-stamped, max 200 words, written for a CRM audience (concise, factual, scannable).
Structure:
- Meeting type and attendees
- Key discussion points (3–5 bullets)
- Qualification signals captured (per gate)
- Agreed next action with owner and date
- Any blockers or risks surfaced

Then attempt to write this to Salesforce:
```bash
sf data create record --sobject Task --values "Subject='Meeting Summary - [DATE]' Description='[NOTE_CONTENT]' Status='Completed' ActivityDate='[DATE]'" --target-org ~~salesforce-org
```

**Deliverable 2 — Internal Leadership Briefing (1 page)**
Written for your manager or VP. Cover:
- Account: company, opportunity stage, deal size estimate
- What happened in the meeting (narrative, not bullets)
- Qualification gate status: green / yellow / red per gate with evidence
- Competitive intelligence surfaced
- Risk factors
- Recommended next steps and ask from leadership (if any)

**Deliverable 3 — Follow-Up Email Draft**
Recipient: primary contact from the meeting.
Format: Under 150 words. Professional, direct, no filler.
Structure:
- One-sentence recap of what was agreed
- Attach or reference any promised materials
- Confirm next step with specific date/time ask
- Clean sign-off

**Deliverable 4 — Qualification Checklist Update**
For each of the three qualification gates, update status based on what was learned:
- Gate 1 (Value): What was confirmed, what's still unknown
- Gate 2 (Path to scale): Champion identified? Budget process known? Timeline?
- Gate 3 (Use case): Current workflow mapped? Bottlenecks confirmed? Integration needs?

Flag any gates that remain red after this meeting. Recommend specific actions to close each gap.
