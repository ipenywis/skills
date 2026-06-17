---
name: c1-agent-environment
description: Set up reusable project context and guardrails for coding agents. Use when a developer wants better Codex, Claude Code, or other agent sessions through AGENTS.md or CLAUDE.md guidance, repo orientation, knowledge-base layout, repeated workflow skills, and always/ask/never safety rules.
---

# Agent Environment

## Overview

Create the workshop a coding agent operates inside: durable context, clear rules, reusable knowledge, and explicit safety boundaries. V1 uses Markdown instructions and templates only; do not add tool hooks or scripts unless the user asks for them.

## Workflow

1. Audit the current environment.
   - Look for `AGENTS.md`, `CLAUDE.md`, README files, architecture docs, package scripts, test commands, and project-specific conventions.
   - Identify missing context the agent repeatedly has to rediscover.

2. Create durable agent instructions.
   - Explain the repo purpose, important boundaries, common commands, validation expectations, and communication preferences.
   - Keep instructions short enough to be read every session.

3. Add knowledge-base structure when useful.
   - Use a simple folder for recurring context such as decisions, architecture notes, runbooks, examples, prompts, or domain references.
   - Prefer a few durable files over many tiny documents.

4. Identify repeatable skills.
   - If a workflow is repeated often, propose a small skill for it.
   - Include trigger conditions, required context, workflow steps, and validation.

5. Define always, ask first, and never rules.
   - Always: actions agents can perform autonomously.
   - Ask first: actions that are useful but need approval.
   - Never: actions that should not happen in this workspace.
   - For v1, express these as Markdown guardrails, not tool-level hooks.

6. Require approval before mutating work.
   - Any template created by this skill must say agents need explicit written approval before edits, installs, migrations, commits, deploys, deletes, or other mutating work.

## AGENTS.md or CLAUDE.md Template

```markdown
# Agent Instructions

## Project Context
- Purpose:
- Main entrypoints:
- Important boundaries:

## How To Work Here
- Read existing patterns before changing code.
- Prefer small, reviewable changes.
- Define verification before implementation.
- Report commands run and checks skipped.

## Common Commands
- Install:
- Test:
- Typecheck:
- Lint:
- Build:

## Guardrails
- Always:
- Ask first:
- Never:

## Approval Boundary
Do not edit files, install packages, run migrations, commit, deploy, delete data,
or perform other mutating work without explicit written approval.
```

## Knowledge Base Template

```text
agent-knowledge/
  decisions.md
  architecture.md
  commands.md
  workflows.md
  examples.md
```

Only create a knowledge base when the user wants persistent project context or the repo has enough recurring context to justify it.
