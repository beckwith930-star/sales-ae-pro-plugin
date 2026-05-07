# Vertical Research Frameworks

Sales AE Pro is vertical-agnostic by design. The prospect-research skill produces the same six research modules regardless of vertical — what changes by vertical is **the keywords, the metrics, the personas, and the trade pubs you watch**.

This file documents how to research any vertical, then provides four example vertical packs (SaaS, fintech, healthcare, industrial) you can copy into `config/settings.md`. Your own vertical likely fits the same template.

---

## How to research any vertical (six dimensions)

For any target vertical, build a research pack that covers:

1. **Operational metrics** — the numbers buyers in this vertical actually report on (cited in earnings, board decks, OKRs)
2. **Buyer personas** — the 4-6 titles who appear on a typical buying committee
3. **Tech stack signals** — incumbent vendor categories whose presence/absence tells you the maturity level
4. **ICP signals** — public events that mark a strong-fit account (funding, M&A, regulatory, leadership change)
5. **Disqualifying signals** — events that mark an account as not-fit (recent procurement freeze, parent acquisition, segment shift)
6. **Trade publications** — the 2-3 industry pubs that buyers actually read; signals here lead news searches by 1-2 weeks

A complete vertical pack fills these six dimensions with 4-8 entries each.

---

## Example pack — SaaS / Dev Tools

### Operational metrics
- ARR, NRR, gross margin, magic number, payback period, DAU/MAU
- Customer count, logos, paid seats, deployment cohort growth
- Engineering headcount, R&D as % of revenue, deploy frequency

### Buyer personas
- VP Engineering, Director of Platform / DevOps, RevOps lead, Head of Data, CTO, Head of Product

### Tech stack signals
- Cloud provider, observability vendor, identity provider, source-control vendor, CI/CD platform, data warehouse
- Recent migrations or RFPs in any of the above

### ICP signals (strong fit)
- Series B+ funding round
- New VP Eng or new CTO in last 6 months
- Headcount growth >30% YoY
- Public commitment to "platform consolidation" or "developer productivity"
- Stated post-IPO efficiency push

### Disqualifying signals
- Recent down-round or restructuring
- Hiring freeze announced last quarter
- Parent acquisition that froze procurement

### Trade pubs
- Crunchbase, The Information, TechCrunch, Lenny's Newsletter, Pragmatic Engineer

---

## Example pack — Fintech / Payments

### Operational metrics
- TPV (total payment volume), take rate, authorization rate, fraud rate, chargeback rate
- Active accounts, monthly active payers, ARPU, churn rate
- Capital ratios (for licensed entities), regulatory cost as % of opex

### Buyer personas
- Head of Risk, VP Compliance, Head of Treasury, VP Payments, CFO, CRO (Chief Risk Officer)

### Tech stack signals
- Core banking vendor, fraud platform, KYC/AML vendor, payment processor, ledger system
- Crypto/digital asset rails (signals modernization initiative)

### ICP signals (strong fit)
- New banking license announced
- Recent regulatory action (consent order, MRA) — drives compliance spend
- Partnership with a major bank or payment network
- Series funding tagged for "compliance" or "risk" infrastructure
- New Head of Risk or VP Compliance hired

### Disqualifying signals
- Active enforcement action with operational restrictions
- Pending acquisition by a larger institution
- Public statement of pulling back from a market segment

### Trade pubs
- Finextra, American Banker, PYMNTS, The Block (for crypto-adjacent), Bank Innovation

---

## Example pack — Healthcare / Pharma

### Operational metrics
- Revenue by therapeutic area, R&D spend, clinical trial pipeline depth, patent expiry exposure
- Hospital/IDN: bed count, occupancy rate, readmission rate, average length of stay
- Pharma: phase-by-phase trial milestones, FDA filing schedule, post-approval commercialization timeline

### Buyer personas
- VP Clinical Operations, Chief Medical Officer, Director of Quality, Head of Regulatory Affairs, VP Commercial Operations, CIO

### Tech stack signals
- EHR vendor (Epic, Cerner, Meditech), eClinical / EDC platform, RIM system, MDM platform
- Recent FDA inspection observations (Form 483) drive QA tooling spend

### ICP signals (strong fit)
- Phase III trial milestone or FDA filing in next 12 months
- Recent M&A activity (consolidation drives systems integration spend)
- New VP Clinical Ops or CMO hired
- Public mention of digital transformation initiative
- Recent Form 483 or warning letter (drives QA investment)

### Disqualifying signals
- Recent layoffs in clinical or commercial ops
- Drug withdrawal or trial failure (focuses spend elsewhere)
- Pending acquisition

### Trade pubs
- Fierce Pharma, Modern Healthcare, Endpoints News, STAT News, FDA Voice

---

## Example pack — Industrial / Supply Chain

### Operational metrics
- Throughput per facility, OEE (overall equipment effectiveness), capacity utilization
- Labor cost as % of COGS, overtime rate, headcount per shift
- Inventory turns, order accuracy rate, on-time-in-full rate

### Buyer personas
- VP Supply Chain, VP Operations, Director of Logistics, COO, Director of Continuous Improvement, CIO

### Tech stack signals
- ERP vendor, WMS / WES / TMS vendors, MES platform, planning system
- Recent capex announcements signal automation initiative

### ICP signals (strong fit)
- Announced capacity expansion or new facility
- Earnings mention of labor cost or throughput as a focus area
- New VP Supply Chain or new COO
- Recent segment leader move (poaching from a more-mature peer)
- Announced sustainability or productivity initiative

### Disqualifying signals
- Plant closures or restructuring announced
- Parent company push to divest segment
- Active union dispute that freezes capex

### Trade pubs
- Industry Week, Supply Chain Dive, Manufacturing Tomorrow, IndustryWeek, Reuters supply-chain desk

---

## Building your own vertical pack

If your target vertical isn't one of the four above, copy the structure of the closest example and replace the content. The skill consumes whatever six-dimension pack you provide — it doesn't care which vertical you're in.

Add your pack inline in `config/settings.md` under `TARGET_VERTICALS`, or contribute it back as a PR if you think other AEs would benefit.
