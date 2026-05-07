# Salesforce Logging Reference

## Activity (Task) Object Fields

| Field | What to Put There | Notes |
|-------|-------------------|-------|
| Subject | `Meeting Summary — [Account] — [Date]` | Scannable in list view |
| Status | `Completed` | Always |
| ActivityDate | Meeting date in YYYY-MM-DD | Not today's date |
| Description | Full CRM note body | 200-word max |
| Type | `Call`, `Meeting`, `Demo`, `Executive Briefing` | Pick the closest |
| WhoId | Primary contact from the meeting | Required for contact association |
| WhatId | Opportunity ID | Required to link to the deal |

## Opportunity Object Fields to Update After Meeting

After logging the activity, assess whether these Opportunity fields need updating:

| Field | Update If... |
|-------|--------------|
| StageName | Meeting advanced the deal to a new stage |
| NextStep | Always — update to specific next action with date |
| CloseDate | Timeline shifted based on meeting intel |
| Description | New strategic context worth preserving |
| Amount | Deal size estimate changed |
| Probability | Confidence shifted significantly |

## SFDC CLI Commands

Log activity:
```bash
sf data create record \
  --sobject Task \
  --values "Subject='Meeting Summary - [ACCOUNT] - [DATE]' Status='Completed' ActivityDate='[DATE]' Description='[ESCAPED_NOTE_BODY]' Type='Meeting'" \
  --target-org ~~salesforce-org
```

Update opportunity next step:
```bash
sf data update record \
  --sobject Opportunity \
  --record-id [OPP_ID] \
  --values "NextStep='[NEXT_STEP_TEXT]' CloseDate='[DATE]'" \
  --target-org ~~salesforce-org
```

Query contact ID for WhoId:
```bash
sf data query \
  --query "SELECT Id, FirstName, LastName FROM Contact WHERE AccountId = '[ACCOUNT_ID]' AND LastName LIKE '%[LAST_NAME]%'" \
  --target-org ~~salesforce-org
```

## Common Mistakes to Avoid
- Logging to Account instead of Opportunity — always associate to the deal
- Using today's date instead of the meeting date
- Writing notes in first person ("I said…") — write in third person or declarative ("AE presented…" or just state facts)
- Leaving NextStep blank or as a generic placeholder
- Over-writing — 200 words is a ceiling, not a goal
