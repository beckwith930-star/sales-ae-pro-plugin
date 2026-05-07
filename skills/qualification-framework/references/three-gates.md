# Three-Gate Framework — Alignment to Common Methodologies

## Mapping to MEDDIC / MEDDPICC

| Three Gates | MEDDIC Component |
|------------|-----------------|
| Gate 1 — Value | Metrics (M), Economic Buyer (E partial) |
| Gate 2 — Path | Decision Criteria (D), Decision Process (D), Paper Process (P), Champion (C) |
| Gate 3 — Use Case | Identify Pain (I), Implicate (I), Competition (C) |

MEDDPICC additions not explicitly in the three gates:
- **Paper Process** → embed in Gate 2 under "internal process"
- **Competition** → embed in Gate 3 under "integration/landscape"
- **Implicate** → embed in Gate 1 under "urgency / compelling event"

## Mapping to BANT

| Three Gates | BANT |
|------------|------|
| Gate 1 — Value | Need (N) |
| Gate 2 — Path | Budget (B), Authority (A), Timeline (T) |
| Gate 3 — Use Case | Need (N) — technical depth |

BANT limitation: It doesn't assess use case fit or workflow understanding — Gate 3 fills that gap.

## Mapping to Challenger / Insight Selling

The Three Gates framework is methodology-agnostic but pairs well with Challenger:
- Gate 1 is where you teach the prospect something new about the scale or nature of their problem (Teach)
- Gate 2 is where you tailor to their decision process (Tailor)
- Gate 3 is where you confirm the workflow fit and take control of the technical validation (Take Control)

## Customizing Gate Criteria

Update `${CLAUDE_PLUGIN_ROOT}/config/settings.md` to modify:

```
# Qualification Framework Customization

## Gate 1 — Value
Required evidence before advancing:
- [Your criteria here]

## Gate 2 — Path to Scale
Required evidence before advancing:
- [Your criteria here]

## Gate 3 — Use Case Fit
Required evidence before advancing:
- [Your criteria here]

## Blocking Rules
- Do not [action] without Gate [X] at [status] or above.
```

## Common Qualification Anti-Patterns

**"Happy ears"** — AE hears interest and marks gates Green without explicit confirmation. Rule: a gate is Green only when the customer confirmed it, not when the AE inferred it.

**Skipping Gate 2** — AE focuses on product fit (Gate 3) and pain (Gate 1) but doesn't map the buying committee until too late. Rule: if champion is not named by end of second meeting, deal is Yellow on Gate 2.

**Manufactured urgency** — AE invents a close date tied to their own quota. Rule: close date must be anchored to a customer-stated event (budget cycle, facility opening, contract expiry, board deadline).

**False Green on Gate 3** — AE assumes integration fit without involving a technical resource. Rule: Gate 3 cannot be Green without SE sign-off on integration requirements.
