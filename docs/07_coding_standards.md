# Coding Standards

## Priority: 6

## Code Standards

- **Clarity**: PEP 8 compliance. Use Black, isort, Ruff for formatting.
- **Efficiency**: Profile with cProfile or line_profiler for bottlenecks.
- **Modularity**: Reusable functions, classes, and modular APIs.
- **Type Hints**: All function signatures. Enforce with mypy.
- **Documentation**: Google/NumPy style docstrings. Generate with Sphinx.
- **Error Handling**: Custom exceptions, retry with tenacity for transient errors.
- **Security**: Use secrets for key management, encrypt sensitive data, validate external inputs.
- **Parameterization**: Use Hydra or OmegaConf for complex config management.

## Testing

- **Framework**: Pytest with 80%+ coverage target
- **Property-based**: Use hypothesis for edge cases
- **Negative tests**: Required for all exclusion/filtering logic
- **Multi-version**: Use tox for cross-version testing

## Data Validation

- Use Pydantic V2, Great Expectations, or Pandera for data integrity
- Track data lineage through pipelines
- Validate all data sources meet expected formats

## Technology Stack

### Primary (Mandatory)
| Purpose | Library |
|---------|---------|
| Data manipulation | Polars |
| SQL analytics | DuckDB |
| Validation | Pydantic V2 |
| Logging | Loguru |
| Testing | Pytest |
| Visualization | DeckGL |

### Secondary (As Needed)
| Purpose | Library |
|---------|---------|
| DataFrames | Pandas / Fireducks |
| Numerical | NumPy, SciPy |
| ML | Scikit-learn, XGBoost, LightGBM |
| Deep Learning | PyTorch, TensorFlow (ONNX for interop) |
| Geospatial | GeoPandas, Shapely, Geopy |
| Similarity search | FAISS-cpu / FAISS-gpu |
| Visualization | Matplotlib, Seaborn, Plotly, Bokeh |
| Orchestration | Airflow, Prefect, Dagster |
| APIs | FastAPI |
| Streaming | Kafka, RabbitMQ |
| Containers | Docker, Kubernetes |
| ML Ops | MLflow, Evidently AI |
| CI/CD | GitHub Actions, Jenkins |
