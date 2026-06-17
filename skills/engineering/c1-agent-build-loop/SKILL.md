---
name: c1-agent-build-loop
description: Guide a coding agent through a complete spec-to-verify implementation loop. Use when a developer asks an agent to build, refactor, fix, or plan non-trivial software work and wants better results through an interview, tight spec, explicit verification, small checkpoints, and a reusable agent environment.
---

# Agent Build Loop

## Overview

Run coding-agent work as a tight engineering loop: clarify the goal, write a small spec, define verification, get approval, implement in checkpoints, and verify before calling the work done.

Use this as the orchestrator. For deeper work, route to:

- `c1-agent-spec` for turning the request into a decision-ready spec.
- `c1-agent-verify` for the verification plan and completion checks.
- `c1-agent-environment` when the repo lacks reusable agent instructions, context, or guardrails.

## Workflow

1. Ground in the repo before asking questions.
   - Inspect entrypoints, existing patterns, tests, package scripts, and relevant docs.
   - Do not ask the user for facts that can be discovered from the workspace.

2. Interview for intent.
   - Clarify the real goal, user or audience, success criteria, constraints, and non-goals.
   - Prefer a few high-impact questions over a long survey.
   - If the user already gave a decision-complete plan, summarize it and move on.

3. Produce a tight spec.
   - Keep scope small enough to review.
   - Include intended behavior, key interfaces, data flow, edge cases, and acceptance criteria.
   - Name assumptions explicitly.

4. Define verification before implementation.
   - List the commands, tests, manual checks, screenshots, logs, or external signals that will prove the work.
   - If verification is impossible or incomplete, say so before starting.

5. Get explicit approval before mutating work.
   - Do not edit files, install packages, run migrations, commit, deploy, delete data, or perform other mutating work until the user clearly approves.
   - Read-only exploration is allowed unless the user says otherwise.

6. Implement in checkpoints.
   - Work in the smallest coherent slice.
   - After each slice, inspect the diff and run the relevant verification.
   - Update the user when direction, scope, or risk changes.

7. Finish with evidence.
   - Report what changed, what was verified, what could not be verified, and any follow-up risks.
   - Do not claim completion without running the agreed checks or clearly naming the gap.

## Useful Prompts

Use or adapt these prompts inside the session:

```text
Interview me until the goal, constraints, success criteria, and non-goals are clear. Then write a tight implementation spec.
```

```text
Before implementing, define the verification plan you will use to prove this works.
```

```text
Break this into the smallest useful checkpoint, complete that slice, verify it, then continue.
```
