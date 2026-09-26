# Mandatory Team Repository Structure

Each team must create a separate repository named:

`MTL-DE-007-<team-name>`

Minimum structure:

```
MTL-DE-007-<team-name>/
│
├── README.md
├── CONTRIBUTIONS.md
├── requirements.txt
├── .gitignore
├── .env.example
│
├── config/
│   └── README.md
│
├── data/
│   ├── raw/
│   │   └── README.md
│   ├── reference/
│   │   └── README.md
│   └── metadata/
│       └── README.md
│
├── docs/
│   ├── 01-discovery/
│   │   └── README.md
│   ├── 02-api-and-architecture/
│   │   └── README.md
│   ├── 03-data-model/
│   │   └── README.md
│   ├── 04-pipeline-and-quality/
│   │   └── README.md
│   ├── 05-analysis-and-output/
│   │   └── README.md
│   └── 06-technical-handover/
│       └── README.md
│
├── src/
│   ├── api/
│   ├── ingestion/
│   ├── validation/
│   ├── transformation/
│   └── utils/
│
├── sql/
├── models/
├── tests/
├── notebooks/
├── analysis/
├── outputs/
│
└── submission/
    └── FINAL_SUBMISSION.md
```

## Repository rules

### Secrets
API keys must never be committed.

Use:
- environment variables;
- local `.env` ignored by Git;
- `.env.example` containing names only.

### Raw API responses
Do not commit large volumes of raw JSON.

The repository should contain:
- code to reproduce them;
- metadata;
- optionally very small anonymised/sample response fixtures for testing.

### Collaboration evidence
Use:
- GitHub issues;
- feature branches;
- meaningful commits;
- pull requests;
- peer review.

## Final version
After QA and Mettelo review, create:

`v1.0-mettelo-submission`
