```markdown
# go-ethereum Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches you the core development patterns, coding conventions, and workflows used in the `go-ethereum` repository, a prominent Go-based implementation of the Ethereum protocol. You'll learn how to structure code, manage imports and exports, write and organize tests, and follow the repository's commit and workflow practices.

## Coding Conventions

### File Naming
- Use **snake_case** for all file names.
  - Example: `block_chain.go`, `transaction_pool.go`

### Import Style
- Use **relative imports** within the project.
  - Example:
    ```go
    import (
        "github.com/ethereum/go-ethereum/core"
        "github.com/ethereum/go-ethereum/common"
    )
    ```

### Export Style
- Use **named exports** for functions, types, and variables that should be accessible outside the package.
  - Example:
    ```go
    // Exported function
    func NewBlockChain() *BlockChain {
        // ...
    }

    // Unexported function
    func calculateDifficulty() int {
        // ...
    }
    ```

### Commit Patterns
- Commit messages are freeform, often prefixed with the affected component (e.g., `core:`).
- Average commit message length is about 55 characters.
  - Example: `core: fix block validation edge case`

## Workflows

### Code Contribution
**Trigger:** When adding new features, fixing bugs, or making improvements  
**Command:** `/contribute`

1. Fork and clone the repository.
2. Create a new branch for your changes.
3. Follow coding conventions for file naming, imports, and exports.
4. Write or update tests as needed.
5. Commit changes with a descriptive message, optionally prefixed by component.
6. Push your branch and submit a pull request.

### Running Tests
**Trigger:** When validating code changes or before submitting a pull request  
**Command:** `/test`

1. Identify test files (pattern: `*.test.*`).
2. Run tests using Go's testing tools:
    ```sh
    go test ./...
    ```
3. Review output and fix any failing tests.

### Reviewing Commits
**Trigger:** When preparing commits for review or submission  
**Command:** `/review-commits`

1. Ensure commit messages are clear and, if possible, prefixed with the relevant component.
2. Keep commit messages concise (around 55 characters).
3. Squash or rebase commits if necessary for clarity.

## Testing Patterns

- Test files follow the pattern `*.test.*` (e.g., `block_chain.test.go`).
- Tests are written using Go's standard testing package.
  - Example:
    ```go
    import "testing"

    func TestBlockChain_AddBlock(t *testing.T) {
        // Test logic here
    }
    ```
- Place tests alongside the code they verify.

## Commands
| Command         | Purpose                                      |
|-----------------|----------------------------------------------|
| /contribute     | Steps for contributing code                  |
| /test           | How to run the test suite                    |
| /review-commits | Guidelines for preparing and reviewing commits|
```
