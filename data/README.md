# Data Sources

## Official source
Companies House Developer Hub:

https://developer.company-information.service.gov.uk/

## API overview
https://developer.company-information.service.gov.uk/overview

## Get started
https://developer.company-information.service.gov.uk/get-started

## Authentication
https://developer.company-information.service.gov.uk/authentication

## Developer guidelines
https://developer.company-information.service.gov.uk/developer-guidelines

## Required resources
At minimum:
- company profile;
- filing history;
- search/discovery or a reproducibly defined company-number cohort.

## Cohort rule
Do not ingest the whole UK register.

Define a bounded cohort and document:
- selection method;
- search terms/SIC criteria where applicable;
- target size;
- inclusion/exclusion rules;
- date the cohort was created.

## Raw-response rule
Raw API responses should be treated as immutable snapshots.

Capture:
- endpoint;
- company number;
- request/retrieval timestamp;
- HTTP status;
- response metadata;
- pipeline run ID.

## Secrets
Never commit API keys.

Store keys locally through environment variables.

Recommended variable:

`COMPANIES_HOUSE_API_KEY`
