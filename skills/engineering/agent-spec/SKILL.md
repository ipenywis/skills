---
name: agent-spec
description: Turn vague coding-agent requests into tight, decision-ready implementation specs. Use when a developer asks to build, refactor, debug, migrate, or design software and the agent needs to clarify goal, scope, constraints, interfaces, edge cases, acceptance criteria, and checkpoints before implementation.
---

# Agent Spec

## Overview

Create specs that transfer the user's real understanding into a form a coding agent can execute. A good spec reduces assumptions, keeps the scope reviewable, and makes success measurable.

## Workflow

1. Discover repo truth first.
   - Inspect relevant files, package scripts, docs, routes, schemas, tests, and existing patterns.
   - Ask only for product intent or missing context that cannot be discovered.

2. Identify the real goal.
   - Convert task wording into the outcome or decision the work should enable.
   - Ask what would make the result obviously useful or obviously wrong.

3. Lock scope.
   - Define in scope and out of scope.
   - Prefer the smallest useful slice over a broad rewrite.
   - Name constraints such as compatibility, public APIs, design systems, data formats, runtime boundaries, or deployment limits.

4. Specify implementation shape.
   - Describe behavior, interfaces, inputs, outputs, data flow, and state changes.
   - Mention important files or modules only when needed to prevent ambiguity.
   - Include edge cases and failure modes that would affect user trust.

5. Define acceptance criteria.
   - State what must be true when the work is done.
   - Include verification signals that can be observed by tests, commands, logs, UI checks, or review.

6. Create checkpoints.
   - Break implementation into small slices that can be reviewed and verified independently.
   - Avoid one-shot waterfall plans for large work.

## Spec Template

```markdown
# Spec: <short title>

## Goal
<the real outcome, decision, or user value>

## Scope
- In:
- Out:

## Constraints
- <repo, runtime, API, compatibility, design, or safety constraints>

## Implementation Shape
- Behavior:
- Interfaces:
- Data flow:
- Edge cases:

## Acceptance Criteria
- <observable result>

## Checkpoints
1. <small slice>
2. <small slice>
3. <small slice>

## Assumptions
- <explicit assumption or default>
```

## Interview Prompts

- "What decision or user outcome should this work enable?"
- "What should stay unchanged?"
- "What would make this implementation unacceptable?"
- "Which checks would convince you the result is correct?"
- "Should this be a narrow fix, a durable abstraction, or a broader redesign?"

If the user already supplied a complete plan, do not re-interview. Confirm the plan in one short summary and proceed to approval or verification planning.

## Approval Boundary

When the spec leads to implementation, require explicit written approval before edits, installs, migrations, commits, deploys, deletes, or other mutating work.
