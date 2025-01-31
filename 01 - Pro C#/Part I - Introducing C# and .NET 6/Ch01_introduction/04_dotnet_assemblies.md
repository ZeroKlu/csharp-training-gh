## .NET Assemblies

All versions of .NET create binary files using the extension `.dll`.

Importantly, although they use the `.dll` (dynamic link library) extension,
.NET binaries have no internal similarity to the unmanaged Windows binaries
that share that extension.

.NET binaries are not complied to machine code (specific to the platform
CPU architecture) but are instead partially compiled int a platform
agnostic intermediate language (IL) that is then translated to machine code
at runtime.

> Intermediate Language (*IL*) is also known as:
> * *CIL*: Common Intermediate Language  
>   or
> * *MSIL*: or Microsoft Intermediate Language

---

### Running An Executable .NET Assembly

#### In .NET Core

In .NET, all assemblies are compiled to the `.dll` extension, even when
they are executable assemblies (In .NET Framework, executables receive the
extension `.exe`).

To execute an executable .NET Core assembly, you would use the following 
command:

```powershell
dotnet.exe <assembly_name.dll>
```

---

#### In .NET Core 3.0+

In .NET 3.0+, the `dotnet.exe` command is copied to the build directory and
renamed to `<assembly_name>.exe`. Running this command automatically calls
the assembly DLL as an argument.

So, a call to...

```powershell
<assembly_name>.exe
```

...is the same as...

```powershell
dotnet.exe <assembly_name.dll>
```

---

#### In .NET 6+

.NET 6 introduces the ability to reduce the compiled assembly to a single
file using the `.exe` extension.

However, this is just a packaging convenience, and the resulting file
still contains both the `.dll` assembly and the `dotnet.exe` command.

---

### Accessing CIL Instructions in .NET Assemblies

.NET assemblies contain CIL code (similar to Java bytecode), which is not 
compiled to machine code until absolutely necessary.

We can think of "absolutely necessary" as "when the CIL is referenced by 
the .NET runtime." This is often referred to as "just-in-time (JIT) 
compilation."

---

### Metadata in .NET Assemblies

.NET assemblies contain metadata that is used by the .NET runtime to
describe characteristics of any types (classes) implemented in the 
assembly.

Additionally, there is a separate tier of metadata that describes the
assembly itself. This is called the *manifest*.

---
