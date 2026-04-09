# Coding Standards

## Priority: 6

These standards define how all code must be written. The Role section in `.amazonq/rules/rules.md` provides the concise version; this doc has the full detail.

## Code Practices

- **Clarity**: PEP 8 compliance. Use Black, isort, Ruff for formatting. Include comments only where logic is non-obvious.
- **Efficiency**: Optimize for large datasets. Profile with cProfile or line_profiler to identify bottlenecks.
- **Modularity**: Reusable functions, classes, and modular APIs. Design interfaces for easy integration.
- **Type Hints**: All function signatures. Enforce with mypy.
- **Documentation**: Google/NumPy style docstrings for all functions and classes. Generate docs with Sphinx.
- **Error Handling**: Custom exception classes, retry with tenacity for transient errors in distributed systems.
- **Security**: Secrets for key management, encrypt sensitive data, prevent injection attacks (sqlparse for SQL), validate all external inputs.
- **Parameterization**: Config-driven via Hydra or OmegaConf. No hardcoded values.
- **Collaboration**: Code reviews via GitHub/GitLab/Bitbucket. Use PR templates.
- **Ethical AI**: Fair, transparent, accountable ML decisions. Monitor for bias with Evidently AI. Document decision-making logic.

## Testing

- **Framework**: Pytest with 80%+ coverage target
- **Property-based**: Use hypothesis for edge cases
- **Negative tests**: Required for all exclusion/filtering logic
- **Multi-version**: Use tox for cross-version testing

## Data Validation

- Use Pydantic V2, Great Expectations, or Pandera for data integrity
- Track data lineage through pipelines (Apache Atlas or DataHub)
- Validate all data sources meet expected formats and log outcomes

## Technology Stack

### Primary (Mandatory)

| Purpose           | Library     |
| ----------------- | ----------- |
| Data manipulation | Polars      |
| SQL analytics     | DuckDB      |
| Validation        | Pydantic V2 |
| Logging           | Loguru      |
| Testing           | Pytest      |
| Visualization     | DeckGL      |

### Secondary (As Needed)

| Purpose           | Library                                |
| ----------------- | -------------------------------------- |
| DataFrames        | Pandas / Fireducks                     |
| Numerical         | NumPy, SciPy                           |
| ML                | Scikit-learn, XGBoost, LightGBM        |
| Deep Learning     | PyTorch, TensorFlow (ONNX for interop) |
| Geospatial        | Duckdb, GeoPandas, Shapely, Geopy     |
| Similarity search | FAISS-cpu / FAISS-gpu                  |
| Visualization     | Matplotlib, Seaborn, Plotly, Bokeh     |
| Orchestration     | Airflow, Prefect, Dagster              |
| APIs              | FastAPI                                |
| Streaming         | Kafka, RabbitMQ                        |
| Containers        | Docker, Kubernetes                     |
| ML Ops            | MLflow, Evidently AI                   |
| CI/CD             | GitHub Actions, Jenkins                |
