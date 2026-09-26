# MTL-DE-007 — UK Companies Registry Data Platform

## Project title
**UK Companies Registry Data Platform — Company Profiles, Filing Activity & Business Intelligence**

## Project type
Data Engineering · Team project · Production-style portfolio project

## Challenge
Companies House exposes live public information about UK-registered companies through an official REST API. The data is valuable but arrives as nested JSON across multiple endpoints, is subject to request limits, and requires careful handling of pagination, incremental ingestion, deduplication, changing company records and API errors.

Your team will build a reproducible data platform that collects a defined cohort of UK companies and converts the API responses into reliable analytics-ready datasets.

## Official data source
Companies House Developer Hub:

https://developer.company-information.service.gov.uk/

API overview:

https://developer.company-information.service.gov.uk/overview

Get started / API access:

https://developer.company-information.service.gov.uk/get-started

Authentication:

https://developer.company-information.service.gov.uk/authentication

Developer guidelines / rate limits:

https://developer.company-information.service.gov.uk/developer-guidelines

## Cost requirement
**The complete project must be achievable at £0.**

No paid cloud account, database or deployment service is required.

Recommended free stack:
- Python
- DuckDB
- SQL
- dbt Core
- Git
- GitHub
- GitHub Actions free allowance for public repositories

A free Companies House developer account/API key may be used.

## Project scope
Do **not** attempt to ingest the full UK company register.

Each team must define and document a manageable company cohort, for example:
- selected SIC codes;
- a defined search term/category;
- a documented list of target companies;
- a bounded sample across selected sectors.

The cohort must be large enough to demonstrate pagination, repeated API calls, incremental loading and data-quality controls without creating unnecessary API load.

## Core objective
Build a reproducible API ingestion and transformation platform that:

1. authenticates securely with Companies House;
2. discovers or loads a defined company cohort;
3. collects company profile data;
4. collects filing-history data;
5. stores raw JSON responses;
6. handles pagination and request limits;
7. supports incremental refreshes;
8. deduplicates repeated records;
9. transforms nested API responses into relational models;
10. creates curated analytical tables;
11. logs pipeline runs and failures;
12. documents lineage, assumptions and limitations.

## Required engineering flow

```
Companies House REST API
        ↓
Authentication / request client
        ↓
Raw JSON ingestion
        ↓
Metadata + run logging
        ↓
Staging / flattening
        ↓
Core company + filing models
        ↓
Curated analytical marts
        ↓
QA + analytical outputs
```

## Minimum source domains
The team must use at least:

- **Company profile**
- **Company search/discovery or an explicitly documented input cohort**
- **Filing history**

Optional extensions:
- officers;
- persons with significant control;
- registered-office information;
- charges.

Do not expand scope until the required pipeline is complete.

## Expected analytical outputs
The curated layer should make it straightforward to answer questions such as:
- What is the status distribution of companies in the selected cohort?
- How does incorporation activity vary over time?
- Which SIC codes are most common?
- How frequently do companies file documents?
- Which filing categories occur most often?
- Which companies show recent filing activity?
- What proportion of the cohort is active, dissolved or otherwise classified?
- How complete are key company attributes across the cohort?

These are validation/use-case questions, not a requirement to build a large BI dashboard.

## Team submission model
Each project team creates **its own GitHub repository**.

Recommended naming:

`MTL-DE-007-<team-name>`

The Mettelo repository is the project specification only.

Each team must:
1. create its own repository;
2. invite the designated Mettelo reviewer/collaborator;
3. follow `project/REPOSITORY_STRUCTURE.md`;
4. use issues/branches/commits/pull requests as evidence of collaboration;
5. never commit API keys or secrets;
6. complete `submission/FINAL_SUBMISSION.md`;
7. complete final QA;
8. tag the accepted version `v1.0-mettelo-submission`;
9. submit the repository URL.

## Project documents
- [Project brief](project/PROJECT_BRIEF.md)
- [API source & handling](data/README.md)
- [Mandatory repository structure](project/REPOSITORY_STRUCTURE.md)
- [Deliverables](project/DELIVERABLES.md)
- [Acceptance criteria](project/ACCEPTANCE_CRITERIA.md)
- [Team roles](project/TEAM_ROLES.md)
- [Contribution rules](CONTRIBUTIONS.md)
- [Final submission template](submission/FINAL_SUBMISSION.md)

---
**Mettelo — Built for What’s Next**
