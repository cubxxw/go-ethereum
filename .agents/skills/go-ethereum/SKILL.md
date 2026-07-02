```markdown
# go-ethereum Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches the core development patterns and conventions used in the `go-ethereum` repository, a prominent Go-based implementation of the Ethereum protocol. You'll learn about file organization, import/export styles, commit conventions, and how to structure and run tests, as well as common workflows for contributing to the codebase.

## Coding Conventions

### File Naming
- Use **snake_case** for file names.
  - Example: `block_chain.go`, `transaction_pool.go`

### Import Style
- Use **relative imports** for internal packages.
  - Example:
    ```go
    import (
        "github.com/ethereum/go-ethereum/core"
        "./utils"
    )
    ```

### Export Style
- Use **named exports** for functions, types, and variables that need to be accessed outside the package.
  - Example:
    ```go
    // Exported function
    func StartNode() {
        // ...
    }

    // Unexported (internal) function
    func startNodeInternal() {
        // ...
    }
    ```

### Commit Patterns
- Commits use **freeform messages** with no strict prefix, averaging 55 characters.
  - Example:  
    ```
    Fix block validation logic for uncle inclusion
    ```

## Workflows

### Code Contribution
**Trigger:** When adding new features, fixing bugs, or improving documentation  
**Command:** `/contribute`

1. Fork and clone the repository.
2. Create a new branch for your changes.
3. Follow the coding conventions for file naming, imports, and exports.
4. Write or update tests as needed.
5. Commit your changes with a clear, concise message.
6. Push your branch and open a pull request.

### Running Tests
**Trigger:** When verifying code correctness or before submitting a pull request  
**Command:** `/test`

1. Identify test files (pattern: `*.test.*`).
2. Run tests using Go's testing tool:
    ```sh
    go test ./...
    ```
3. Review test output for failures and fix any issues.

### Code Review Preparation
**Trigger:** Before submitting code for review  
**Command:** `/prepare-review`

1. Ensure all code follows the documented conventions.
2. Run all tests and confirm they pass.
3. Rebase your branch onto the latest main branch.
4. Double-check commit messages for clarity.

## Testing Patterns

- Test files follow the pattern `*.test.*`.
- The testing framework is not explicitly specified, but Go's built-in testing is likely used.
- Example test file: `block_chain.test.go`
- Example test function:
    ```go
    func TestBlockValidation(t *testing.T) {
        // test logic here
    }
    ```

## Commands
| Command           | Purpose                                     |
|-------------------|---------------------------------------------|
| /contribute       | Start the code contribution workflow        |
| /test             | Run all tests in the repository             |
| /prepare-review   | Prepare your code for review and submission |
```
