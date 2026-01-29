# MoonBit AST Printer

A pretty printer for MoonBit AST - converts parsed AST back to source code.

## Quick Commands

```bash
just           # check + test
just fmt       # format code
just check     # type check
just test      # run tests
just test-update  # update snapshot tests
just info      # generate type definition files
```

## Project Structure

- `moon.mod.json` - Module definition
- `src/moon.pkg` - Package dependencies
- `src/*.mbt` - Source files
- `src/*_test.mbt` - Test files

## Coding Convention

- Each block is separated by `///|`
- MoonBit code uses snake_case for variables/functions (lowercase only)

## Code Navigation (IMPORTANT)

**Always use `moon ide` and `moon doc` instead of grep/Read for code exploration.**

### `moon ide` - Semantic Code Navigation

```bash
# Show symbol definition with source code
moon ide peek-def print_code
moon ide peek-def print_expr

# List symbols in a file
moon ide outline src/printer.mbt
```

### `moon doc` - Standard Library API Discovery

```bash
moon doc 'String'         # List String methods
moon doc 'Array'          # List Array methods
moon doc '@parser'        # List symbols in package
```

## Tooling

- `moon fmt` is used to format your code properly.
- `moon info` is used to update the generated interface of the package.
- `moon test` to check the test is passed. Use `moon test --update` to update snapshots.
- `moon check` to check the code is linted correctly.

## Before Commit

```bash
just release-check  # fmt + info + check + test
```
