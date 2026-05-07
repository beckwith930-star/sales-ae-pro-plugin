# Sales AE Pro — User Settings

Configure this file after installing the plugin. All commands and skills read from this file to personalize output.

---

## Your Company & Products

```
COMPANY_NAME: [Your company name]
COMPANY_TAGLINE: [One-line description of what your company does]
```

### Product 1
```
PRODUCT_NAME: [Product name]
PRODUCT_DESCRIPTION: [2–3 sentences: what it does, who it's for, primary value proposition]
PRIMARY_VERTICAL: [your primary vertical name — free text, e.g. "SaaS", "fintech", "healthcare", "industrial"]
KEY_OUTCOMES:
  - [Outcome 1 — quantified where possible, e.g. "Reduces processing time by X%"]
  - [Outcome 2]
  - [Outcome 3]
```

### Product 2 (if applicable)
```
PRODUCT_NAME: [Product name]
PRODUCT_DESCRIPTION: [Description]
PRIMARY_VERTICAL: [vertical]
KEY_OUTCOMES:
  - [Outcome 1]
  - [Outcome 2]
```

---

## Salesforce Configuration

```
SALESFORCE_OWNER_NAME: [Your full name exactly as it appears in Salesforce]
SALESFORCE_ORG_ALIAS: [Your sf CLI org alias — run: sf org list]
SALESFORCE_CURRENCY: USD
QUOTA_CURRENT_PERIOD: [e.g., 1200000]
QUOTA_PERIOD: [e.g., FY2026 or Q2 2026]
```

---

## Target Verticals & ICP Definition

Define one ICP block per target vertical. The plugin's prospect research and business case skills use these definitions to score fit and tailor output. The structure is intentionally generic — adapt the field set to match what matters for your sales motion.

```
TARGET_VERTICALS:
  - [your-vertical-1]
  - [your-vertical-2]

ICP_[YOUR_VERTICAL_1]:
  MIN_EMPLOYEES: [e.g., 500]
  REVENUE_RANGE: [e.g., "$250M+"]
  GEOGRAPHIES: [e.g., "North America, EMEA"]
  TECHNOLOGY_MATURITY: [your fit criteria — e.g., "uses one of {Stack A, Stack B}", "has dedicated [X] team"]
  KEY_PAIN_POINTS:
    - [Pain 1]
    - [Pain 2]
    - [Pain 3]

ICP_[YOUR_VERTICAL_2]:
  MIN_EMPLOYEES: [size threshold]
  REVENUE_RANGE: [revenue threshold]
  TECHNOLOGY_MATURITY: [fit criteria]
  KEY_PAIN_POINTS:
    - [Pain 1]
    - [Pain 2]
```

Example bundled patterns are in `skills/prospect-research/references/vertical-frameworks.md` (SaaS, fintech, healthcare, industrial). Copy the structure, replace the values with yours.

---

## Qualification Framework

The defaults below match the three-gate framework. Modify thresholds to match your org's methodology.

```
QUAL_GATE_1_VALUE:
  REQUIRED:
    - Pain point confirmed and quantified
    - Recurring revenue range estimated
    - Compelling event or urgency identified
  BLOCKING_CONDITION: Do not move to Proposal with Gate 1 Red

QUAL_GATE_2_PATH:
  REQUIRED:
    - Champion named and active
    - Economic buyer identified
    - Decision process documented
    - Budget confirmed or fundable
    - Close date tied to customer event
  BLOCKING_CONDITION: Do not submit for discount/approval with Gate 2 Red

QUAL_GATE_3_USE_CASE:
  REQUIRED:
    - Current workflow documented
    - Integration requirements identified
    - Security/compliance requirements known
    - Success metrics agreed
  BLOCKING_CONDITION: Do not provide pricing without Gate 3 Yellow or above
```

---

## Competitor List

List primary competitors your prospects evaluate. Used in prospect research, call prep, and business cases.

```
COMPETITORS:
  - name: [Competitor 1]
    primary_vertical: [vertical]
    displacement_notes: [What makes you win vs. this competitor]
  - name: [Competitor 2]
    primary_vertical: [vertical]
    displacement_notes: [What makes you win vs. this competitor]
```

---

## Customer References

Used in outreach, business cases, and presentation content. Do not use customer names without approval — use neutral size/segment descriptors instead.

```
CUSTOMER_REFERENCES:
  - descriptor: "[Size + segment, e.g. 'Mid-market SaaS company (1,500 employees)']"
    outcome: "[Specific result achieved]"
    vertical: [vertical]
    approved_for_external: false  # Set true only if customer approved named reference

  - descriptor: "[Size + segment, e.g. 'Regional financial services firm']"
    outcome: "[Specific result]"
    vertical: [vertical]
    approved_for_external: false
```

---

## Pipeline Defaults

```
STAGE_PROBABILITIES:
  Prospecting: 10
  Qualification: 20
  Discovery: 30
  Solution/Demo: 40
  Proposal: 60
  Negotiation: 75
  Verbal Commit: 85

STALE_DEAL_THRESHOLD_DAYS: 7
PIPELINE_COVERAGE_TARGET: 3.5  # Healthy = 3-4x quota
```
