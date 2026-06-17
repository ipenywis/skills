---
name: c1-ask
description: CoderOne Ask research-only mode. Use when the user says c1-ask, $c1-ask, coderone-ask, ask mode, research only, investigate only, debug/explain without changing, or otherwise explicitly asks to diagnose, investigate, answer, or recommend actions before making changes. Agents must research, inspect, debug, and answer directly while avoiding implementation or mutation until the user gives clear written approval for a specific action.
---

# C1 Ask

C1 Ask is the short name for CoderOne Ask. Use it to investigate and answer the user's problem, question, or concern before taking action.

## Core Rules

- Treat the turn as research, debugging, investigation, and direct answering only.
- Use non-mutating investigation: read files, search code, inspect configs, review logs, run safe diagnostics, and gather evidence.
- Do not edit files, apply patches, write repo artifacts, run rewriting formatters, install dependencies, start migrations, commit, deploy, delete data, change external systems, or otherwise mutate state without explicit written approval.
- Require approval that is clear, written, and action-specific. Accept approval such as "Implement the fix you described" or "Yes, edit those files." Do not treat vague replies like "ok", "sounds good", "sure", or "yes" as sufficient unless they clearly authorize the concrete mutation.
- If the user asks for implementation while C1 Ask is active but has not explicitly approved a concrete action, explain what would be changed and ask for written approval before doing it.
- After approval, do only the approved action and keep the scope tight.

## Answer Style

- Answer the user's actual question directly; do not default to a long implementation plan.
- Explain what is happening, why it is happening, and the evidence for the conclusion.
- Cite specific files, commands, logs, errors, or observations when available.
- State the recommended action or next few actions in plain language.
- Call out uncertainty and what additional investigation would reduce it.
- End by making the approval boundary explicit when mutation would be the next step.

## Safety Boundary

If an action could alter repo-tracked files, local configuration, installed packages, databases, services, accounts, deployments, generated source, or user-visible state, treat it as mutating. Do not perform it until the user explicitly approves that action in writing.
