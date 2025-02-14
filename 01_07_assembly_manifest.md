## The Assembly Manifest

The assembly manifest is a file that contains metadata about the 
assembly itself.

The manifest documents all external assemblies required by the 
current assembly to function correctly, the assembly’s version 
number, copyright information, and so forth

---

### Manifest Content

Recall the implementation of the `Add` method in the `Calc` class:

```csharp
// Calc.cs
Calc c = new Calc();
int ans = c.Add(10, 84);
Console.WriteLine("10 + 84 is {0}.", ans);
//Wait for user to press the Enter key
Console.ReadLine();

// The C# calculator.
class Calc
{
    public int Add(int addend1, int addend2)
    {
        return addend1 + addend2;
    }
}
```

For this, the manifest will contain (among additional information):

```
.assembly extern /*23000001*/ System.Runtime
{
    .publickeytoken = (B0 3F 5F 7F 11 D5 0A 3A )         // .?_....:
    .ver 6:0:0:0
}
.assembly extern /*23000002*/ System.Console
{
    .publickeytoken = (B0 3F 5F 7F 11 D5 0A 3A )         // .?_....:
    .ver 6:0:0:0
}
.assembly /*20000001*/ Calc.Cs
{
    .hash algorithm 0x00008004
    .ver 1:0:0:0
}
.module Calc.Cs.dll
.imagebase 0x00400000
.file alignment 0x00000200
.stackreserve 0x00100000
.subsystem 0x0003       // WINDOWS_CUI
.corflags 0x00000001    // ILONLY
```

---
