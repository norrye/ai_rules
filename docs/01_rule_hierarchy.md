# Rule Hierarchy and Precedence

## Priority Order (Highest to Lowest)

| Priority | Rule | Doc |
|----------|------|-----|
| 1 | Data Verification | `02_data_verification.md` |
| 2 | Compliance Enforcement | `03_compliance_enforcement.md` |
| 3 | Root Cause Analysis & Approval | `04_root_cause_analysis.md` |
| 4 | Data Integrity (Visual, JOINs, Exclusions) | `05_data_integrity.md` |
| 5 | Production Standards | `06_production_standards.md` |
| 6 | Code Quality & Testing | `07_coding_standards.md` |
| 7 | Versioning | `08_versioning.md` |

## Conflict Resolution

When rules conflict:
- Data verification always takes precedence
- Production requirements override convenience
- Root cause fixes preferred over quick patches
- Quality standards maintained unless production-critical

## Enforcement

All rules are enforced through:
- Pydantic V2 validators
- Automated validation at pipeline step boundaries
- Code review for rule compliance
- Fail-fast mechanisms to prevent violations

See `09_enforcement.md` for the shared enforcement pattern used across all rules.
