---
layout: page
title: Source
permalink: /hacking/
---

Compiler sources are on Github: [github.com/llvm-fortran/fort][comp].

## Building Fort together with LLVM

1. Get required tools
   - C/C++ compiler, see [LLVM System Requirements][ll-req]
   - CMake for builds, get it at [cmake.org/download](http://www.cmake.org/download)
   - Python for running tests, get it at [python.org/download](http://www.python.org/download)
   - `make` is assumed to be present, but you can use other [CMake generators][llcmake]
2. Get LLVM
   - `git clone https://github.com/llvm-mirror/llvm.git`
3. Checkout Fort inside of LLVM source tree
   - `cd llvm/tools`
   - `git clone https://github.com/llvm-fortran/fort.git`
4. Build
   - `mkdir build` (in-source builds are not supported)
   - `cd build`
   - `cmake ../llvm`
   - `make`

## Building Fort outside of LLVM source tree

1. Get, build, and install LLVM from source
2. Get Fort
   - `git clone https://github.com/llvm-fortran/fort.git`
3. Build
   - Make sure that `bin` subdirectory of LLVM installation is on the `PATH`
   - `mkdir build`
   - `cd build`
   - `cmake ../fort`
   - `make`


<a href="https://github.com/llvm-fortran"><img style="position: absolute; top: 0; right: 0; border: 0;" src="https://camo.githubusercontent.com/652c5b9acfaddf3a9c326fa6bde407b87f7be0f4/68747470733a2f2f73332e616d617a6f6e6177732e636f6d2f6769746875622f726962626f6e732f666f726b6d655f72696768745f6f72616e67655f6666373630302e706e67" alt="Fork me on GitHub" data-canonical-src="https://s3.amazonaws.com/github/ribbons/forkme_right_orange_ff7600.png"></a>

[comp]: https://github.com/llvm-fortran/fort
[rt]: https://github.com/llvm-fortran/libfortrt
[ll-req]: https://llvm.org/docs/GettingStarted.html#requirements
[llcmake]: https://llvm.org/docs/CMake.html
