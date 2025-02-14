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

Starting in C# 10, .NET introduces the concept of a global using statement.

You can add using statements in a standalone file or alongside
top-level statements (covered in chapter 3).

Alternately, you can include global using statements in the project file
(`<project_name>.csproj`) as follows:

```xml
<ItemGroup>
  <Using Include="System" />
  <Using Include="System.Text.Json" />
</ItemGroup>
```

---

### ImplicitGlobal Using Statements

Also introduced in C# 10, .NET introduces the concept of an implicit 
global using statement.

In the project file (`<project_name>.csproj`), you'll find the following:

```xml
<PropertyGroup>
  ...
  <ImplicitUsings>enable</ImplicitUsings>
  ...
</PropertyGroup>
```

When the `ImplicitUsings` property is enabled, the compiler will
automatically add using statements for namespaces that are referenced
in the code.

Not all namespaces can be added implicitly. Here are some examples of
supported namespaces:

|.NET Application Type|Supported Implicit Namespaces|
|-|-|
|Client (Microsoft.NET.Sdk)|System<br>System.Collections.Generic<br>System.IO<br>System.Linq<br>System.Net.Http<br>System.Threading<br>System.Threading.Tasks|
|Web (Microsoft.NET.Sdk.Web)|All from Microsoft.NET.Sdk plus:<br>System.Net.Http.Json<br>Microsoft.AspNetCore.Builder<br>Microsoft.AspNetCore.Hosting<br>Microsoft.AspNetCore.Http<br>Microsoft.AspNetCore.Routing<br>Microsoft.Extensions.Configuration<br>Microsoft.Extensions.DependencyInjection<br>Microsoft.Extensions.Hosting<br>Microsoft.Extensions.Logging|
|Worker Service (Microsoft.NET.Sdk.Worker)|All from Microsoft.NET.Sdk plus:<br>Microsoft.Extensions.Configuration<br>Microsoft.Extensions.DependencyInjection<br>Microsoft.Extensions.Hosting<br>Microsoft.Extensions.Logging|
|||

If implicit global using statements are enabled in your project, you
can see what namespaces were implicitly added in:
`.\obj\Debug\net8.0\<project_name>.GlobalUsings.g.cs`

```csharp
// <auto-generated/>
global using global::System;
global using global::System.IO;
// ...
```

---

### File-Scoped Namespaces

Another feature introduced in C# 10 is the ability to create file-scoped
namespaces.

These can be expressed at the beginning of a file without requiring curly
braces.

So...

```csharp
namespace HelloWorld
class Program {
    // ...
}
```

...is the same as...

```csharp
namespace HelloWorld
{
    class Program {
        // ...
    }
}
```

---

### Referencing External Assemblies

#### What happened to the GAC?

In the older .NET Framework, you referenced external assemblies from the
GAC (Global Assembly Cache). In .NET Core, each version is installed
separately.

For example, on a Windows PC, each version's SDK is installed in
`C:\Program Files\dotnet\sdk\...`

---

#### Where do I find assemblies for needed namespaces?

You typically use the NuGet package manager to install external assemblies
for .NET Core applications.

**In Visual Studio**

1. Right-click the project (in the Solution Explorer) and select *Manage 
  NuGet Packages*.  
  or...  
  Click on the *Project* menu and select *Manage NuGet Packages*.
2. Search for the package you want to install.
3. Select and install the desired version.

**In Visual Studio Code**

1. Press *Ctrl+Shift+P* to open the Palette Menu and select the
  *Nuget: Add NuGet Package* command.
2. If you have multiple projects, you will be prompted to select which 
  project to update.
3. Search for the package you want to install.
4. Select and install the desired version.

---

#### What about assemblies that aren't available on NuGet?

We'll practice a number of ways to include non-NuGet assemblies, including

* Adding a reference to the assembly in the project file
* Using the dependency node in visual studio
* etc.

---
