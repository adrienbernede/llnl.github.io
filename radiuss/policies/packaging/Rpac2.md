
**R.pac.2** Each RADIUSS product should use a limited and well-defined symbol, macro, library, and include file name space . For example, there should be no publicly-visible include files such as utils.h, or package named libutil.a or macros named YES or TRUE. Namespacing of include files can be handled either by prepending each include file with a package name, for example <XXXutils.h>, or by placing and referencing all include files in a subdirectory with a package name, for example <XXX/utils.h>. Note that using a -I/XXX/ and referencing it in source via <utils.h> would not be acceptable namespacing due to the inherent fragility of this approach.

> Rationale: This allows users to unambiguously identify the components within their installed configuration. 

Ref: Smart Libraries Practice 18 / Less restrictive than xSDK M9
