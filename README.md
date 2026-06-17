# CoderOne Skills

Portable skills for building better and faster with coding agents like Codex,
Claude Code, and other SKILL.md-compatible tools.

This collection is intentionally small. V1 focuses on one reusable engineering
loop:

1. Turn vague work into a tight spec.
2. Define verification before implementation.
3. Build inside a reusable agent environment.
4. Run the work in small checkpoints instead of one giant handoff.

## Install

After this repository is published on GitHub:

```bash
npx skills add CoderOne/skills
```

If the repository owner changes, replace `CoderOne` with the actual GitHub
owner.

## Skills

| Skill | Purpose |
| --- | --- |
| `agent-build-loop` | Orchestrate a full spec-to-verify coding-agent session. |
| `agent-spec` | Convert vague requests into decision-ready implementation specs. |
| `agent-verify` | Create and run verification plans for agent-built work. |
| `agent-environment` | Set up reusable project context, knowledge layout, and guardrails. |

## Layout

```text
skills/
  engineering/
    agent-build-loop/
      SKILL.md
    agent-spec/
      SKILL.md
    agent-verify/
      SKILL.md
    agent-environment/
      SKILL.md
```

## Positioning

These skills are inspired by the practical spec, verifier, and environment
structure used by strong agent-assisted developers. They are not official
skills from any model provider or public speaker.

## Development

Keep each skill portable and concise:

- Use only `name` and `description` in `SKILL.md` frontmatter.
- Keep workflow instructions in the skill body.
- Add resource folders only when a skill genuinely needs them.
- Require explicit written approval before edits, installs, migrations,
  commits, deploys, deletes, or other mutating work.
