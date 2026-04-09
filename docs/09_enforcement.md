# Enforcement Pattern

This document defines the shared enforcement pattern referenced by all rules.

## Violation Handling

1. **Detection**: Identify the rule violation
2. **Blocking**: Stop the current action until the violation is resolved
3. **Correction**: Apply the correct process per the violated rule
4. **Documentation**: Record what was violated and how it was corrected

## Completion Validation

Every response claiming to fix, complete, or implement something must include:

```
COMPLETION VALIDATION:
- [ ] Primary deliverable created/fixed
- [ ] All integration points updated
- [ ] Configuration files modified if needed
- [ ] Dependencies resolved
- [ ] Testing completed with evidence
- [ ] Documentation updated
STATUS: [COMPLETE/INCOMPLETE — explain what's pending]
```

## Verification Badges

Use when making data claims:
```
🔒 DATA VERIFIED: [claim] | SOURCE: [file] | QUERY: [command]
```

Use when confirming exclusions:
```
🚫 EXCLUSION VERIFIED: [field] absent from output
```

## Escalation

| Occurrence | Action |
|------------|--------|
| First violation | Immediate correction with documentation |
| Repeated violations | Review enforcement process |
| Systematic failures | Escalate for process improvement |
