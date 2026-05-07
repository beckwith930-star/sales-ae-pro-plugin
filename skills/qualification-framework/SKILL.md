---
name: qualification-framework
description: >
  This skill is loaded automatically by all deal-related commands in the Sales AE Pro plugin.
  It provides the three-gate qualification framework used to assess opportunity health across
  prospect research, call prep, post-meeting processing, pipeline hygiene, and business case building.
  Explicitly triggers when the user asks to "qualify a deal", "check qualification", "assess deal health",
  or "run the qualification framework".
version: 0.1.0
---

# Qualification Framework — Three Gates

All deals must pass through three qualification gates before engineering or significant pre-sales resources are allocated. Every deal-related command in this plugin checks gate status and flags gaps.

## Gate 1 — Estimation of Potential Value

**Question this gate answers**: Is this opportunity worth pursuing at the size and urgency implied?

**What must be confirmed:**
- Recurring revenue potential is quantified (range is acceptable; a guess is not)
- Pain point is real and tied to a business outcome the prospect cares about
- The scale of the pain maps to a deal size worth the sales cycle cost
- There is urgency or a compelling event — without urgency, there is no deal, only a conversation

**Evidence sources**: Earnings commentary, operational data, contact statements during discovery, facility count × ARR per site estimates.

**Gate 1 Status Indicators:**
- 🟢 Green: Revenue range estimated, pain confirmed with specifics, compelling event identified
- 🟡 Yellow: Pain acknowledged but not quantified; urgency unclear; deal size speculative
- 🔴 Red: No confirmed pain, no size estimate, no urgency — qualification call needed before any investment

**Blocking condition**: Do not move to Proposal stage with Gate 1 still Red.

---

## Gate 2 — Steps and Timeline to Scale

**Question this gate answers**: Do we know who needs to say yes, and can they actually do it on a timeline that matters?

**What must be confirmed:**
- **Champion**: Named individual who will advocate internally, has credibility, and will share intel
- **Economic Buyer**: Named individual with budget authority; may or may not be the champion
- **Internal Process**: The customer's evaluation, procurement, and approval process is understood
- **Budget**: Exists, is findable this cycle, or a specific future cycle is identified
- **Timeline**: A realistic close date anchored to a customer event (not the AE's quota deadline)

**Evidence sources**: Direct statements from contacts, procurement process documentation, deal stage relative to close date.

**Gate 2 Status Indicators:**
- 🟢 Green: Champion named and active, buyer identified, process mapped, budget confirmed or fundable, close date tied to a real event
- 🟡 Yellow: Champion identified but not fully active; buyer not confirmed; process partially understood; budget soft
- 🔴 Red: No champion, buyer unknown, process opaque, budget not discussed, close date invented — multi-threading required immediately

**Blocking condition**: Do not submit for approval or discount without Gate 2 at Yellow or above.

---

## Gate 3 — Use Case and Workflow Understanding

**Question this gate answers**: Does our solution actually fit their environment and can it be implemented without surprises?

**What must be confirmed:**
- **Current process**: How the relevant workflow operates today — step by step
- **Bottlenecks**: Specific friction points that your solution addresses (not assumed — confirmed)
- **Integration requirements**: What systems your solution must connect to (ERP, CRM, identity provider, observability, ticketing, or other dependencies relevant to your sale)
- **Security and compliance**: Any data residency, security review, or compliance requirements identified
- **Success metrics**: How the customer will measure success — defined before the sale, not after

**Evidence sources**: Technical discovery questions, SE involvement, RFP/RFI responses, IT stakeholder input.

**Gate 3 Status Indicators:**
- 🟢 Green: Workflow documented, bottlenecks confirmed, integration map in hand, security requirements known, success metrics agreed
- 🟡 Yellow: Workflow understood at high level; some integration details outstanding; success metrics not formally agreed
- 🔴 Red: Use case assumed but not confirmed; integration requirements unknown; no technical discovery done — SE engagement required before any proposal

**Blocking condition**: Do not provide scoping or pricing without Gate 3 at Yellow or above.

---

## Framework Application Rules

### Per-Command Behavior
Every deal-related command must:
1. Assess the current gate status based on available data
2. Output a 3-gate status summary (R/Y/G per gate)
3. For each Red gate: name the specific gap and recommend the action to close it

### Gate Status Output Format
```
QUALIFICATION STATUS
Gate 1 — Value:     🟢 / 🟡 / 🔴  [one-sentence evidence or gap]
Gate 2 — Path:      🟢 / 🟡 / 🔴  [one-sentence evidence or gap]
Gate 3 — Use Case:  🟢 / 🟡 / 🔴  [one-sentence evidence or gap]

Red Gate Actions:
• Gate [X]: [Specific action to close the gap] — Owner: [AE / SE / Manager]
```

### Customization
The specific criteria within each gate can be adjusted to match your organization's methodology. Update `${CLAUDE_PLUGIN_ROOT}/config/settings.md` to modify thresholds, add gates, or rename criteria to match your internal language (e.g., MEDDIC, BANT, MEDDPICC).

See `references/three-gates.md` for alignment mapping to common enterprise qualification frameworks.
