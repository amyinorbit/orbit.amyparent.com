---
title: Source Code
nav: true
layout: page
---

Orbit is open source!

The source code behind the compiler and the runtime are available on [GitHub at amyinorbit/orbitvm](https://github.com/amyinorbit/orbitvm). If you found a bug, want to fix an issue or add a feature, you are more than welcome to file an issue, fork the project or send a pull request.

Orbit is programmed entirely in C. The development has been done using LLVM/Clang so far, but the project should compile with GCC without problems. CMake is used for the build system.

The project structure is heavily inspired by that of the Swift Programming Language ([apple/swift](https://github.com/apple/swift)). Each module of the runtime and compiler is compiled as a library, which enables better reuse of each of those modules.
