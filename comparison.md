---
layout: page
title: Comparisons
long_title: Fort vs Other Open Source Compilers
permalink: /comparison/
---

## Fort vs Flang

Pro's of Flang vs Fort:

- Much more complete Fortran support (though less than that of GCC)

Pro's of Fort vs Flang:

- Fort, just like Clang, is designed to be easily understandable; it has virtually no learning curve for developers familiar with LLVM or Clang
- Fort implements its own compilation pipeline (rather than piggy-backing on Clang) which reduces complexity of the project and allows for faster builds
- Fort compiles against LLVM components and produces LLVM IR in memory, which allows catching many of potential IR issues at compile time
- Fort follows LLVM release lifecycle from get-go
- Fort supports all LLVM targets
- Flang emits LLVM IR as text, which is error-prone and often forces to check output only at runtime
- Fort uses LLVM diagnostics

## Fort vs GNU Fortran

Pro's of GNU Fortran vs fort:

- Much more complete Fortran support
- GNU Fortran (and GCC in general) supports more targets

Pro's of fort vs GNU Fortran:

- Fort ASTs and design are intended to be easily understandable
- Fort is designed as an API, which allows it to be used as a foundation for other tools
- BSD-style license (can be embedded in other products)
- Clear and concise diagnostics

