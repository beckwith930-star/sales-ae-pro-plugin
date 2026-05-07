---
description: Pre-call package — briefing, questions, talk track, objections
allowed-tools: WebSearch, WebFetch, Bash, Read, Write
argument-hint: "company contact-name meeting-type"
---

Generate a full pre-call preparation package for:
- Company: $1
- Contact: $2
- Meeting type: $3

Load the discovery-call-prep skill from `${CLAUDE_PLUGIN_ROOT}/skills/discovery-call-prep/SKILL.md`.
Load the qualification-framework skill from `${CLAUDE_PLUGIN_ROOT}/skills/qualification-framework/SKILL.md`.
Load user settings from `${CLAUDE_PLUGIN_ROOT}/config/settings.md`.

**Step 1 — Pull CRM Context**
Query Salesforce for this account and contact:
```bash
sf data query --query "SELECT Id, Name, StageName, Amount, LastActivityDate, NextStep, Description FROM Opportunity WHERE Account.Name LIKE '%$1%' AND IsClosed = false ORDER BY LastActivityDate DESC LIMIT 5" --target-org ~~salesforce-org
```
```bash
sf data query --query "SELECT Id, FirstName, LastName, Title, Email, Phone, Account.Name FROM Contact WHERE Account.Name LIKE '%$1%' LIMIT 10" --target-org ~~salesforce-org
```

If Salesforce is unavailable, note the gap and proceed with web research only.

**Step 2 — Contact Research**
Research $2 at $1:
- Current role, tenure, prior companies
- LinkedIn activity or public statements relevant to your solution
- Any shared connections, mutual customers, or prior touch points
- Decision-making authority relative to meeting type

**Step 3 — Pre-Call Briefing**
Synthesize CRM data + contact research into a 1-page brief:
- Account status (stage, open opportunities, last activity)
- Contact background and likely agenda
- Known pain points and open questions from prior interactions
- Risks or sensitivities to be aware of

**Step 4 — Discovery Questions**
Generate 8–10 tailored discovery questions mapped to the three qualification gates:
- Gate 1 (Value sizing): 3 questions
- Gate 2 (Path to scale): 3 questions
- Gate 3 (Use case/workflow fit): 3–4 questions

Questions should be open-ended, sequenced logically, and include a "pivot" version for when the conversation goes off track.

**Step 5 — Talk Track**
Write a concise opening talk track (under 90 seconds verbal equivalent):
- Strong opener tied to a recent company signal or pain point
- One-sentence positioning of your solution
- Bridge to discovery ("The reason I wanted to spend time with you today…")
Include 2–3 pivot statements for common early deflections.

**Step 6 — Objection Prep**
List 4–5 likely objections for this meeting type and contact profile. For each: the objection, a direct response, and a follow-up question to regain momentum.

**Step 7 — Qualification Status Check**
Based on everything known, flag which qualification gates are green / yellow / red. Note what this meeting needs to accomplish to advance the gates.
