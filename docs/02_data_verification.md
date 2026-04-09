# Data Verification

## Priority: 1 (Highest)

All factual, statistical, and numerical claims MUST be verified against actual data sources before responding.

## Required Behavior

- **Query actual sources** before making any data claim (record counts, column counts, file sizes, schema details).
- **Never rely on** cached knowledge, script variables, assumptions, or partial file searches.
- **Include a verification badge** with every data claim.

## Data Source Priority (use highest available)

1. Live pipeline output / user-provided execution logs
2. Direct queries of actual source/output files
3. Latest timestamped log files
4. Configuration file settings

## Verification Badge Format

```
🔒 DATA VERIFIED: [specific claim]
SOURCE: [file/table queried]
QUERY: [command executed]
RESULT: [actual output]
```

## Violations

- Providing approximate or assumed statistics without verification
- Using lower-priority sources when higher-priority sources are available
- Claiming data "should contain" values without querying

See `09_enforcement.md` for enforcement pattern.
