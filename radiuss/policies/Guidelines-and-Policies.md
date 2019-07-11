
# RADIUSS Guidelines and Policies :

M → Mandatory

R → Recommended


## Licensing

**M.lic.1**  [OSI-approved permissive open-source license](/licensing/Mlic1.md)

**M.lic.2**  [List of dependencies](/licensing/Mlic2.md)

**R.lic.3**  Existing RADIUSS products should consider transitioning to an OSI-approved, permissive open-source license (e.g., Apache, MIT, or BSD 3-Clause). 

**R.lic.4**  RADIUSS products should provide a list of dependencies and their associated licenses in Software Package Data Exchange (SPDX) format.


## Documentation

**M.doc.1** RADIUSS products must publish documentation in a web-based form.

**M.doc.2** RADIUSS product documentation source must be revision-controlled along with source code.

**R.doc.3** RADIUSS product documentation should be produced using Sphinx, LaTeX, or Doxygen.

**R.doc.4** RADIUSS products should provide code samples along with documentation

**M.doc.5** Provide a documented, reliable way to contact the development team, even for RADIUSS itself


## Build

**M.bui.1** All RADIUSS products must support automated builds of their dependencies.

**M.bui.2** All RADIUSS products must support installation using Spack.

**R.bui.3** RADIUSS products coded in C++ and/or FORTRAN should be built using CMake and BLT (Build, Link and Test).


## Version Control

**M.ver.1** All RADIUSS products must be version-controlled and must use Git.

**M.ver.2** Each RADIUSS product must be maintained at GitHub.

**R.ver.3** Products should use Pull Requests to facilitate code review and testing of code changes.


## Testing and Continuous Integration

**M.tes.1** All products must include regression tests.

**M.tes.2** RADIUSS products must provide a comprehensive test suite that can be run by users and does not require the purchase of commercial software.

**R.tes.3** A significant subset of the test suite should complete within a few hours on standard workstation-level hardware. It is also recommended that at least a significant subset of the tests be can be run in batch-only environments.

**R.tes.4** The test suite should include an option to perform compilation across a matrix of compilers.

**M.tes.5** All RADIUSS products must use Continuous Integration (CI) so that changes are tested as they are introduced.  Examples of CI tools include Travis CI for projects hosted on GitHub or GitLab CI for projects hosted on a GitLab instance such as LC-GitLab.  Future products may use Azure Pipelines.

**R.tes.6** Products should enforce code quality/health with static checkers and/or other tools.


## Portability

**M.por.1** RADIUSS products must support common HPC platforms, including standard Linux distributions, and common compiler toolchains such as GNU, Clang, and vendor compilers. 

**R.por.2** Support for Apple Mac OS and Microsoft Windows Visual Studio is recommended.


## Packaging

**M.pac.1** Each RADIUSS product API must include a way to return the current version number of the software and indicate which configure/CMAKE and compiler options were used to build the package. For development versions of the software, each package must provide the current commit ID in the repository.

**R.pac.2** Each RADIUSS product should use a limited and well-defined symbol, macro, library, and include file name space . For example, there should be no publicly-visible include files such as utils.h, or package named libutil.a or macros named YES or TRUE. Namespacing of include files can be handled either by prepending each include file with a package name, for example <XXXutils.h>, or by placing and referencing all include files in a subdirectory with a package name, for example <XXX/utils.h>. Note that using a -I/XXX/ and referencing it in source via <utils.h> would not be acceptable namespacing due to the inherent fragility of this approach.

**M.pac.3** Each RADIUSS product that utilizes MPI must restrict its MPI operations to MPI communicators that are provided to it and not use directly MPI_COMM_WORLD. Products must use configure tests or version tests to detect MPI 2 or MPI 3 features that may not be available; it should not be assumed that a full MPI 2 or MPI 3 implementation is available. Products can change the MPI error-handling mode by default but should have an option to prevent them from changing the MPI error handling (which may have been set by another package or the application). The product should also behave appropriately regardless of the MPI error handling being used. There is no requirement that the product provide a sequential (non-MPI) version, but if one is provided, there is no requirement that it be compatible or usable with other RADIUSS products running without MPI.


## Logging and Debugging

**R.log.1**  RADIUSS products should use SLIC for logging.

**R.log.2**  RADIUSS products should make debug support switchable at compile time.


