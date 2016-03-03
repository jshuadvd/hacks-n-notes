# From JS to C# #

> A guide for JavaScript developers who want to understand C#

These notes are from a perspective of a JavaScript developer. I am trying to understand the similarities and differences between JavaScript (JS) and C#.

## Dictionary

A Dictionary is like storing key and values in an object literal example:

```javascript
var colorValues = {
  "blue": "#00F",
  "red": "#F00"
}
```

The difference is that in JavaScript the key is always a string and you can have different type of objects in the same dictionary. 

> Note: In C# the key types are mostly *strings* or *ints*. I wonder if there is any other type useful for a Dictionary. I could think of *Enums*.

JS Arrays are like C# Dictionaries with key-value type of int.

## HashSet
This looks like a *List* but it is un-ordered and has better performance. It would be like a JS Array but instead of *Int* key types it uses unique *enums*.

## Anonymous Types
They look somewhat similar to JS literal objects and they work similar but they are commonly used for *LINQ* notation or similar.

Example of anonymous types from [MSDN](https://msdn.microsoft.com/en-us/library/bb397696.aspx)

```C#
var v = new { Amount = 108, Message = "Hello" };

Console.WriteLine(v.Amount + v.Message);
```

## Lists
Lists are a wrapper on Array to make it usable as the JS Array.



## Classes

### Static Classes

C# Static classes are like JS Object literals. They can't be instantiated, but the methods are usable.

eg. of a C# class in JS

```javascript
const MathFunctions = {
  sumToNumbers (num1, num2) {
    return num1 + num2;
  }
}
```

### Sealed Classes

> Sealed classes are not inherited by any class but can be instantiated.

- Sealed classes can help keep the code shallow and simple. That is good to avoid the *gorrilla-banana* problem.

---

## ReSharper
> helper tool for Visual Studio

You can interact with ReSharper config by commenting with the keyword **ReSharper** 
eg. ` // ReSharper disable once PossibleInvalidOperationException`

## #Pragma

> `#pragma` gives the compiler special instructions for the compilation of the file in which appears. The instructinos must be supported by the compiler. In other words, you cannot use `#pragma` to create custom preprocessing instructions.

The Microsoft C# compiler supports:

- `#pragma warning`
- `#pragma checksum`

## Dependencies

> Files in a project have access to all the dependencies declared in *.csproj*

- the keyword `using` is like import, which will bring into *csproj* a determined dependency.
- 

## [Operators](https://msdn.microsoft.com/en-us/library/a1sway8w.aspx)

### Left-shift operator `<<`
> bit-shift operation

## Architecture

### Entry point
> `Main()` is a static method that serves as an entry point for a C# app and normally lives in a file named **Program.cs**

### AssemblyInfo
> Provides properties for getting the information about the application, such as the version number, description, loaded assemblies, and so on.

