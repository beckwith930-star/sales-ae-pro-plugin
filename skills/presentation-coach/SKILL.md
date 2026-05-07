---
name: presentation-coach
description: >
  This skill should be used when the user asks to "review my deck", "score my presentation",
  "give feedback on my slides", "check this against TED principles", "coach my QBR",
  "make my presentation better", or runs /ae:deck-review or /ae:qbr. Applies to both
  internal presentations (QBRs, deal reviews, team meetings) and customer-facing decks
  (executive briefings, proposals, demos, board presentations).
version: 0.1.0
---

# Presentation Coach

Review any deck against the Talk Like TED 9-principle framework. Score each principle with evidence, identify weak slides, and recommend specific improvements. Apply distinct criteria for internal QBRs vs. customer-facing presentations.

## The Talk Like TED 9 Principles

See `references/talk-like-ted.md` for the full framework with scoring rubrics and examples.

Summary of all nine principles:

| # | Principle | Core Question |
|---|-----------|---------------|
| 1 | Unleash the Master Within | Does the presenter's genuine passion come through? |
| 2 | Master the Art of Storytelling | Is there a narrative arc with a protagonist? |
| 3 | Have a Conversation | Does it feel like a dialogue, not a lecture? |
| 4 | Teach Me Something New | Does the audience learn something they didn't know? |
| 5 | Deliver Jaw-Dropping Moments | Is there one moment designed to be unforgettable? |
| 6 | Lighten Up | Is there appropriate levity — humor or humanizing elements? |
| 7 | Stick to the 18-Minute Rule | Is every slide earning its place? |
| 8 | Paint a Mental Picture | Do visuals support the narrative? Is it multisensory? |
| 9 | Stay in Your Lane | Does the content stay in the speaker's zone of authentic expertise? |

## Scoring Rubric

Score each principle 1–5:
- **5**: Excellent — strong execution, hard to improve
- **4**: Good — present and effective, minor improvements available
- **3**: Adequate — present but underdeveloped; misses its potential
- **2**: Weak — principle attempted but fails to land
- **1**: Missing — no evidence of this principle in the deck

## Deck Type Adaptations

### Internal QBR / Deal Review
Key principles to weight heavily: 4 (novel insight), 7 (brevity), 9 (authenticity/credibility).
Common failure modes:
- Status-reporting instead of insight delivery (fails principle 4)
- Slide count creep — too many slides, most don't earn their place (fails principle 7)
- No clear "so what" or leadership ask (fails principles 2 and 5)

A strong QBR deck answers: What happened? What does it mean? What do you need?

### Customer-Facing Executive Presentation
Key principles to weight heavily: 2 (storytelling), 5 (jaw-dropping moment), 8 (visuals).
Common failure modes:
- Feature-focused instead of outcome-focused (fails principle 2)
- No memorable anchor — the deck is forgettable 24 hours later (fails principle 5)
- Text-heavy slides that work as documents but fail as presentations (fails principle 8)

A strong customer-facing deck creates urgency, demonstrates understanding of their world, and makes the next step obvious.

## Slide-Level Review Process

1. Read all slides in sequence
2. Identify which principle each slide primarily serves (or fails to serve)
3. Flag the 3–5 slides most in need of revision
4. For each flagged slide: state the problem specifically, provide a concrete rewrite or redesign recommendation
5. Do not suggest changes for slides that are working — only flag genuine weaknesses

## Output Format

1. Deck audit summary (type, audience, objective, slide count)
2. 9-principle scorecard table with score, evidence, and recommendation per principle
3. Slide-level weakness list (top 3–5)
4. Overall composite score and top 3 priority fixes
5. Deck-type-specific assessment (QBR or customer-facing)
