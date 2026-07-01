```markdown
# go-ethereum Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches you the core development patterns, coding conventions, and common workflows used in the `go-ethereum` (Geth) codebase. You'll learn how to implement new features with proper test coverage, update protocol parameters across multiple modules, and follow the project's conventions for file structure, naming, and code organization.

## Coding Conventions

### File Naming
- **CamelCase** is used for file names.
  - Example: `genesisAlloc.go`, `chaincmd.go`

### Import Style
- **Relative imports** are used within the project.
  - Example:
    ```go
    import (
        "github.com/ethereum/go-ethereum/core"
        "github.com/ethereum/go-ethereum/params"
    )
    ```

### Export Style
- **Named exports** are used for functions, types, and variables intended for use outside their package.
  - Example:
    ```go
    // Exported function
    func NewTxPool() *TxPool {
        // ...
    }

    // Unexported function
    func newTxPoolInternal() *TxPool {
        // ...
    }
    ```

### Commit Patterns
- **Freeform commit messages** with optional prefixes (`core`, `params`, `cmd`).
- Average commit message length: ~59 characters.
  - Example: `core, params: implement EIP-4844 blobpool logic`

## Workflows

### Feature Implementation with Associated Tests
**Trigger:** When adding a new feature or migration and ensuring it is properly tested  
**Command:** `/new-feature-with-tests`

1. **Implement the new feature or migration logic** in the relevant source file(s).
   - Example: Add logic in `core/txpool/blobpool/limbo.go`
2. **Add or update corresponding test file(s)** to cover the new logic.
   - Example: Add tests in `core/txpool/blobpool/limbo_test.go`

**Example:**
```go
// core/txpool/blobpool/limbo.go
func (l *LimboPool) AddBlob(blob Blob) error {
    // Implementation logic
}

// core/txpool/blobpool/limbo_test.go
func TestAddBlob(t *testing.T) {
    // Test for AddBlob
}
```

### Multi-Module Parameter or Config Update
**Trigger:** When changing protocol parameters, adding fork support, or updating global configuration affecting several components  
**Command:** `/update-params`

1. **Update configuration or parameter files.**
   - Example: Modify `params/config.go`
2. **Update related logic in core or consensus modules.**
   - Example: Edit `core/genesis.go`, `consensus/misc/eip4844/eip4844.go`
3. **Update or add tests** to reflect the new configuration or parameter logic.
   - Example: Update `core/eip8246_test.go`, `core/vm/eip8037_test.go`
4. **Update CLI or utility code if necessary.**
   - Example: Edit `cmd/geth/chaincmd.go`, `cmd/utils/flags.go`

**Example:**
```go
// params/config.go
var NewForkBlock = big.NewInt(12345678)

// core/genesis.go
if block.Number.Cmp(params.NewForkBlock) >= 0 {
    // Apply new fork rules
}

// core/eip8246_test.go
func TestNewForkBlock(t *testing.T) {
    // Test new fork logic
}
```

## Testing Patterns

- **Test files** use the pattern `*_test.go`.
- **Testing framework** is Go's standard `testing` package.
- **Tests are placed** alongside the code they test, often in the same directory.
- **Example:**
  ```go
  // core/txpool/blobpool/limbo_test.go
  import "testing"

  func TestAddBlob(t *testing.T) {
      // Test implementation
  }
  ```

## Commands

| Command                   | Purpose                                                         |
|---------------------------|-----------------------------------------------------------------|
| /new-feature-with-tests   | Scaffold a new feature or migration with associated tests        |
| /update-params            | Apply and propagate protocol/configuration changes across modules |
```
