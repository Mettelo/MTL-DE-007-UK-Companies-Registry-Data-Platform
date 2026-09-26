# Acceptance Criteria

## Source & scope
- Official Companies House API is used.
- Cohort definition is documented and reproducible.
- At least company profile and filing history are ingested.
- API limitations are acknowledged.

## Security
- No API keys/secrets are committed.
- Credentials are loaded from environment variables or equivalent.
- `.env.example` contains no real credentials.

## API engineering
- API client is reusable.
- HTTP errors are handled.
- Pagination works correctly.
- Request limiting/throttling is addressed.
- Retry/backoff behaviour is documented or implemented where appropriate.

## Reproducibility
- A reviewer can configure their own free API key.
- Setup/run instructions work.
- Paid services are not required.

## Incremental behaviour
- Initial and repeat runs are supported.
- Company profiles can be refreshed.
- Filing records are not duplicated on rerun.
- Pipeline runs are identifiable.

## Modelling
- Company table grain is clear.
- Filing table grain is clear.
- Company-to-filing relationships are preserved.
- SIC structures are modelled consistently.
- Curated outputs are analysis-ready.

## Data quality
- Company-number uniqueness is tested.
- Duplicate filings are detected/prevented.
- Referential integrity is tested.
- Missing/invalid data handling is explicit.
- Reconciliation checks exist.

## Engineering quality
- Code is modular.
- Logging exists.
- Errors are visible.
- Configuration is not hard-coded to one machine.
- Dependencies are reproducible.

## Analytical validation
- Curated data answers meaningful company/filing questions.
- Results trace back to the modelled data.
- No unsupported conclusions are presented.

## Documentation
- Architecture documented.
- API behaviour documented.
- Model documented.
- Run/test/refresh instructions complete.
- Limitations documented.

## Collaboration
- Team contributions are transparent.
- Git history demonstrates meaningful participation.
- PR workflow used where practical.

## Submission
- Final submission document complete.
- Reviewer has access.
- QA complete.
- Final tag `v1.0-mettelo-submission` created.
