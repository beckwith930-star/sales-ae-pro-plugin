# Business Case Framework — Pain Points, Impact Sizing, ROI Templates

The frameworks below are vertical-agnostic. Each pain-point template includes:
- The **earnings/public quote pattern** — phrases that signal the pain is on leadership's radar
- The **impact-sizing model** — how to estimate the dollar value of solving it
- An **assumption to state explicitly** — the variable executives will challenge

For vertical-specific impact ranges, configure them in `config/settings.md` under your `KEY_OUTCOMES` per product. The skill reads those when building the case.

---

## Pain Point Templates

### 1. Operational Cost Reduction

**Common quote pattern**: *"[Cost category] remains our largest variable cost…"* / *"We continue to see [cost type] pressure…"*

**Impact-sizing model**:
```
Annual savings = (cost category total) × (% reduction your solution delivers, range)
```

State the assumption: *"Based on [N units] at [average cost per unit] per [time period]."*

For initial estimates, use the conservative end of your customer-validated range. Optimistic numbers are easy to discount.

---

### 2. Process Quality / Error Reduction

**Common quote pattern**: *"[Quality metric] remains a challenge…"* / *"[Error type] rates have impacted [downstream outcome]…"*

**Impact-sizing model**:
```
Annual savings = (current error volume) × (% reduction) × (average cost per error)
```

Cost per error includes: rework cost, customer-facing remediation, downstream impact (lost trust, churn risk). Industry benchmarks for "cost per error" exist for most categories — cite the source.

---

### 3. Throughput / Capacity

**Common quote pattern**: *"We are investing to expand [capacity area]…"* / *"[Operational lever] remains a focus area…"*

**Impact-sizing model**:
```
Capacity unlocked = (current throughput) × (% improvement)
Revenue impact = (capacity unlocked) × (revenue per unit) [if revenue-tied]
Cost avoidance = (capacity unlocked) ÷ (current cost per unit) [if cost-tied]
```

State whether the customer captures this as growth (revenue) or efficiency (cost avoidance). Both are valid — but the buyer's framing dictates yours.

---

### 4. Compliance / Risk Reduction

**Common quote pattern**: *"[Regulatory/audit/compliance] requirements continue to increase…"* / *"Recent [enforcement action / audit finding] has prompted…"*

**Impact-sizing model**:
```
Cost avoidance = (probability of incident) × (cost of incident if unmitigated)
+ Compliance overhead reduction = (current compliance FTE cost) × (% reduction)
```

Probabilities are speculative — use industry benchmarks or the customer's own historical incident rate. Always show your work; never present a probability without sourcing.

---

## ROI Model Structure (Simplified)

For pilot proposal:
```
Pilot Investment: $[X]
Pilot Sites/Scope: [N]
Annual Savings per Site/Unit (conservative): $[Y]
Payback Period: [X / (Y × N)] months
3-Year ROI: [(Y × N × 3) - X] / X × 100%
```

Always present three scenarios:
- **Conservative**: low end of savings ranges; shortest realistic payback
- **Base**: midpoint; most-likely case
- **Optimistic**: high end; explicitly state what assumptions must hold

Executives discount optimistic cases by default. Conservative cases that still clear the hurdle rate are far more persuasive than optimistic ones that require everything to go right.

---

## Comparable Customer References (Template)

When using customer references in a business case (without naming them), use neutral size + segment descriptors:

- *"A mid-market SaaS company with 1,500 employees achieved…"*
- *"A regional financial services firm in the [size band] tier saw…"*
- *"A specialty manufacturer with multi-site operations reduced…"*
- *"A health-system IDN with [N] facilities improved…"*

Load your actual customer references from `${CLAUDE_PLUGIN_ROOT}/config/settings.md` to replace these templates with real proof points. Set `approved_for_external: true` only for customers who have approved named references.

---

## What this framework does *not* prescribe

- **Specific impact percentages** — those come from your `KEY_OUTCOMES` config, anchored to your real customer data.
- **Vertical-specific pain points** — bundled vertical packs in `skills/prospect-research/references/vertical-frameworks.md` cover the metric language by industry.
- **Pricing or contract terms** — outside the scope of this skill.

The framework is structural. The numbers are yours.
