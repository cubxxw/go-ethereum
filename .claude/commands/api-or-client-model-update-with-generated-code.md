---
name: api-or-client-model-update-with-generated-code
description: Workflow command scaffold for api-or-client-model-update-with-generated-code in go-ethereum.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /api-or-client-model-update-with-generated-code

Use this workflow when working on **api-or-client-model-update-with-generated-code** in `go-ethereum`.

## Goal

Updates API or client models, including changes to generated code artifacts and associated tests.

## Common Files

- `ethclient/*.go`
- `ethclient/*_test.go`
- `ethclient/gen_*.go`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Modify API/client implementation file
- Regenerate code artifacts (e.g., using code generation tools)
- Update or add related test files

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.