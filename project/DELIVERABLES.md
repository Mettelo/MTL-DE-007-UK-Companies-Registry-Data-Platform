# Required Deliverables

## D1 — Discovery & API assessment
Document:
- Companies House source purpose;
- endpoints/resources used;
- authentication method;
- rate-limit constraints;
- cohort definition;
- JSON structures;
- pagination behaviour;
- source limitations.

Output:
`docs/01-discovery/`

## D2 — API & architecture design
Provide:
- system architecture;
- request flow;
- retry/throttling design;
- pagination logic;
- first-load vs incremental-refresh design;
- raw/staging/core/curated flow;
- security approach.

Output:
`docs/02-api-and-architecture/`

## D3 — Data model
Provide:
- ERD;
- table/model grain;
- identifiers;
- source-to-target mapping;
- handling of nested/list fields;
- filing identifiers and deduplication approach.

Output:
`docs/03-data-model/`

## D4 — Reusable API ingestion layer
Implement:
- secure authentication;
- API client;
- company profile ingestion;
- filing-history ingestion;
- cohort discovery/input handling;
- pagination;
- retries/error handling;
- rate-limit awareness;
- run metadata.

Output:
`src/api/` and `src/ingestion/`

## D5 — Incremental / rerunnable behaviour
Demonstrate:
- first full load;
- subsequent refresh;
- no uncontrolled duplication;
- profile updates/upserts;
- filing deduplication;
- run history.

## D6 — Transformation layer
Build:
- staging models;
- company core model;
- company SIC model;
- filing core model;
- curated analytical marts.

Output:
`models/`, `sql/` and/or `src/transformation/`

## D7 — Data-quality framework
Automate checks for:
- keys;
- completeness;
- referential integrity;
- duplicates;
- date validity;
- accepted values where appropriate;
- raw/modelled reconciliation.

Output:
`tests/` and `docs/04-pipeline-and-quality/`

## D8 — Analytics-ready outputs
Produce validated outputs supporting:
- company status;
- incorporation;
- SIC/sector;
- filing volume;
- filing recency;
- filing categories;
- completeness/coverage.

Output:
`analysis/` and `outputs/`

## D9 — Technical handover
Document:
- API registration;
- local setup;
- environment variables;
- installation;
- cohort configuration;
- run commands;
- test commands;
- refresh behaviour;
- troubleshooting;
- known limitations.

Output:
`docs/06-technical-handover/`

## D10 — Collaboration & submission
Complete:
- `CONTRIBUTIONS.md`;
- GitHub collaboration evidence;
- `submission/FINAL_SUBMISSION.md`;
- final tag.
