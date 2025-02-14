## The Common Type System

In the world of .NET, type is simply a general term used to refer to 
a member from the set `{class, interface, structure, enumeration, 
delegate}`.

The CTS is a formal specification that documents how types must be 
defined in order to be hosted by the .NET Runtime.

ALthough delving into the inner workings of the CTS is beyond the
scope of this training, it's important to understand the five types
defined in the CTS and how to use them in C#.

CTS Types:

* Class
* Interface
* Structure
* Enumeration
* Delegate

---

### CTS Class Type

The class is the primary building-block of OOP (object-oriented 
programming). A class can contain any number of members and fields.

CTS Class Characteristics:

|Characteristic|Meaning|
|-|-|
|Is the class sealed?|A sealed class cannot be inherited from|
|Does it implement an interface?|Interfaces are collections of abstract members that provide a contract between object and user|
|Is it abstract?|Abstract classes cannot be instantiated|
|What is its visibility?|The visibility of a class is determined by the access modifier|
|||

In C#, we identify a class using the `class` keyword.

Example:

```csharp
// A C# class type with 1 method.
class Calc
{
    public int Add(int addend1, int addend2)
    {
        return addend1 + addend2;
    }
}
```

---

### CTS Interface Type

Interfaces are named collections of abstract members and/or default
implementations (in C#8+) which must be implemented by a class.

Interfaces are used to provide a contract between an object and its
user (typically a class that implements the interface).

In C#, we identify an interface using the `interface` keyword.

Example:

```csharp
// A C# interface type is usually
// declared as public, to allow types in other
// assemblies to implement their behavior.
public interface IDraw
{
    void Draw();
}
```

Clearly, that isn't much use on its own, since the `Draw` method
doesn't do anything.

However, if a class implements the `IDraw` interface, it must provide
an implementation of the `Draw` method.

Example:

```csharp
// A C# Class that implements the IDraw interface.
class Shape : IDraw
{
    public void Draw()
    {
        // Code to draw the shape.
    }
}
```

---

### CTS Structure Type

If you have ever worked with pre-OOP languages like C (or even with 
some modern languages like Rust), you're probably familiar with 
structures.

In C#, structures are similar to classes, but they have value-based 
semantics, meaning that like value types, they are stored on the 
stack, whereas reference types (like classes) are stored on the heap.

Structures are used to group together related data similarly to 
classes.

In C#, we identify a structure using the `struct` keyword.

Example:

```csharp
// A C# structure type.
struct Point
{
    // Structures can contain fields.
    public int xPos, yPos;

    // Structures can contain parameterized constructors.
    public Point(int x, int y)
    {
        xPos = x;
        yPos = y;
    }

    // Structures may define methods.
    public void PrintPosition()
    {
        Console.WriteLine("({0}, {1})", xPos, yPos);
    }
}
```

---

### CTS Enumeration Type

Enumerations are a handy programming construct that allow you to 
group name-value pairs.

By default, the underlying type of an enumeration is `int` (`Int32`),
but you can change that to any integer type.

In C#, we identify an enumeration using the `enum` keyword.

Example:

```csharp
// A C# enumeration type.
enum CharacterTypeEnum
{
    Wizard = 100,
    Fighter = 200,
    Thief = 300
}
```

---

### CTS Delegate Type

A delegate is the equivalent of a function pointer in C. The
delegate allows a function to be assigned to a variable (or used
anonymously where a variable might be used).

In C#, we identify a delegate using the `delegate` keyword.

Example:

```csharp
// This C# delegate type can "point to" any method
// returning an int and taking two ints as input.
delegate int BinaryOp(int x, int y);
```

---
