## CTS Type Members

A CTS type can contain any number of members, which are of the set
`{constructor, finalizer, static constructor, nested type, operator, 
method, property, indexer, field, read-only field, constant, event}`

CTS members can possess a number of adornments, such as:
* Visibility: public, private, protected, internal, etc.
* Usage: static, virtual, abstract, sealed, etc.

---

### CTS Intrinsic DataTypes

The CTS also establishes a well-defined set of fundamental data 
types, including:

|CTS Data Type|VB Type Keyword|C# Type Keyword|
|-|-|
|System.Byte|Byte|byte|
|System.SByte|SByte|sbyte|
|System.Int16|Short|short|
|System.Int32|Integer|int|
|System.Int64|Long|long|
|System.UInt16|UShort|ushort|
|System.UInt32|UInteger|uint|
|System.UInt64|ULong|ulong|
|System.Single|Single|float|
|System.Double|Double|double|
|System.Object|Object|object|
|System.Char|Char|char|
|System.String|String|string|
|System.Boolean|Boolean|bool|

Examples:

```csharp
// Define some "ints" in C#.
int i = 0;
System.Int32 j = 0;
```

```vb
' Define some "ints" in VB.
Dim i As Integer = 0
Dim j As System.Int32 = 0
```

> Side Note: These intrinsic types are implemented in both C# and
> VB.NET. In F#, however, types are inferred and are defined somewhat 
> differently.

---
