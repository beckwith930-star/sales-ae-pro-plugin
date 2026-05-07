# Pipeline Scoring & Probability Calibration

## Stage-Level Default Probabilities

Use these as baselines if Salesforce probability is not customized. Override with your org's actuals if available in settings.md.

| Stage | Default Probability | What It Means |
|-------|--------------------|-|
| Prospecting | 10% | Identified, not yet engaged |
| Qualification | 20% | In discovery, no gates confirmed |
| Discovery | 30% | Active conversations, 1+ gates confirmed |
| Solution/Demo | 40% | Demonstrated value, buyer mapped |
| Proposal | 60% | Formal proposal delivered |
| Negotiation | 75% | Commercial terms being worked |
| Verbal Commit | 85% | Customer said yes, paper pending |
| Closed Won | 100% | |
| Closed Lost | 0% | |

## Probability Adjustments

Add or subtract from stage baseline based on qualification signal quality:

| Factor | Adjustment |
|--------|-----------|
| Champion identified and actively engaged | +10% |
| Budget confirmed and allocated | +10% |
| Close date confirmed by customer | +5% |
| Compelling event (deadline with consequence) | +10% |
| No champion identified | -15% |
| Procurement process not understood | -10% |
| Competitor shortlisted | -10% |
| Deal stale 15+ days | -15% |
| Deal stale 30+ days | -25% |
| Close date slipped once already | -10% |

## Pipeline Coverage Ratio

A healthy pipeline requires coverage above quota to account for deal loss rates:

| Coverage Ratio | Pipeline Health |
|---------------|----------------|
| < 2x quota | Critically underpowered — build mode |
| 2–3x quota | Thin — focus on new pipe generation |
| 3–4x quota | Healthy — focus on closing existing deals |
| 4x+ quota | Strong — qualify harder, kill weak deals |

## Deal Score Card (Per Opportunity)

Run this for every deal in a pipeline review:

| Question | Yes (+1) | No (0) |
|----------|----------|--------|
| Champion identified by name? | | |
| Economic buyer identified? | | |
| Budget confirmed (allocated or findable)? | | |
| Decision process documented? | | |
| Compelling event exists? | | |
| Timeline confirmed by customer? | | |
| Use case and workflow mapped? | | |
| Integration requirements identified? | | |
| Competitive situation understood? | | |
| Reference customer available? | | |

Score interpretation: 8–10 = Strong; 5–7 = Developing; <5 = At Risk.
