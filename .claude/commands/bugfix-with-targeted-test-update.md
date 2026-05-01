---
name: bugfix-with-targeted-test-update
description: Workflow command scaffold for bugfix-with-targeted-test-update in go-ethereum.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /bugfix-with-targeted-test-update

Use this workflow when working on **bugfix-with-targeted-test-update** in `go-ethereum`.

## Goal

Fixes a bug in a specific component and updates or adds a targeted test to verify the fix.

## Common Files

- `*/*.go`
- `*/*_test.go`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Modify the implementation file to fix the bug
- Modify or add a specific test file to cover the fixed behavior

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.