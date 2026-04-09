# Data Integrity

## Priority: 4

Never fabricate data. All outputs must use verified sources. All transformations must be validated.

## Visual Output Integrity

Before creating any chart, diagram, or flowchart:
- Verify ALL data sources by querying actual files
- No assumptions — fail-fast if any source cannot be verified
- Include verification badge: `🔒 DATA INTEGRITY VERIFIED`
- Document which sources were queried

## JOIN Validation

All JOIN operations require:
1. **Pre-JOIN**: Record input table counts and unique key counts
2. **Key analysis**: Verify 1:1, 1:many, or many:many relationship
3. **Index creation**: Create indexes on join keys before execution
4. **Post-JOIN**: Verify output count matches expectation
5. **Fail-fast**: Block execution if unexpected record multiplication

```python
def validate_join(conn, left_table, right_table, join_key):
    left_count = conn.execute(f"SELECT COUNT(*) FROM {left_table}").fetchone()[0]
    right_unique = conn.execute(f"SELECT COUNT(DISTINCT {join_key}) FROM {right_table}").fetchone()[0]
    right_total = conn.execute(f"SELECT COUNT(*) FROM {right_table}").fetchone()[0]
    if right_total != right_unique:
        raise ValueError("Right table has duplicate keys — will multiply records")
    return left_count
```

## Exclusion Validation

All exclusion/filtering logic must be:
1. **Defined** — requirement clearly stated
2. **Implemented** — enforcement logic written
3. **Applied** — used in all relevant places
4. **Validated** — verified with both positive and negative tests

```python
# Defining a list does NOT equal implementing it
excluded = ['field_a', 'field_b']
output = [f for f in fields if f not in excluded]
for field in excluded:
    assert field not in output, f"Excluded field {field} found in output"
```

## Negative Testing

All exclusion and filtering logic requires:
- Positive tests: verify desired elements are present
- Negative tests: verify unwanted elements are absent
- Boundary tests: test edge cases
- Integration tests: end-to-end validation

See `09_enforcement.md` for enforcement pattern.
