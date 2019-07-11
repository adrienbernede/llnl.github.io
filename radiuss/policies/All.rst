


M → Mandatory requirement
R → Recommended practice




1. Licensing

**M.lic.1**  New RADIUSS products must use an OSI-approved, permissive open-source license (e.g., Apache, MIT, or BSD 3-Clause).  Similarly, any required dependencies must use an OSI-approved license that is considered compatible with the open-source permissive license for distribution purposes. Non-critical optional dependencies may use any OSI-approved license.

> Rationale: A permissive open-source license is friendlier to use by commercial entities. Note that strong copyleft licenses (e.g., GPL) are not considered compatible with permissive licenses. Weaker copyleft licenses (e.g., LGPL or GPL v2 with runtime exception) can be considered compatible for distribution purposes.

Ref: xSDK M7


**M.lic.2**  RADIUSS products must provide a list of dependencies and their associated licenses.

> Rationale: This provides critical information to users and projects that include RADIUSS products.


**R.lic.3**  Existing RADIUSS products should consider transitioning to an OSI-approved, permissive open-source license (e.g., Apache, MIT, or BSD 3-Clause). 

> Rationale: See M4.1


**R.lic.4**  RADIUSS products should provide a list of dependencies and their associated licenses in Software Package Data Exchange (SPDX) format.

> Rationale: The SPDX License List is a list of commonly found licenses and exceptions used in open source software that enables easy and efficient identification of such licenses. See also M4.2.

Example:  See the Spack COPYRIGHT file.

Tag: Practical/Convenience technical restriction




2. Documentation

**M.doc.1** RADIUSS products must publish documentation in a web-based form.

> Rationale: Web-based documentation is accessible, searchable, and linkable. It allows users to easily point each other to relevant parts of the documentation in emails, in the code, and in other documents. 

Ref: WSC 4.1


**M.doc.2** RADIUSS product documentation source must be revision-controlled along with source code.

> Rationale: The documentation should be version controlled along with source code so that developers and users can easily retrieve the documentation associated with any revision of the code. Versioning documentation with source code also allows any developer to easily contribute to the documentation. (WSC 4.3)

Ref: WSC 4.3


**R.doc.3** RADIUSS product documentation should be produced using Sphinx, LaTeX, or Doxygen.

> Rationale: All of these tools allow you to create web-based manuals and API documentation automatically, using a familiar, non-HTML plain-text format.

Ref: WSC 4.4

Tag: Practical/Convenience technical restriction


**R.doc.4** RADIUSS products should provide code samples along with documentation


**M.doc.5** Provide a documented, reliable way to contact the development team, even for RADIUSS itself

Ref: xSDK M5




1. Build

**M.bui.1** All RADIUSS products must support automated builds of their dependencies.

> Rationale: Automating the build process prevents duplication of effort and allows others to build a copy of the code and to incorporate needed fixes in dependency tools and libraries. 

Ref: enforce WSC 1.1


**M.bui.2** All RADIUSS products must support installation using Spack.

> Rationale: Spack is a package management tool designed for both HPC environments and for laptops that allows easy configuration with multiple dependency versions, configurations, platforms, and compilers. (WSC 1.2) (Practical/Convenience technical restriction)

Ref: Enforce WSC 1.2

Tag: Practical/Convenience technical restriction


**R.bui.3** RADIUSS products coded in C++ and/or FORTRAN should be built using CMake and BLT (Build, Link and Test).

> Rationale: Consistent use of CMake and BLT will enable individual users, computing centers, and package managers (such as Spack) to install the package in a way that is compatible with other RADIUSS products on the same system.

Ref: WSC 3.1

Tag: Practical/Convenience technical restriction




4. Version Control

**M.ver.1** All RADIUSS products must be version-controlled and must use Git.

> Rationale: Version control is essential for collaborative development and change tracking.  Git is the most popular version control system by a wide margin and sophisticated many web-based collaboration tools are available for it.

Ref: WSC 2.1

Tag: Practical/Convenience technical restriction


**M.ver.2** Each RADIUSS product must be maintained at GitHub.

> Rationale: GitHub is one of the most-used repositories of open source software that includes collaboration tools such as issue tracking, pull requests, and wikis. Pull requests allow project maintainers to review changes, comment, and iterate with developers before new features are committed to a code base. Pull requests and branching simplify management of large numbers of contributions (particularly contributions across teams) and they enable many features to be developed concurrently.

Ref: WSC 2.3, 2.4

Tag: Practical/Convenience technical restriction


**R.ver.3** Products should use Pull Requests to facilitate code review and testing of code changes.

> Rationale: The product maintainer can review code and associated test results before merging it into a public branch. Pull requests can also be linked to GitHub issues, which can be created by anyone.

Ref: Part of xSDK M10 and R1




5 Testing and Continuous Integration

**M.tes.1** All products must include regression tests.

> Rationale: Regression tests prevent new features from affecting prior functionality, and they allow developers to have more confidence in their changes when modifying code.

Ref: WSC 5.1


**M.tes.2** RADIUSS products must provide a comprehensive test suite that can be run by users and does not require the purchase of commercial software.

> Rationale: An executable test suite gives users confidence that the product gives correct results. (M1.4 + M1.6 = xSDK M2)

Ref: xSDK M2


**R.tes.3** A significant subset of the test suite should complete within a few hours on standard workstation-level hardware. It is also recommended that at least a significant subset of the tests be can be run in batch-only environments.

> Rationale: A limited set of tests is needed to quickly identify obvious (not subtle) problems. (M1.4 + M1.6 = xSDK M2)

Ref: xSDK M2


**R.tes.4** The test suite should include an option to perform compilation across a matrix of compilers.

> Rationale: This option helps guard against platform-specific or compiler-specific errors.  Ideally, it should execute in minutes, not hours.


**M.tes.5** All RADIUSS products must use Continuous Integration (CI) so that changes are tested as they are introduced.  Examples of CI tools include Travis CI for projects hosted on GitHub or GitLab CI for projects hosted on a GitLab instance such as LC-GitLab.  Future products may use Azure Pipelines.

> Rationale: CI helps prevent integration problems by identifying issues as they arise instead of allowing them to compound. This helps reduce rework and reduces cost and time

Examples:

RAJA with Travis CI on GitHub.  See .travis.yml 
VisIT with Circle CI on GitHub.  See  .circleci/config.yml
MFEM with AppVeyor on GitHub.  See  .appveyor.yml
Ascent with Azure Pipelines on GitHub. See azure-pipelines.yml


**R.tes.6** Products should enforce code quality/health with static checkers and/or other tools.

> Rationale: Code quality checkers help to prevent code constructs that may result in errors in future environments where the code may run. They also reduce noise in build output that may obfuscate real errors. Code style checkers can also help enforce consistent style across a project.

Ref: WSC 5.4



6. Portability

**M.por.1** RADIUSS products must support common HPC platforms, including standard Linux distributions, and common compiler toolchains such as GNU, Clang, and vendor compilers. 

> Rationale:  This will ensure a broad base of users.

Ref: xSDK M4


**R.por.2** Support for Apple Mac OS and Microsoft Windows Visual Studio is recommended.

> Rationale:  This allows code development on common desktop and laptop machines.

Ref: xSDK M4



7. Packaging

**M.pac.1** Each RADIUSS product API must include a way to return the current version number of the software and indicate which configure/CMAKE and compiler options were used to build the package. For development versions of the software, each package must provide the current commit ID in the repository.

> Rationale: This allows users to make an inventory of what they have, which can aid debugging and configuration management. 

Ref: See Smart Libraries Practice 10 / xSDK M8.


**R.pac.2** Each RADIUSS product should use a limited and well-defined symbol, macro, library, and include file name space . For example, there should be no publicly-visible include files such as utils.h, or package named libutil.a or macros named YES or TRUE. Namespacing of include files can be handled either by prepending each include file with a package name, for example <XXXutils.h>, or by placing and referencing all include files in a subdirectory with a package name, for example <XXX/utils.h>. Note that using a -I/XXX/ and referencing it in source via <utils.h> would not be acceptable namespacing due to the inherent fragility of this approach.

> Rationale: This allows users to unambiguously identify the components within their installed configuration. 

Ref: See Smart Libraries Practice 18. / Less restrictive than xSDK M9


**M.pac.3** Each RADIUSS product that utilizes MPI must restrict its MPI operations to MPI communicators that are provided to it and not use directly MPI_COMM_WORLD. Products must use configure tests or version tests to detect MPI 2 or MPI 3 features that may not be available; it should not be assumed that a full MPI 2 or MPI 3 implementation is available. Products can change the MPI error-handling mode by default but should have an option to prevent them from changing the MPI error handling (which may have been set by another package or the application). The product should also behave appropriately regardless of the MPI error handling being used. There is no requirement that the product provide a sequential (non-MPI) version, but if one is provided, there is no requirement that it be compatible or usable with other RADIUSS products running without MPI.

> Rationale:  See xSDK M3.




8. Logging and Debugging

**R.log.1**  RADIUSS products should use SLIC for logging.

> Rationale:  Consistency and ease of maintenance, etc.

Tag: Practical/Convenience technical restriction


**R.log.2**  RADIUSS products should make debug support switchable at compile time.

> Rationale:  Users don't always need (or want) debug information, and providing debug support may degrade performance.

Ref: Smart Libraries practice 19


