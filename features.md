---
layout: page
title: Features
long_title: Fort - Features and Goals
permalink: /features/
---

## End-user goals

- Fast compiles and low memory use
- Expressive diagnostics
- Modern Fortran support

## Utility and applications

- Modular library based architecture
- Support for building external tools via tooling API
- Same 'BSD' license as LLVM

## Development goals

- Following LLVM best practices
- Ease of maintenance
- Support for all LLVM-supported platforms
- Verbose diagnostics
- Quick portability
- Accepting contributions

## Examples

For diagnostics, consider this program:
```
$ cat init.f90
module i
  integer x, y, z
  parameter (y = 1, x = 3 + y + z)
end module
```

Note that variable `z` does not have `parameter` attribute, and therefore is illegal in `parameter` initialization.

First, Flang:
```
$ flang -fsyntax-only init.f90
F90-S-0087-Non-constant expression where constant expression required (init.f90: 3)
  0 inform,   0 warnings,   1 severes, 0 fatal for i
```

That is literally all the output, at least from version that supports LLVM 5. Second, GNU Fortran:
```
$ gfortran -fsyntax-only init.f90
init.f90:3:29:

   parameter (y = 1, x = 3 + z)
                             1
Error: Parameter 'z' at (1) has not been declared or is a variable, which does not reduce to a constant expression
```

And finally the same with Fort:
```
$ fort -fsyntax-only init.f90
init.f90:3:21: error: parameter 'x' must be initialized by a constant expression
  parameter (y = 1, x = 3 + y + z)
                    ^
init.f90:3:33: note: this expression is not allowed in a constant expression
  parameter (y = 1, x = 3 + y + z)
                                ^
```

