---
name: pipeline-hygiene
description: >
  This skill should be used when the user asks to "check the pipeline", "review open deals",
  "find stale opportunities", "calculate weighted pipeline", "prep for a pipeline review",
  "run pipeline hygiene", or runs /ae:pipeline or /ae:weekly. Also triggers when the user
  asks which deals need attention or wants a prioritized action list.
version: 0.1.0
---

# Pipeline Hygiene

Query, analyze, and clean the open pipeline. Produce a stale deal report, qualification gap matrix, weighted pipeline calculation, and a prioritized action list.

## Staleness Definition

A deal is **stale** if `LastActivityDate` is 7 or more calendar days in the past. Stale deals are categorized:

| Days Since Activity | Category | Default Action |
|--------------------|----------|----------------|
| 7–14 days | Warming — needs re-engagement | Schedule touchpoint |
| 15–30 days | Cold — risk to close date | Immediate outreach + manager flag |
| 30+ days | Frozen — recommend close-lost or push | Deal review required |

## Qualification Gap Analysis

For each open opportunity, assess qualification gate status using available CRM data as proxies:

| Proxy Field | Maps to Gate |
|-------------|-------------|
| Amount populated and reasonable | Gate 1 (Value sizing) |
| Close date within 90 days | Gate 2 (Timeline signal) |
| NextStep mentions a specific next meeting/action | Gate 2 (Process signal) |
| Description mentions use case, workflow, or integration | Gate 3 (Use case fit) |
| Opportunity has associated contacts | Gate 2 (Champion signal) |

Gates marked Red: field is absent or clearly generic. Yellow: field exists but is vague. Green: specific and credible.

Any deal missing 2+ gates = **At Risk**. Flag with a recommendation.

See `references/pipeline-scoring.md` for full scoring rubric and probability calibration guide.

## Weighted Pipeline Calculation

For each opportunity: `Weighted Value = Amount × (Probability / 100)`

Aggregate:
- Total pipeline (unweighted)
- Total weighted pipeline
- Weighted pipeline by stage
- Deals closing this month (sum weighted)
- Deals closing this quarter (sum weighted)

If quota is available in settings.md, calculate: gap to quota and % coverage ratio (weighted pipeline ÷ remaining quota).

## Prioritized Action List

Rank all open deals requiring immediate action. Scoring factors:
1. **Days to close date** (closer = higher priority)
2. **Deal size** (larger = higher priority)
3. **Qualification completeness** (more red gates = more urgent)
4. **Days since last activity** (staler = more urgent)

For each prioritized deal, specify:
- The single most important action
- The owner (AE, SE, leadership)
- A suggested completion date

## Output Format

Produce three sections:
1. **Pipeline Snapshot** — numbers-first summary table
2. **Stale & At-Risk Deals** — flagged list with recommended actions
3. **Priority Action Plan** — top 5–8 actions ranked for the week

Keep the action plan concrete enough that it can be used in a manager 1:1 without modification.
