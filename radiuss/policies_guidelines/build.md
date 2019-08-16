## Build

**M.bui.1** All RADIUSS products must provide packaged installation and automated builds of their dependencies. In particular, a Spack package must be made available. 

> Rationale: Automating the build process prevents duplication of effort and allows others to build a copy of the code and to incorporate needed fixes in dependency tools and libraries. Spack is a package management tool designed for both HPC environments and for laptops that allows easy configuration with multiple dependency versions, configurations, platforms, and compilers.

Ref: Enforce WSC 1.1 and WSC 1.2

Tag: Tools 

---

**R.bui.3** RADIUSS products coded in C++ and/or FORTRAN should be buildable using CMake. BLT (Build, Link and Test) may be helpful as well.

> Rationale: Consistent use of CMake and BLT will enable individual users, computing centers, and package managers (such as Spack) to install the package in a way that is compatible with other RADIUSS products on the same system.

Ref: WSC 3.1

Tag: Tools 

---
