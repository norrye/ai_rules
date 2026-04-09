# AI Rules for Amazon Q

A structured rule system for guiding Amazon Q behavior in data science and pipeline development projects.

## Quick Start

Amazon Q automatically loads rules from `.amazonq/rules/rules.md`. No configuration needed — just open this workspace in your IDE with the Amazon Q plugin installed.

## Structure

```
.amazonq/rules/
  rules.md              # Consolidated rules (auto-loaded by Amazon Q)

docs/
  01_rule_hierarchy.md          # Priority ordering for all rules
  02_data_verification.md       # Verify all data claims against actual sources
  03_compliance_enforcement.md  # Follow processes, test before claiming success
  04_root_cause_analysis.md     # Ishikawa fishbone analysis, user approval required
  05_data_integrity.md          # Visual outputs, JOINs, exclusions, negative testing
  06_production_standards.md    # Logging, error handling, config-driven code
  07_coding_standards.md        # PEP 8, tech stack, testing requirements
  08_versioning.md              # File versioning and semantic versioning
  09_enforcement.md             # Shared enforcement pattern for all rules
```

## Rule Priority

| Priority | Rule | Purpose |
|----------|------|---------|
| 1 | Data Verification | No unverified statistics or claims |
| 2 | Compliance | Follow processes, no shortcuts |
| 3 | Root Cause Analysis | Systematic diagnosis, user approval |
| 4 | Data Integrity | Verified visuals, validated JOINs |
| 5 | Production Standards | Production-ready code requirements |
| 6 | Code Quality | Standards, testing, tech stack |
| 7 | Versioning | File and semantic versioning |

## How It Works

- `.amazonq/rules/rules.md` is automatically included as context in every Amazon Q chat and inline chat request
- The `docs/` directory contains detailed documentation for each rule, used as human reference and for explicit `@docs` context inclusion
- Rules are enforced through Pydantic V2 validators, automated pipeline validation, and fail-fast mechanisms

## Customization

To adapt these rules for your project:
1. Edit `.amazonq/rules/rules.md` to adjust priorities and behaviors
2. Modify docs for detailed rule documentation
3. Add project-specific rules to `.amazonq/rules/` as additional `.md` files

## Technology Stack

See `docs/07_coding_standards.md` for the full technology stack. Primary tools: Polars, DuckDB, Pydantic V2, Loguru, Pytest.
