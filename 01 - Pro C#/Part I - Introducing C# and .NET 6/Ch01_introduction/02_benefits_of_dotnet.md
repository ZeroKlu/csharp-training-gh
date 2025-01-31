## Why Use .NET?

There are a number of benefits to using .NET.

### Key Benefits of .NET

* Multi-Language Support
    * C# - C-like, primary language used for ASP.NET Core
    * F# - Python-like, simplified language for functional .NET programming
    * VB.NET - Visual Basic-like, alternate language for .NET
* Common Runtime
    * The CoreCLR is the .NET Core equivalent of the .NET Framework CLR
    * Includes implementations of data types and basic runtime engine
* Language Integration
    * The following cross-language features are supported:
        * Inheritance
        * Exception Handling
        * Debugging
        * Reflection
* Comprehensive Base CLass Library
    * .NET includes thousands of predefined classes
* Simplified Deployment Model
    * .NET libraries do not have to be registered (in the system registry)
    * Multiple versions of .NET can be installed on a single machine
* Command-Line Support
    * The command-line interface (CLI) is a cross-platform toolchain
    * Can be used to create, develop, build, and deploy applications

---

### .NET Support Life Cycle

#### Long Term Releases

When a long-term support (LTS) version of .NET is released, it is supported
for one of the following (whichever is longer):

* Three years after the initial release
* One year after the next LTS version release

#### Short Term Releases

A short-term release of .NET is supported for six months after the next
short- or long-term release.

---

### Building Blocks of .NET

.NET is made up of three main parts:

* The .NET Runtime
    * The set of minimal implementations that are tied specifically to a 
      platform (Windows, iOS, Linux) and architecture (x86, x64, ARM)
    * All of the base types for .NET
* The Common Type System (CTS)
    * Fully describes all possible data types and all programming 
      constructs supported by the runtime
    * Note: Not all languages will support every CTS component
* The Common Language Specification (CLS)
    * Subset of common types and programming constructs that all .NET 
      programming languages can agree on.
    * Limiting your code to CLS-only guarantees that your code will
      be compatible with all other .NET languages

---

### Base Class Libraries

The base class libraries are a collection of prebuilt components that
are common to all programming languages supported by .NET.

---

### What is .NET Standard?

The number of base class libraries in the .NET Framework far exceeds those 
in .NET. Additionally, many organizations have built extensive libraries
of software based on .NET Framework.

This is understandable, as the .NET Framework had a 14-year head start on
.NET.

This disparity created issues when attempting to use .NET Framework code 
with .NET code.

The solution (and requirement) for .NET Framework/.NET Core 3.1 interop 
is .NET Standard, which:

* Defines a uniform set of BCL APIs for all .NET implementations to 
  implement, independent of workload
* Enables developers to produce portable libraries that are usable across .
  NET implementations, using this same set of APIs
* Reduces or even eliminates conditional compilation of shared source due 
  to .NET APIs, only for OS APIs

---
