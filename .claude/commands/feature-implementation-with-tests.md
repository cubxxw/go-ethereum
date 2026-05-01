---
name: feature-implementation-with-tests
description: Workflow command scaffold for feature-implementation-with-tests in go-ethereum.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /feature-implementation-with-tests

Use this workflow when working on **feature-implementation-with-tests** in `go-ethereum`.

## Goal

Implements a new feature or enhances an existing one, updating implementation files and corresponding tests.

## Common Files

- `*/*.go`
- `*/*_test.go`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Modify or add implementation files to introduce or update functionality
- Modify or add corresponding test files to cover the new or changed functionality

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.