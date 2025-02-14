## What C# Brings to the Table

C#, like Java, is a descendent of the C family of programming languages
(C, Objective-C, C++, etc.), at least in terms of syntax.

Additionally, C# draws from the syntax of VIsual Basic (for example, the
implementation of class *properties* as opposed to getter and setter
methods).

C# also inherits useful concepts from other languages, such as lambda 
expressions and anonymous functions (from functional languages like Haskell)

C# also introduces unique constructs based on LINQ (Language Integrated
Query).

---

### Advantages of C#

C# brings a number of advantages to the table:

* Does not require pointers (although they are still supported)
* Automatic memory management (using the garbage collector)
* Formal syntactic constructs for classes, interfaces, structures, 
  enumerations, and delegates
* Operator overloading (without the complexity required in C++)
* Support for attribute-based programming (decoration)

---

### Managed vs Unmanaged Code

C# can only be used to build .NET (and .NET Framework) applications.

Because of this, C# cannot explicitly allocate or free memory on the heap.
The .NET garbage collector takes care of this for you. This is known as
*managed code*.

The side effect of building managed code is that it can be executed on any
platform supported by .NET, including Windows, Linux, and macOS.

Although .NET does allow you to make use of unmanaged code (COM DLLs,
e.g.), doing so, locks you into the specific platform (Windows, e.g.) for
which the unmanaged code was written.

---
