# agent-handoff

Crash-safe continuation between AI coding agents.

## Why

AI coding sessions often end with incomplete edits, partial context, and unclear next steps.
`agent-handoff` captures repository, task, and execution state so another agent can continue safely.

## Features

- Capture git-aware workspace state
- Record task progress and next action
- Detect partial or risky edits
- Export a canonical handoff bundle
- Render continuation summaries for target agents

## Example

```bash
agent-handoff capture --source claude-code --repo . --out handoff.bundle.json
agent-handoff inspect handoff.bundle.json
agent-handoff validate handoff.bundle.json
agent-handoff render --input handoff.bundle.json --target codex --format markdown --out handoff.summary.md
