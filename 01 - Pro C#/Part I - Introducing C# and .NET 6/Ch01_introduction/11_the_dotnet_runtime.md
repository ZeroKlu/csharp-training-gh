## The .NET Runtime

The .NET runtime is just like the Java Virtual Machine (JVM) or the 
Python interpreter. It is the runtime environment (collection of 
services) that executes .NET code.

Conveniently, the .NET runtime is the same for all .NET languages.

---

## Assembly vs Namespace vs Type

### Namespaces

C# does not have a language-specific library, instead using the 
language-neutral .NET libraries.

In the interest of organization, .NET leverages the concept of 
*namespaces* to group related code together.

A namespace is the top-level, semantically meaningful grouping of
types.

As you can see in the example below, we can access namespaces from the
.NET library in the form: `using <namespace>`. IN this case, we are
accessing the `System` namespace, which is where the `Console` type is
defined.

Additionally, when we create an application, it has its own namespace. In
this case, we created the `HelloWorld` namespace.

```csharp
using System; // .NET Namespace where `Console` is defined

namespace HelloWorld // User-defined Namespace for application
{
    class Program
    {
        static void Main()
        {
            Console.WriteLine("Hello, World!");
        }
    }
}
```

> Note: You'll find that when you're creating .NET applications, you'll
> be able to optionally omit both of these from the code, as the
> C# project file provides an option to make namespaces implicit as well
> as the defined application namespace.

---

Although we are focused on C#, it's useful to see the syntax to access
namespaces in VB.NET as well.

```vb
Imports System ' .NET Namespace where `Console` is defined

Namespace HelloWorld ' User-defined Namespace for application
    Module Program
        Sub Main()
            Console.WriteLine("Hello World!")
        End Sub
    End Module
End Namespace
```

---

### Common Namespaces

|.NET Namespace|Description|
|-|-|
|System|Intrinsic data, mathematical computations, random number generation, environment variables, garbage collection, and commonly used exceptions and attributes|
|System.Collections<br>System.Collections.Generic|Stock container types and generics|
|System.Data<br>System.Data.Common<br>System.Data.SqlClient|Database interactions|
|System.IO<br>System.IO.Compression<br>System.IO.Ports|File and stream I/O operations|
|System.Reflection<br>System.Reflection.Emit|Runtime type discovery and dynamic creation of types|
|System.Runtime.InteropServices|Allows .NET types to interact with unmanaged code|
|System.Windows.Forms<br>System.Drawing|Types used to build desktop applications using .NET's original UI toolkit (WinForms)|
|System.Windows<br>System.Windows.Controls<br>System.Windows.Shapes|Root types for WPF applications|
|System.Linq<br>System.Linq.Expressions|Expose LINQ API|
|System.AspNetCore|ASP.NET Core applications and REST services|
|System.Threading<br>System.Threading.Tasks|Multi-threaded and async programming|
|System.Security|Security, authentication, permissions, and cryptography|
|System.Xml|Provides types for interacting with XML|
|||

---

### Programmatic Access to Namespaces

We noted above that we can make the content of a namespace available
throughout a .NET code file by using the `using` keyword.

If we omit the `using` statement, we can still access the namespace
directly when calling for a type it contains, like this:

```csharp
System.Console.WriteLine("Hello, World!");
```

Note how we prefixed the `Console` type with the `System` namespace
instead of including the `using System;` line.

We call this a *fully qualified name*. You will find places such as
configuration files where you will see the use of fully qualified types.

---

### Global Using Statements


