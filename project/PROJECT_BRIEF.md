# Project Brief

## 1. Business context
Public company-register data is often consumed manually or through one-off scripts. A reusable data product needs reliable API access, repeatable extraction, controlled refreshes, stable schemas, quality checks and analytical models.

Assume the platform supports analysts or research teams that need a consistent view of a defined set of UK companies and their filing activity.

## 2. Problem statement
Build a production-style API pipeline that ingests Companies House public company data for a clearly defined cohort and turns it into validated, analytics-ready datasets.

The project must run locally and remain achievable without paid infrastructure.

## 3. Primary users
Assume the data product serves:
- business intelligence analysts;
- research teams;
- economic/sector analysts;
- data analysts;
- downstream data scientists.

## 4. Required source resources

### Company discovery / cohort
Use either:
- Companies House search endpoints; or
- a clearly documented input list of company numbers created from a reproducible discovery method.

### Company profile
Collect the current company profile for every company in scope.

### Filing history
Collect filing-history records for every company in scope.

## 5. Engineering requirements

### API client
Build a reusable API client that:
- reads credentials from environment variables;
- never hard-codes secrets;
- handles successful and failed HTTP responses;
- implements retries/backoff where appropriate;
- respects API request limits;
- logs endpoint, timestamp, status and relevant metadata.

### Raw layer
- Preserve API responses as raw JSON or equivalent immutable extracts.
- Capture retrieval timestamp.
- Record endpoint/resource metadata.
- Keep raw and transformed data separate.

### Pagination
Filing/search endpoints may return paginated results.

The pipeline must:
- detect pagination;
- request subsequent pages;
- stop correctly;
- avoid duplicate page ingestion;
- record counts.

### Incremental loading
Design refresh logic so a rerun does not require rebuilding everything unnecessarily.

At minimum:
- distinguish first load vs refresh;
- identify already-ingested records;
- upsert/update current company profiles;
- avoid duplicate filing records;
- record pipeline run timestamps.

### Staging
- Flatten nested JSON structures.
- Standardise names/types.
- Handle null/missing fields explicitly.
- Create stable identifiers.
- Document field exclusions.

### Core models
At minimum model:
- companies;
- company SIC classifications;
- filing history;
- pipeline/API run metadata.

### Curated marts
Create analytical tables supporting:
- company status;
- incorporation trends;
- SIC/sector analysis;
- filing activity;
- filing recency/frequency;
- data completeness.

### Data quality
Tests should cover:
- company-number uniqueness;
- required fields;
- duplicate filing records;
- valid dates;
- accepted status/category values where appropriate;
- referential integrity between companies and filings;
- raw vs staged/modelled reconciliation.

## 6. Minimum engineering standard
The solution must demonstrate:
- reusable API client design;
- secure credential handling;
- pagination;
- request throttling/rate-limit awareness;
- incremental/rerunnable ingestion;
- structured logging;
- modular code;
- automated tests;
- clear lineage;
- documented assumptions.

## 7. Out of scope
The core project does **not** require:
- scraping the Companies House website;
- ingesting the entire company register;
- paid cloud infrastructure;
- real-time streaming;
- machine learning;
- a production front-end;
- a large BI dashboard.

## 8. Success definition
A reviewer should be able to clone the repository, provide their own free Companies House API key, define/use the documented cohort, run the pipeline, execute tests and reproduce curated outputs without undocumented manual intervention.
