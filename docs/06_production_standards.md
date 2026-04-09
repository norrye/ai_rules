# Production Standards

## Priority: 5

Every script MUST be production-ready with these requirements.

## Mandatory Requirements

1. **Logging** — Rotating file handlers with structured output (Loguru)
2. **Docstrings** — Google/NumPy style for all functions and classes
3. **Error Handling** — Try/catch with graceful failures and custom exceptions
4. **Type Hints** — All function parameters and return values
5. **Config-Driven** — Use config files, no hardcoded paths or values
6. **Input Validation** — Validate all inputs before processing (Pydantic V2)
7. **Progress Tracking** — Monitor long-running operations
8. **Resource Cleanup** — Properly close connections and files
9. **Exit Codes** — 0 for success, 1+ for failure
10. **Structured Output** — Professional logging and user feedback

## Template

```python
#!/usr/bin/env python3
"""
Script Name - Version X.X

Description of what the script does.

Author: <author>
Date: YYYY-MM-DD
Version: X.X (Change description)
"""
import sys
from loguru import logger
from pydantic import BaseModel

def setup_logging() -> None:
    logger.add("logs/script_name.log", rotation="10 MB", retention="7 days", level="INFO")

def main() -> None:
    try:
        setup_logging()
        # Implementation
        logger.info("✅ Process completed successfully")
        sys.exit(0)
    except Exception as e:
        logger.error(f"❌ Process failed: {e}")
        sys.exit(1)

if __name__ == "__main__":
    main()
```

## Prohibited Practices

```python
output_file = "/data/processed/output.parquet"  # ❌ Hardcoded path
output_file = config['output']['path']           # ✅ Config-driven
```

See `09_enforcement.md` for enforcement pattern.
