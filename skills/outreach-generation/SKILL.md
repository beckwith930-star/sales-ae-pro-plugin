---
name: outreach-generation
description: >
  This skill should be used when the user asks to "write a cold email", "draft outreach",
  "create a LinkedIn message", "write a cold call script", "build a cadence", "reach out to [company]",
  "generate a prospect sequence", or runs /ae:outreach. Applies to cold and warm outreach
  across all channels: email, LinkedIn, and phone.
version: 0.1.0
---

# Outreach Generation

Generate personalized, channel-specific outreach for a target prospect. All content is calibrated for B2B enterprise sales: direct, low-friction, outcomes-focused, and under the word limits that drive response rates.

## Cold Email Rules

**Hard constraints:**
- Under 125 words total
- No subject line clickbait ("Quick question" is acceptable; "Unlock your potential" is not)
- No opener that references yourself before establishing relevance to them
- No feature lists — one outcome, one proof point maximum
- One CTA, low-friction (15-minute call, not "let's schedule a demo")
- No attachments implied in a cold email

**Subject line formula:** Specific outcome or signal + company name or role reference.
Good: "Replenishment accuracy at [Company]" / "Cutting overtime at [Company]'s DCs"
Bad: "Following up" / "Quick question about your operations"

**Email structure:**
1. Hook line: a specific, researched signal about their company (news, job posting, earnings commentary)
2. One-sentence bridge: what you do, framed as an outcome they'd care about
3. One proof line: a customer result in a comparable context (no names required, use industry/vertical)
4. CTA: specific and low-commitment

See `references/cadence-templates.md` for message templates by vertical and persona.

## LinkedIn Connection Request Rules

**Hard constraints:**
- Under 300 characters
- No pitch
- References something real: shared connection, their recent post, their role, their company news
- Ends with a reason to connect — not a meeting ask

**Formula:** [Specific observation about them] + [Why connecting makes sense] + [Optional soft bridge]

## LinkedIn Follow-Up Message

Sent after connection accepted, no reply received. Under 150 words.
- Opens with context from the connection request (don't pretend it was organic if it wasn't)
- One soft pivot to a specific problem your solution addresses in their context
- One CTA (not a meeting ask — a question or a content offer)

## Phone Talk Track

**Cold call opener (30 seconds verbal):**
- Pattern interrupt first line (not "Did I catch you at a bad time?")
- Who you are and company — fast
- Why you're calling: specific to their context, not generic
- Permission ask: "I have 30 seconds — can I tell you why I called?"

**Voicemail (under 25 seconds):**
- Name, company, one-sentence hook
- Callback number stated once, clearly
- No long explanation — create curiosity, not information overload

## 3-Week Cadence Structure

A standard cold outreach cadence for enterprise B2B:

| Day | Channel | Action |
|-----|---------|--------|
| 1 | Email | Cold email (primary contact) |
| 2 | LinkedIn | Connection request |
| 3 | Phone | Cold call + voicemail if no answer |
| 5 | Email | Follow-up email referencing cold call |
| 8 | LinkedIn | Follow-up message (post-connection) |
| 10 | Phone | Second call attempt |
| 14 | Email | Value-add email (insight, case study, or relevant news) |
| 17 | LinkedIn | Engage with their content if possible + message |
| 21 | Email | Break-up email ("Last reach out — happy to reconnect later") |

Adapt timing based on response signals. If any reply at any point — break sequence and respond personally.

## Persona Adaptations

Adapt messaging by contact title/persona. Reference `references/cadence-templates.md` for templates organized by persona: VP Operations / Operational Leader, CIO / VP IT / Head of Platform, CFO / Finance, and Champion / Director-level buyer. Each template adapts to your vertical via the proof points and pain language pulled from `config/settings.md`.
