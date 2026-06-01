```markdown
# go-ethereum Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches the core development patterns and conventions used in the `go-ethereum` repository, a prominent Go codebase implementing the Ethereum protocol. You'll learn how to structure files, write imports and exports, and follow commit and testing practices observed in this project.

## Coding Conventions

### File Naming
- Use **snake_case** for file names.
  - Example: `block_chain.go`, `transaction_pool.go`

### Import Style
- Use **relative imports** for internal packages.
  - Example:
    ```go
    import (
        "fmt"
        "github.com/ethereum/go-ethereum/common"
        "github.com/ethereum/go-ethereum/core"
    )
    ```

### Export Style
- Use **named exports**: Exported functions, types, and variables start with an uppercase letter.
  - Example:
    ```go
    // Exported type
    type BlockChain struct {}

    // Exported function
    func NewBlockChain() *BlockChain {
        // ...
    }
    ```

### Commit Patterns
- Commit messages are **freeform** with some use of prefixes like `internal`, `node`.
- Example:
  ```
  internal: optimize block propagation logic
  node: add support for custom genesis files
  ```

## Workflows

### Adding a New Feature
**Trigger:** When introducing new functionality to the codebase  
**Command:** `/add-feature`

1. Create a new file using snake_case naming.
2. Implement the feature with exported types/functions as needed.
3. Use relative imports for internal packages.
4. Write or update tests in corresponding `*_test.go` files.
5. Commit changes with a descriptive message, optionally using a prefix (e.g., `internal:`, `node:`).

### Fixing a Bug
**Trigger:** When resolving a bug or issue  
**Command:** `/fix-bug`

1. Locate the relevant file(s) using snake_case naming.
2. Apply the fix, ensuring exported functions/types are updated if needed.
3. Update or add tests to cover the bug fix.
4. Commit with a descriptive message, optionally using a prefix.

### Writing and Running Tests
**Trigger:** When adding or updating tests  
**Command:** `/run-tests`

1. Write tests in files matching the pattern `*_test.go`.
2. Use Go's standard testing package (`testing`).
   ```go
   import "testing"

   func TestNewBlockChain(t *testing.T) {
       // test logic
   }
   ```
3. Run tests using Go tooling:
   ```
   go test ./...
   ```

## Testing Patterns

- Test files use the `*_test.go` naming convention.
- The testing framework is not explicitly detected, but Go's standard `testing` package is implied.
- Example test:
  ```go
  import "testing"

  func TestTransactionPool(t *testing.T) {
      // Test logic here
  }
  ```

## Commands
| Command      | Purpose                                  |
|--------------|------------------------------------------|
| /add-feature | Scaffold and commit a new feature        |
| /fix-bug     | Apply and commit a bug fix               |
| /run-tests   | Run all tests in the repository          |
```
