# Basics of PowerShell 🛠️

In this tutorial, we will cover the basics of PowerShell, including command syntax, variables and data types, working with strings and numbers, and arrays and hash tables.

## 1. Command Syntax

PowerShell commands generally follow the verb-noun syntax. Here's a breakdown:

```
<Verb>-<Noun> [-<Parameter> <Value>]
```

For example:

```powershell
Get-Process
Start-Service -Name "MyService"
```

## 2. Variables and Data Types

PowerShell supports various data types, including integers, strings, arrays, hash tables, and more. To declare a variable, use the `$` symbol followed by the variable name.

```powershell
$myVariable = "Hello, World!"
$myNumber = 42
```

PowerShell automatically assigns data types based on the value assigned to a variable.

## 3. Working with Strings and Numbers

### Strings

Strings in PowerShell can be manipulated using various methods and operators. Here are some examples:

```powershell
$string = "Hello, World!"

# Concatenation
$greeting = "Hello"
$name = "John"
$fullGreeting = $greeting + " " + $name

# Substring
$substring = $string.Substring(0, 5)

# Length
$length = $string.Length
```

### Numbers

PowerShell supports basic arithmetic operations for numbers:

```powershell
$number1 = 10
$number2 = 5

# Addition
$result = $number1 + $number2

# Subtraction
$result = $number1 - $number2

# Multiplication
$result = $number1 * $number2

# Division
$result = $number1 / $number2
```

## 4. Arrays and Hash Tables

### Arrays

Arrays in PowerShell can hold multiple values of different data types.

```powershell
# Creating an array
$myArray = @("apple", "banana", "cherry")

# Accessing elements
$firstElement = $myArray[0]

# Adding elements
$myArray += "orange"

# Length of array
$arrayLength = $myArray.Length
```

### Hash Tables

Hash tables consist of key-value pairs and are useful for storing structured data.

```powershell
# Creating a hash table
$myHashTable = @{
    "Name" = "John";
    "Age" = 30;
    "City" = "New York";
}

# Accessing values
$name = $myHashTable["Name"]

# Adding new key-value pairs
$myHashTable["Job"] = "Developer"

# Removing key-value pairs
$myHashTable.Remove("Age")
```

This concludes our basic tutorial on PowerShell. Practice these concepts to become proficient in PowerShell scripting!
