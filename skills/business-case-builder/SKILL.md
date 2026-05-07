---
name: business-case-builder
description: >
  This skill should be used when the user asks to "build a business case", "size the opportunity",
  "create an expansion case", "build a ROI model", "prepare for a deal review", "write an internal
  business case", or runs /ae:business-case. Applies to both new logo opportunities and expansion
  deals where internal justification is required.
version: 0.1.0
---

# Business Case Builder

Build a structured internal expansion business case from public company data, earnings commentary, and CRM context. Output is designed for deal reviews, leadership briefings, and supporting an economic buyer's internal approval process.

## Source Priority

1. 10-K / Annual Report (SEC EDGAR for public companies)
2. Most recent earnings call transcript (Seeking Alpha, company IR site)
3. Investor Day presentations
4. Press releases and trade press
5. LinkedIn job postings (signals operational investment priorities)
6. Industry analyst benchmarks for context

## Business Case Structure

### Executive Summary
One paragraph. State: the company, the size of the opportunity, the core operational pain evidenced in public data, and the recommended approach. Written for a CRO reading in 30 seconds. No jargon.

### Pain Point Mapping
Identify 3–5 operational pain points with evidence:
- Quote or data point from source document
- Page/slide reference if applicable
- How your solution addresses it (from settings.md product positioning)
- Estimated impact range (use industry benchmarks if company-specific data is unavailable)

See `references/business-case-framework.md` for pain point templates and impact sizing benchmarks by vertical.

### Solution Fit Matrix
Map your product's core capabilities to their stated priorities:

| Their Priority | Your Capability | Fit Level | Note |
|----------------|----------------|-----------|------|
| [From earnings/10-K] | [From settings.md] | Strong/Moderate/Gap | |

Identify the primary use case, secondary use cases, and any gaps requiring partner or services involvement.

### Facility-Level Opportunity Sizing

Use public facility data to build a bottom-up opportunity estimate:

1. Total addressable sites (from filings, press, logistics real estate databases)
2. Addressable sites (subset that fits your ICP — exclude sites below size/complexity threshold)
3. ARR per site (use a range: conservative / base / optimistic)
4. Total ARR range: addressable sites × ARR per site range
5. Phased path: Pilot (1–2 sites) → Phase 2 (regional) → Full deployment

Be explicit about assumptions. Executives will challenge ranges — pre-empt by anchoring to comparable customer data.

### Competitive Urgency

Three urgency drivers to address:
1. **Competitive pressure**: Is a competitor already in their environment or shortlisted?
2. **Market window**: Is there an operational event (fiscal year-end, regulatory deadline, planned system migration, leadership transition, contract expiry) where timing matters?
3. **Cost of delay**: Quantify what one more year of the status quo costs in labor, errors, or missed throughput — even as an estimate.

### Pilot-to-Enterprise Playbook

Define the expansion path:

| Phase | Scope | Success Metrics | Timeline | Key Dependencies |
|-------|-------|----------------|----------|------------------|
| Pilot | 1–2 sites | [Specific metrics] | [Weeks] | IT access, ops champion |
| Phase 2 | Regional expansion | [Metrics] | [Months] | Procurement, IT rollout |
| Full Deployment | All addressable sites | [Metrics] | [Months] | Executive sponsorship |

### Qualification Gate Status
Map business case findings to the three qualification gates. Flag any gate that public data cannot confirm — those gaps become the discovery agenda.

### Leadership Asks
List 2–3 specific asks from your sales leadership: executive sponsor introduction, reference customer, pricing flexibility, implementation resources, or other.

## Output Format

Structure as a 1–2 page internal document. Sections should be complete enough to present in a deal review without additional explanation. Numbers should always include the underlying assumption.
