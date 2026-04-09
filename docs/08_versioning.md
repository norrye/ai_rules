# Versioning

## Priority: 7

## File Versioning

For substantial changes, create new file versions:
- `script.py` → `script_v2.py` (root cause fix)
- `script_v2.py` → `script_v3.py` (next substantial change)

### When to Version
| Change Type | Action |
|-------------|--------|
| Root cause fix | New file version |
| Architecture change | New file version |
| New feature | New file version |
| Major bug fix | New file version |
| Production upgrade | New file version |
| Typo / comment fix | Overwrite original |

## Semantic Versioning (Libraries/Modules)

Use `MAJOR.MINOR.PATCH` for shared libraries and APIs:
- **MAJOR**: Breaking changes
- **MINOR**: New features, backward compatible
- **PATCH**: Bug fixes, backward compatible

## Version Documentation

Each new version MUST include in its docstring:
```python
"""
Script Name - Version 2.0

CHANGES IN V2:
- Root cause fix: [description]
- Added Pydantic V2 validation
- Implemented production logging

Author: <author>
Date: YYYY-MM-DD
Version: 2.0 (Change description)
"""
```

## Legacy Code

- Create new versions with full compliance
- Maintain originals for backward compatibility
- Gradually migrate to compliant versions
