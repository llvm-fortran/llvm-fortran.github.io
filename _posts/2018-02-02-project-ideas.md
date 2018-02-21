---
layout: post
title:  Project Ideas
date:   2018-02-02 17:17:59 -0800
categories: projects
---

_Update:_ See [Project Ideas][wiki] wiki page for current list.

The ideas listed here came from our community, feel free to propose your own.

## Tooling

- Develop [Tooling API](Tooling). Define a C and C++ interfaces to
  - embed the compiler in third-party applications
  - write plugins
- Write a static processing tool for Fortran (requires some of the tooling API)

## Compiler driver

- Implement [compiler driver][dr]

## Debug information support

Use LLVM IR Metadata to emit debug information.

## Polyhedral optimizations

Add support for polyhedral loop optimizations. This would include:

- Providing support for [LLVM Polly][polly] optimization passes
- Analyzing optimized code and potentially tweaking optimization passes

## OpenMP support

Implement some OpenMP support using LLVM's OpenMP runtime library. Project is open-ended, full scope would be very large, but a subset of OpenMP clauses can be implemented in reasonable time. This would include:

- Parsing OpenMP pragmas
- Outlining regions defined by the pragmas
- Emitting code for outlined regions and making calls to OpenMP runtime

## Proposing your own project

Please open an issue describing your proposal. Check our [proposed enhancement list][es] for some of the potential ideas. Feel free to post comment on any of those if you have questions.

[is]: https://github.com/llvm-fortran/fort/issues
[es]: https://github.com/llvm-fortran/fort/issues?q=is%3Aissue+is%3Aopen+label%3Aenhancement
[dr]: https://github.com/llvm-fortran/fort/issues/4
[polly]: http://polly.llvm.org
[wiki]: https://github.com/llvm-fortran/fort/wiki/Project-Ideas
