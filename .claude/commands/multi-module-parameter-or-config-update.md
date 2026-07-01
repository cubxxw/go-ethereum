---
name: multi-module-parameter-or-config-update
description: Workflow command scaffold for multi-module-parameter-or-config-update in go-ethereum.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /multi-module-parameter-or-config-update

Use this workflow when working on **multi-module-parameter-or-config-update** in `go-ethereum`.

## Goal

Updates configuration or parameter logic, often to support new forks, features, or protocol changes, and touches multiple modules and their tests.

## Common Files

- `params/config.go`
- `core/genesis.go`
- `cmd/geth/chaincmd.go`
- `cmd/geth/config.go`
- `cmd/geth/main.go`
- `cmd/utils/flags.go`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Update configuration or parameter files.
- Update related logic in core or consensus modules.
- Update or add tests to reflect the new configuration or parameter logic.
- Update CLI or utility code if necessary.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.