# MoonBit AST Printer

A pretty printer for MoonBit AST that converts parsed AST back to source code.

## Installation

```json
{
  "deps": {
    "mizchi/ast_printer": "0.1.0"
  }
}
```

## Usage

```moonbit
let source = "fn hello() -> String { \"hello\" }"
let parsed = @moonbitlang/parser.parse_string(source)

// Print back to source code (returns None if parse errors)
let result : String? = @mizchi/ast_printer.print_code(parsed)

// Or print AST directly
let (impls, _) = parsed
let code : String = @mizchi/ast_printer.print_impls(impls)
```

## API

- `print_code(parsed)` - Convenience function that takes parse result, returns `String?`
- `print_impls(impls)` - Print top-level implementations to string
- `print_expr(buf, expr)` - Print expression to StringBuilder
- `print_type(buf, ty)` - Print type to StringBuilder
- `print_pattern(buf, pat)` - Print pattern to StringBuilder
- `print_constant(buf, c)` - Print constant to StringBuilder
