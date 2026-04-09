# Amazon Q Rules

## Priority Hierarchy (highest to lowest)

1. **Data Verification** — Never provide unverified statistics or factual claims. Query actual sources before responding.
2. **Compliance Enforcement** — Follow established rules and processes. No shortcuts.
3. **Root Cause Analysis** — Use Ishikawa (fishbone) analysis for all problem diagnosis. Get user approval before implementing fixes.
4. **Data Integrity** — Never fabricate data. All visual outputs must use verified sources.
5. **Production Standards** — All code must meet production requirements (logging, error handling, type hints, config-driven).
6. **Code Quality** — Follow coding standards, testing requirements, and versioning guidelines.

## Core Behaviors

### Data Verification (Priority 1)
- Before making ANY statistical or factual claim, execute a verification query against actual data sources.
- Never rely on cached knowledge, assumptions, or hardcoded values.
- Use data sources in priority order: live pipeline output > source file queries > recent logs > config files.

### Compliance (Priority 2)
- Before any action: identify applicable rules, determine root cause vs symptom, check if data verification is needed.
- Every fix must be tested before claiming success — provide evidence, not assumptions.
- Complete all integration points before claiming a task is done.

### Root Cause Analysis (Priority 3)
- Use Ishikawa fishbone analysis: define the problem, examine categories (Manpower, Machine, Material, Method, Measurement), trace to root cause with evidence.
- Present analysis and proposed fix to user. Wait for explicit approval before implementing.
- Document analysis in `scripts/root_cause/` directory.

### Data Integrity (Priority 4)
- All visual outputs (charts, diagrams) must use verified data sources with a verification badge.
- All JOIN operations require pre/post record count validation.
- All exclusion/filtering logic must be validated — defining a requirement does not equal implementing it.

### Production Standards (Priority 5)
- Every script must have: logging with rotation, docstrings, error handling, type hints, config-driven values, input validation, progress tracking, resource cleanup, exit codes.
- No hardcoded paths or values — use configuration files.
- Create new file versions (v2, v3) for substantial fixes; maintain originals for backward compatibility.

### Code Quality (Priority 6)
- Follow PEP 8. Use Black, isort, Ruff for formatting.
- Use Pydantic V2 for validation, Loguru for logging, Pytest for testing (80%+ coverage).
- Include negative tests for all exclusion/filtering logic.
- Use type hints on all function signatures.

## Technology Stack
- **Data**: Polars, DuckDB, Pydantic V2
- **ML**: Scikit-learn, XGBoost/LightGBM, PyTorch/TensorFlow
- **Geo**: GeoPandas, Shapely, DeckGL
- **Infra**: Docker, FastAPI, Airflow/Prefect/Dagster
- **Quality**: Pytest, Ruff, Black, mypy

## Enforcement
All rules are enforced via Pydantic V2 validators, automated pipeline validation, code review, and fail-fast mechanisms. See `docs/` for detailed rule documentation.
