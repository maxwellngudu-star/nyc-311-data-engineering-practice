# NYC 311 — Data Engineering Competency Challenge

## Purpose

This challenge evaluates practical Python data-engineering
skills using New York City's public 311 service-request data.

Expected effort: 2 hours.

## Dataset

NYC 311 Service Requests from 2020 to Present

https://data.cityofnewyork.us/d/erm2-nwe9

Use the public Socrata Open Data API.

## Task 1 — Data extraction

Develop a Python pipeline that:

1. Discovers and documents the API endpoint.
2. Inspects the available fields and data types.
3. Retrieves records where:
   - complaint_type = 'Noise - Residential'
   - created_date >= 2025-01-01
   - created_date < 2025-02-01
4. Applies filtering on the API server.
5. Implements pagination to retrieve all matching records.
6. Handles timeouts, failed requests and retries with back-off.
7. Uses Python logging instead of print statements.
8. Saves the extracted dataset locally.
9. Retrieves the corresponding API-reported record count.

Do not manually download the complete dataset.

## Task 2 — Cleaning and transformation

Using the extracted records:

1. Inspect the required columns and their types.
2. Identify duplicate service-request identifiers.
3. Examine missing or inconsistent borough information.
4. Standardise valid borough names.
5. Document any excluded or unresolved records.
6. Count service requests per borough.
7. Sort results from highest to lowest count.
8. Export a CSV containing:
   - borough
   - report_count

## Task 3 — Validation

Implement checks to verify that:

1. All expected fields exist.
2. Request identifiers are unique.
3. Extracted records match the API-reported count.
4. Aggregated records plus documented exclusions
   reconcile with the extracted total.
5. Report counts are non-negative integers.
6. The pipeline stops with a useful error if validation fails.

## Task 4 — Reproducibility

The solution must:

1. Use Python scripts (.py), not only notebooks.
2. Follow PEP 8 conventions.
3. Organise code into understandable functions.
4. Include an appropriate dependency file.
5. Include a one-command pipeline execution script.
6. Generate meaningful logs.
7. Run without manual data downloads or editing file paths.
8. Document setup and execution instructions.

## Deliverables

- Python source code
- Dependency specification
- Pipeline execution script
- Final borough-level CSV
- Validation results
- README documentation
- Meaningful Git commits

Generated raw datasets should not be committed to Git.

## Evaluation criteria

| Category | Marks |
|---|---:|
| API extraction and pagination | 25 |
| Code organisation and readability | 15 |
| Data cleaning and transformation | 20 |
| Validation and data integrity | 20 |
| Logging and error handling | 10 |
| Reproducibility and documentation | 10 |
| **Total** | **100** |

## Rules

- Use publicly available data only.
- Do not manually modify extracted records.
- Document all cleaning decisions.
- Do not hardcode final analytical results.
- Ensure the pipeline can be executed from a fresh clone.
- Be prepared to explain every implementation decision.

This is an independent practice assessment.
It is not affiliated with NYC Open Data or UCT.
