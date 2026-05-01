```markdown
# go-ethereum Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill provides a comprehensive guide to contributing to the `go-ethereum` codebase. It covers the project's coding conventions, common development workflows, and testing patterns. Whether you're implementing new features, updating API/client models, or fixing bugs, this guide will help you follow the established patterns and best practices in the repository.

## Coding Conventions

### File Naming
- Use **snake_case** for all file names.
  - Example: `state_trie.go`, `eth_client.go`, `block_header_test.go`

### Import Style
- Use **relative imports** within the project.
  - Example:
    ```go
    import (
        "github.com/ethereum/go-ethereum/trie"
        "github.com/ethereum/go-ethereum/ethclient"
    )
    ```

### Export Style
- Use **named exports** for functions, types, and variables that need to be accessed outside the package.
  - Example:
    ```go
    // Exported function
    func NewTrie() *Trie {
        // ...
    }

    // Unexported (internal) function
    func buildNode() *node {
        // ...
    }
    ```

### Commit Patterns
- Commit messages are **freeform** but often use prefixes such as `trie` or `ethclient`.
- Average commit message length: ~60 characters.
  - Example: `trie: optimize node caching for large state trees`

## Workflows

### Feature Implementation with Tests
**Trigger:** When adding a new feature or modifying an existing one, ensuring it is tested  
**Command:** `/feature-with-tests`

1. **Modify or add implementation files** to introduce or update functionality.
    - Example: Edit `trie/state_trie.go` to add a new method.
2. **Modify or add corresponding test files** to cover the new or changed functionality.
    - Example: Add tests in `trie/state_trie_test.go`.

#### Example
```go
// In trie/state_trie.go
func (t *Trie) NewFeature() {
    // implementation
}

// In trie/state_trie_test.go
func TestTrie_NewFeature(t *testing.T) {
    // test cases
}
```

---

### API or Client Model Update with Generated Code
**Trigger:** When updating API/client data structures, ensuring generated code and tests are up to date  
**Command:** `/update-client-model`

1. **Modify API/client implementation file** (e.g., `ethclient/client.go`).
2. **Regenerate code artifacts** using code generation tools.
    - Example: Run `go generate ./ethclient` to update `gen_*.go` files.
3. **Update or add related test files** to cover the changes.
    - Example: Edit `ethclient/client_test.go`.

#### Example
```go
// In ethclient/client.go
type NewAPIModel struct {
    // fields
}

// In ethclient/gen_api.go (generated)
...

// In ethclient/client_test.go
func TestNewAPIModel(t *testing.T) {
    // test cases
}
```

---

### Bugfix with Targeted Test Update
**Trigger:** When fixing a bug and ensuring the fix is covered by a test  
**Command:** `/bugfix-with-test`

1. **Modify the implementation file** to fix the bug.
    - Example: Fix logic in `trie/state_trie.go`.
2. **Modify or add a specific test file** to verify the fixed behavior.
    - Example: Add or update `trie/state_trie_test.go`.

#### Example
```go
// In trie/state_trie.go
func (t *Trie) FixedMethod() {
    // fixed implementation
}

// In trie/state_trie_test.go
func TestTrie_FixedMethod(t *testing.T) {
    // test for the bugfix
}
```

## Testing Patterns

- **Test files** use the pattern `*_test.go`.
- Tests are written using Go's standard `testing` package.
- Place tests in the same package as the code under test.
- Example test structure:
    ```go
    // In trie/state_trie_test.go
    import "testing"

    func TestTrie_SomeFeature(t *testing.T) {
        // Arrange
        // Act
        // Assert
    }
    ```

## Commands

| Command                | Purpose                                                         |
|------------------------|-----------------------------------------------------------------|
| /feature-with-tests    | Start a feature implementation with corresponding tests         |
| /update-client-model   | Update API/client models, regenerate code, and update tests     |
| /bugfix-with-test      | Fix a bug and add/update a targeted test                       |
```
