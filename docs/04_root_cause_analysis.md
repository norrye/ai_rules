# Root Cause Analysis & Approval

## Priority: 3

All problem diagnosis must use systematic Ishikawa (fishbone) analysis. Fixes require user approval before implementation.

## Analysis Process

1. **Define the problem** clearly as the "fish head"
2. **Examine categories** systematically (choose appropriate framework below)
3. **Verify actual data** for each potential cause — no assumptions
4. **Trace to root cause** using evidence
5. **Present analysis** to user and ask for approval
6. **Implement fix** only after explicit user confirmation

## Category Frameworks

### 5 Ms (Technical Issues)
- **Manpower**: Human factors, knowledge gaps, assumptions
- **Machine**: Systems, tools, environment, infrastructure
- **Material**: Data sources, files, inputs, configuration
- **Method**: Processes, procedures, workflows
- **Measurement**: Validation, monitoring, verification

### 4 Ss (Service Issues)
- **Surroundings**: Environment, context, conditions
- **Suppliers**: External dependencies, inputs
- **Systems**: Processes, tools, infrastructure
- **Skills**: Knowledge, capabilities, assumptions

## Approval Requirement

After every root cause analysis, ask:

> "Do you agree with this root cause analysis and the proposed fix? Should I proceed with implementing the changes?"

**No implementation until user responds with clear approval.**

## Documentation

Save each analysis to: `scripts/root_cause/YYYYMMDD_problem_description.md`

## Fix Requirements

- Address root causes, not symptoms
- Create new file versions (v2, v3) for substantial fixes
- Add validation to prevent recurrence
- Update documentation

See `09_enforcement.md` for enforcement pattern.
