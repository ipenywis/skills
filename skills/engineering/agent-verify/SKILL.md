---
name: agent-verify
description: Create and run verification plans for coding-agent work. Use when a developer needs tests, typecheck, lint, build checks, runtime checks, screenshots, logs, external signals, or second-agent critique to prove that an implementation, refactor, bug fix, migration, or generated artifact is correct.
---

# Agent Verify

## Overview

Make quality measurable before and after implementation. Do not trust confident output; define what good means, then collect evidence.

## Workflow

1. Define evaluation criteria up front.
   - Translate success into observable checks.
   - Include both functional behavior and regression risk.
   - For subjective work, define concrete review criteria.

2. Discover available verification.
   - Inspect package scripts, test directories, CI configs, docs, and existing examples.
   - Prefer existing local checks before inventing new ones.

3. Choose the smallest sufficient check set.
   - Fast focused tests for narrow changes.
   - Broader suites for shared behavior, public APIs, migrations, or cross-module changes.
   - Manual or visual checks for UI, docs, generated files, and workflow changes.

4. Pull external signal where possible.
   - Use real logs, deployed URLs, screenshots, database state, API responses, generated artifacts, or browser checks when they are relevant and safe.
   - Say when a check cannot be run locally.

5. Use second-agent critique for complex work.
   - Ask another capable model or reviewer to inspect the spec, diff, and verification evidence.
   - Keep the critique focused on bugs, missed edge cases, regressions, and unverified claims.

6. Report evidence honestly.
   - Separate checks that passed, checks that failed, and checks not run.
   - Do not call work complete if the agreed verification was skipped without explanation.

## Verification Menu

- Static: typecheck, lint, formatting check, dependency audit, schema validation.
- Unit: focused tests around changed behavior.
- Integration: API, database, workflow, generated artifact, or CLI checks.
- UI: browser smoke test, screenshot comparison, responsive viewport check, accessibility scan.
- Runtime: logs, health checks, deployed endpoint, job status, queue state.
- Review: diff inspection, second-agent critique, acceptance-criteria checklist.

## Verification Plan Template

```markdown
## Verification Plan

### Criteria
- <what good means>

### Checks
- `<command or manual check>` proves <claim>
- `<command or manual check>` proves <claim>

### External Signals
- <logs, screenshots, deployed endpoint, generated output, or none>

### Risk-Based Expansion
- Run broader checks if <condition>

### Completion Report
- Passed:
- Failed:
- Not run:
```

## Approval Boundary

Prefer read-only checks by default. Require explicit written approval before running checks that edit files, install packages, run migrations, deploy, delete data, commit changes, or otherwise mutate local or remote state.
