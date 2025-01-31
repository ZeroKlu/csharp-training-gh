## Understanding Type Metadata

As we've already discussed, in addition to the CIL instructions, .NET
assemblies contain metadata that is used by the .NET runtime to 
describe the characteristics of any types (classes) implemented in 
the assembly.

Let's review how that works.

---

### Metadata for the `Calc` Class and `Add` Method

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

For this, the assembly includes the following metadata:

```
// TypeDef #2 (02000003)
// -------------------------------------------------------
//  TypDefName: Calc (02000003)
//  Flags     : [NotPublic] [AutoLayout] [Class] [AnsiClass] [BeforeFieldInit] (00100000)
//  Extends    : 0100000D [TypeRef] System.Object
//  Method #1 (06000003)
//  -------------------------------------------------------
//    MethodName: Add (06000003)
//    Flags     : [Public] [HideBySig] [ReuseSlot] (00000086)
//    RVA       : 0x00002090
//    ImplFlags : [IL] [Managed] (00000000)
//    CallCnvntn: [DEFAULT]
//    hasThis
//    ReturnType: I4
//    2 Arguments
//      Argument #1:  I4
//      Argument #2:  I4
//    2 Parameters
//      (1) ParamToken : (08000002) Name : addend1 flags: [none] (00000000)
//      (2) ParamToken : (08000003) Name : addend2 flags: [none] (00000000)
```

In addition to the runtime, many other tools use this metadata to
understand the structure of the assembly.

For example, the availability of IntelliSense in Visual Studio and
VS Code relies on this metadata.

---
