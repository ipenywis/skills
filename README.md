# CoderOne Skills

Portable skills for building better and faster with coding agents like Codex,
Claude Code, and other SKILL.md-compatible tools.

These skills are inspired by the workflow [Andrej Karpathy](https://x.com/karpathy) uses to build
quality software faster and more reliably with AI agents: write a precise spec,
define a verifier, and improve the environment the agent works inside.

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

This collection highlights the Karpathy-inspired workflow for high-quality
agent-assisted software development: make the goal explicit, turn it into a
tight spec, verify the result with real signals, and compound the environment
over time. These are not official skills from Karpathy, any model provider, or
any public speaker.

## Development

Keep each skill portable and concise:

- Use only `name` and `description` in `SKILL.md` frontmatter.
- Keep workflow instructions in the skill body.
- Add resource folders only when a skill genuinely needs them.
- Require explicit written approval before edits, installs, migrations,
  commits, deploys, deletes, or other mutating work.
