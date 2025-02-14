## Understanding the Common Intermediate Language (CIL)

As we've already discussed, the code you develop in a .NET application is
compiled only down to a common language (the CIL), which is agnostic to the
platform-specific instruction set.

Let's take a look at how CIL works.

---

### CIL Instructions

As an example, the book has us look at the `Add` method in a `Calc`
class:

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

If we compile this C# code, we produce an assembly that contains a 
manifest, metadata, and a set of CIL instructions:

In the assembly, the `Add` method is defined in CIL as follows:

```msil
.method public hidebysig instance int32 Add(int32 addend1,
            int32 addend2) cil managed
{
    // Method begins at RVA 0x2090
    // Code size       9 (0x9)
    .maxstack 2
    .locals /*11000002*/ init (int32 V_0)
    IL_0000: /* 00 |                     */ nop
    IL_0001: /* 03 |                     */ ldarg.1
    IL_0002: /* 04 |                     */ ldarg.2
    IL_0003: /* 58 |                     */ add
    IL_0004: /* 0A |                     */ stloc.0
    IL_0005: /* 2B | 00                  */ br.s IL_0007
    IL_0007: /* 06 |                     */ ldloc.0
    IL_0008: /* 2A |                     */ ret
} // end of method Calc::Add
```

We'll learn how to read this later, but the important thing to note is that
this is not platform-specific code.

---

### Other Languages

The exact same CIL would be compiled if you implemented the `Add` method in
a different language:

#### VB.NET

The same method implemented in Visual Basic...
```vb
' Calc.vb
Module Program
' This class contains the app's entry point.
Sub Main(args As String())
Dim c As New Calc
Dim ans As Integer = c.Add(10, 84)
Console.WriteLine("10 + 84 is {0}", ans)
'Wait for user to press the Enter key before shutting down
Console.ReadLine()
End Sub
End Module
' The VB.NET calculator.
Class Calc
Public Function Add(ByVal addend1 As Integer, ByVal addend2 As Integer) As Integer
Return addend1 + addend2
End Function
End Class
```

... results in essentially the same CIL:

```msil
.method public instance int32 Add(int32 addend1,
                                  int32 addend2) cil managed
{
    // Code size       9 (0x9)
    .maxstack 2
    .locals init (int32 V_0)
    IL_0000:  nop
    IL_0001:  ldarg.1
    IL_0002:  ldarg.2
    IL_0003:  add.ovf
    IL_0004:  stloc.0
    IL_0005:  br.s       IL_0007
    IL_0007:  ldloc.0
    IL_0008:  ret
} // end of method Calc::Add
```

---

#### F#

The method implemented in F#...
```f#
// Calc.fs
open System

module Calc =
    let add addend1 addend2 =
        addend1 + addend2
[<EntryPoint>]
let main argv =
    let ans = Calc.add 10 84
    printfn "10 + 84 is %d" ans
    Console.ReadLine()
    0
```

... still produces basically the same CIL:

```msil
.method public instance int32 Add(int32 addend1,
                                  int32 addend2) cil managed
{
    // Code size       9 (0x9)
    .maxstack  2
    .locals init (int32 V_0)
    IL_0000:  nop
    IL_0001:  ldarg.1
    IL_0002:  ldarg.2
    IL_0003:  add.ovf
    IL_0004:  stloc.0
    IL_0005:  br.s       IL_0007

    IL_0007:  ldloc.0
    IL_0008:  ret
} // end of method Calc::Add
```

---

### Advantages of CIL

There are a number of advantages to CIL:

* Language Integration
    * Since all .NET languages produce functionally equivalent CIL, you can
      implement an assembly created in any .NET language in code in another
* Platform Agnostic
    * Since CIL is not tied to any platform-specific instruction set, you 
      can develop code once and deploy it across multiple platforms  
      *So there, Java devs!  
      You're not the only single-code-base language on the block any more 
      \- Neener neener!*
    * Prior to .NET 6, there were multiple platform-specific  
      implementations of .NET (Mono, e.g.), but those have become mostly
      redundant, since .NET 6+ includes implementations for those platforms

---

### Compiling CIL to Machine Code

At the end of the day, a CPU can only execute code that calls its specific
instruction set. This means that CIL is not directly executed on the CPU.
It must be compiled to machine code.

This is accomplished by the just-in-time (JIT) compiler (or *jitter*). 
.NET includes JIT compilers for each supported platform architecture.

Jitters are platform-aware, so they are able to optimize the code to be
run in the target platform's environment.

A jitter will only compile a class or function to machine code if it is
referenced during runtime. However, once an item is compiled to machine
code, it is cached, so if it is later referenced again, it does not need
to be recompiled.

Prior to .NET 6, you could use `crossgen.exe` to pre-JIT your code, but
this is now built into the framework.
      
---
