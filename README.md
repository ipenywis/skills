# Agentic Engineering Skills

Portable skills for building better and faster with coding agents like Codex,
Claude Code, and other SKILL.md-compatible tools.

These skills are inspired by the workflow [Andrej Karpathy](https://x.com/karpathy) uses to build
quality software faster and more reliably with AI agents: write a precise spec,
define a verifier, and improve the environment the agent works inside.

This collection is intentionally small. V1 focuses on one reusable engineering
loop plus a research-only ask mode:

1. Turn vague work into a tight spec.
2. Define verification before implementation.
3. Build inside a reusable agent environment.
4. Run the work in small checkpoints instead of one giant handoff.

## Install

After this repository is published on GitHub:

```bash
npx skills add ipenywis/skills
```

This installs the collection from
[`ipenywis/skills`](https://github.com/ipenywis/skills).

## Skills

| Skill | Purpose |
| --- | --- |
| `c1-agent-build-loop` | Orchestrate a full spec-to-verify coding-agent session. |
| `c1-agent-spec` | Convert vague requests into decision-ready implementation specs. |
| `c1-agent-verify` | Create and run verification plans for agent-built work. |
| `c1-agent-environment` | Set up reusable project context, knowledge layout, and guardrails. |
| `c1-ask` | Investigate, debug, and answer directly without mutating until explicit approval. |

## Layout

```text
skills/
  engineering/
    c1-agent-build-loop/
      SKILL.md
    c1-agent-spec/
      SKILL.md
    c1-agent-verify/
      SKILL.md
    c1-agent-environment/
      SKILL.md
    c1-ask/
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
