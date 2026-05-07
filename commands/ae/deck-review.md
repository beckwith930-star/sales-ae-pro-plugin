---
description: Score a presentation against the Talk Like TED 9-principle framework
allowed-tools: Read, Write, Bash
argument-hint: (attach or reference the deck file path)
---

Review the presentation provided and score it against the Talk Like TED 9-principle framework.

$ARGUMENTS

If no file is referenced, prompt: "Attach the deck or paste the slide content, then re-run."

Load the presentation-coach skill from `${CLAUDE_PLUGIN_ROOT}/skills/presentation-coach/SKILL.md`.
Load settings from `${CLAUDE_PLUGIN_ROOT}/config/settings.md`.

If a .pptx file path is referenced, read it with the Read tool. If it's a PDF, extract text. If the user pasted slide content, use that directly.

**Step 1 — Deck Audit**
Identify: number of slides, presentation type (internal QBR / customer-facing / board), apparent audience, stated or implied objective.

**Step 2 — Score Against the 9 TED Principles**
For each principle, provide:
- Score: 1–5
- Evidence: specific slide(s) or content that drove the score
- Recommendation: one concrete, actionable improvement

| # | Principle | Score | Weakness | Fix |
|---|-----------|-------|----------|-----|
| 1 | Unleash the Master Within (passion & authenticity) | | | |
| 2 | Master the Art of Storytelling | | | |
| 3 | Have a Conversation (natural delivery cues) | | | |
| 4 | Teach Me Something New (novel insight) | | | |
| 5 | Deliver Jaw-Dropping Moments (memorable anchors) | | | |
| 6 | Lighten Up (appropriate levity) | | | |
| 7 | Stick to the 18-Minute Rule (brevity/density) | | | |
| 8 | Paint a Mental Picture (visuals + multisensory) | | | |
| 9 | Stay in Your Lane (authenticity to speaker's expertise) | | | |

**Step 3 — Slide-Level Weaknesses**
List the 3–5 slides most in need of revision. For each:
- Slide number/title
- Problem (specific, not vague)
- Rewrite or redesign recommendation

**Step 4 — Overall Assessment**
- Composite score (average of 9 principles)
- Biggest structural issue (one sentence)
- Top 3 priority fixes before delivery
- If QBR: flag whether the deck advances deal momentum or just reports status
- If customer-facing: flag whether it creates urgency and a clear call to action
