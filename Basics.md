- Values Types: 
https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/value-types-table
- Reference Types: 
https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/reference-types



Hello World
```c#
using System;
class Hello
{
    static void Main()
    {
        Console.WriteLine("Hello, World");
    }
}
```
Statements
https://docs.microsoft.com/en-us/dotnet/csharp/tour-of-csharp/statements

Declarations
```c#
static void Declarations(string[] args)
{
    int a;
    int b = 2, c = 3;
    a = 1;
    Console.WriteLine(a + b + c);
}
```
If statement
```c#
static void IfStatement(string[] args)
{
    if (args.Length == 0)
    {
        Console.WriteLine("No arguments");
    }
    else 
    {
        Console.WriteLine("One or more arguments");
    }
}
```
While
```c#
static void WhileStatement(string[] args)
{
    int i = 0;
    while (i < args.Length) 
    {
        Console.WriteLine(args[i]);
        i++;
    }
}
```
For
```c#
static void ForStatement(string[] args)
{
    for (int i = 0; i < args.Length; i++) 
    {
        Console.WriteLine(args[i]);
    }
}
```
Foreach
```c#
static void ForEachStatement(string[] args)
{
    foreach (string s in args) 
    {
        Console.WriteLine(s);
    }
}
```
