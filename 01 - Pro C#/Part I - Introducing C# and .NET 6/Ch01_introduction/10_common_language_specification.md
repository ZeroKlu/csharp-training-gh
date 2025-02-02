## The Common Language Specification (CLS)

The Common Language Specification (CLS) defines a subset of
functionality common to all .NET languages.

---

### Languages Implement the Same Functionality Differently

Different programming languages do things... well... differently.

For example:

#### String Concatenation

In C#...

```csharp
string s1 = "Hello";
string s2 = "World";
string s3 = s1 + " " + s2;
```

In VB.NET...

```vb
Dim s1 As String = "Hello"
Dim s2 As String = "World"
Dim s3 As String = s1 & " " & s2
```

In F#...

```f#
let s1 = "Hello"
let s2 = "World"
let s3 = s1 + " " + s2
```

For areas like this, where all the functionality is the same, the 
.NET runtime doesn't care about the syntactic differences, because 
the language compilers will emit the same CIL.

---

### But Not All Functionality is Common

Unfortunately, not all functionality is common across all .NET 
languages.

Because of this, it is important to define the base set of 
functionality that all .NET languages must support, so that the 
.NET runtime can use the same CIL to execute all code.

The CLS is a set of rules that describe in vivid detail the minimal 
and complete set of features a given .NET compiler must support to 
produce code that can be hosted by the .NET Runtime, while at the 
same time be accessed in a uniform manner by all languages that 
target the .NET platform. In many ways, the CLS can be viewed as a 
subset of the full functionality defined by the CTS.

---

### CLS Rules

**Rule 1**:  
CLS rules apply only to those parts of a type that are exposed 
outside the defining assembly.

So, this example would be non-compliant, because it exposes a
non-compliant type (`ulong`):

```csharp
class Calc
{
    // Exposed unsigned data is not CLS compliant!
    public ulong Add(ulong addend1, ulong addend2)
    {
        return addend1 + addend2;
    }
}
```

But, if the unsigned data is only used internally, the code is CLS
compliant:

```csharp
class Calc
{
    public int Add(int addend1, int addend2)
    {
        // As this ulong variable is only used internally,
        // we are still CLS compliant.
        ulong temp = 0;
        // ...
        return addend1 + addend2;
    }
}
```

> Note: We can ensure CLS compliance by annotating our code thus:
>
> ```csharp
> [assembly: CLSCompliant(true)]
> ```
>
> This attribute instructs the compiler to check all code for CLS
> compliance. Any non-compliant code will raise a compiler warning.

---
