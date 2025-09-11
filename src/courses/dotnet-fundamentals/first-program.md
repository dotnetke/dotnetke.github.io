---
sidebar_position: 2
---

# Your First C# Program

Let's write your very first C# program! In this lesson, you'll create a simple "Hello, Kenya!" application and understand the basic structure of a C# program.

## Creating a New Project

Open your terminal and navigate to where you want to create your project:

```bash
mkdir MyFirstApp
cd MyFirstApp
dotnet new console
```

This creates a new console application with the basic structure.

## Understanding the Code

Let's examine the generated `Program.cs` file:

```csharp
// See https://aka.ms/new-console-template for more information
Console.WriteLine("Hello, World!");
```

This is a minimal C# program that:
1. Uses the `Console` class to output text
2. Calls the `WriteLine` method to print a line of text
3. The text appears in the terminal when you run the program

## Making It Personal

Let's modify the program to make it more relevant to our Kenyan community:

```csharp
Console.WriteLine("Hello, Kenya! 🇰🇪");
Console.WriteLine("Karibu to .NET development!");
Console.WriteLine($"Today is {DateTime.Now:dddd, MMMM dd, yyyy}");

// Let's make it interactive
Console.Write("What's your name? ");
string? name = Console.ReadLine();
Console.WriteLine($"Nice to meet you, {name}!");
Console.WriteLine("Welcome to the .NET Kenya community! 🚀");
```

## Running Your Program

To run your program, use:

```bash
dotnet run
```

You should see output like:
```
Hello, Kenya! 🇰🇪
Karibu to .NET development!
Today is Monday, January 15, 2024
What's your name? 
```

## Understanding the Syntax

Let's break down what we used:

### String Interpolation
```csharp
$"Hello, {name}!"
```
The `$` before the string allows you to embed variables directly using `{}`.

### DateTime Formatting
```csharp
{DateTime.Now:dddd, MMMM dd, yyyy}
```
This formats the current date in a readable format.

### User Input
```csharp
string? name = Console.ReadLine();
```
`Console.ReadLine()` gets input from the user. The `?` indicates the variable can be null.

## Exercise: Personal Greeting App

Create a program that:
1. Asks for the user's name
2. Asks for their favorite programming language
3. Tells them how .NET compares to their favorite language
4. Displays a personalized welcome message

## Sample Solution

```csharp
Console.WriteLine("Welcome to .NET Kenya! 🇰🇪");
Console.WriteLine("Let's get to know you better...\n");

Console.Write("What's your name? ");
string? name = Console.ReadLine();

Console.Write("What's your favorite programming language? ");
string? favLanguage = Console.ReadLine();

Console.WriteLine($"\nHello {name}!");
Console.WriteLine($"That's great that you like {favLanguage}!");
Console.WriteLine("You'll find that C# shares many concepts with other languages,");
Console.WriteLine("but with powerful features like:");
Console.WriteLine("• Strong typing");
Console.WriteLine("• Cross-platform development");
Console.WriteLine("• Rich standard library");
Console.WriteLine("• Great tooling and community support");
Console.WriteLine($"\nWelcome to your .NET journey, {name}! 🚀");
```

## What's Next?

In the next lesson, we'll explore:
- Variables and data types
- Basic operations
- Control structures (if/else, loops)

Great job on creating your first C# program! 🎉