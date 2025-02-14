## Exploring an Assembly

Microsoft provides a tool called `ildasm.exe` (the Intermediate 
Language Disassembler utility) that can be used to disassemble .NET 
assemblies. This tool can be used to see the CIL code that is generated 
from a .NET assembly.

### Installing the `ildasm` Tool

To install navigate your terminal to the directory where your `.csproj` 
file is located. Then, run the following command to install `ildasm`
via NuGet:

```powershell
dotnet add package Microsoft.NETCore.ILDAsm --version 8.0.0
```
\* Note: I installed the .NET 8 version of `ildasm`, even though the
book uses .NET 6.

This will add the `ildasm` tool to your project and install `ildasm.exe`
to your user profile.

Then, modify your `Path` environment variable to include the directory
where `ildasm.exe` is installed. By default:

```C:\Users\<username>\.nuget\packages\runtime.win-x64.microsoft.netcore.ildasm\8.0.0\runtimes\win-x64\native\```

---

### Using the `ildasm` Tool

To use the `ildasm` tool, with the terminal still pointed to the 
project directory, run the following command:

```powershell
ildasm /all /METADATA /out=csharp.il .\bin\Debug\net8.0\HelloWorld.dll
```

Note: The path to your DLL may differ.

---

### Viewing the Disassembled Code

You can now open the `csharp.il` file. Let's look at the IL file
generated for our `HelloWorld` project.:

[Disassembled Code (csharp.il)](./HelloWorld/csharp.il)

---
