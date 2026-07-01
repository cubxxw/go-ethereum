---
name: feature-implementation-with-associated-tests
description: Workflow command scaffold for feature-implementation-with-associated-tests in go-ethereum.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /feature-implementation-with-associated-tests

Use this workflow when working on **feature-implementation-with-associated-tests** in `go-ethereum`.

## Goal

Implements a new feature or migration and adds corresponding test coverage for the new logic.

## Common Files

- `core/txpool/blobpool/limbo.go`
- `core/txpool/blobpool/limbo_test.go`
- `consensus/misc/eip4844/eip4844.go`
- `consensus/misc/eip4844/eip4844_test.go`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Implement the new feature or migration logic in the relevant source file(s).
- Add or update corresponding test file(s) to cover the new logic.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.