# Functions

In this tutorial, we will cover the fundamentals of functions in PowerShell, including creating functions, working with parameters and arguments, handling return values, and understanding function scope.

## 1. Creating Functions

Functions in PowerShell allow you to encapsulate a block of code for reuse. Here's how you can create a simple function:

```powershell
function SayHello {
    Write-Host "Hello, World!"
}

# Call the function
SayHello
```

## 2. Parameters and Arguments

Parameters allow you to pass values to a function. You can define parameters when creating a function and pass arguments when calling it.

```powershell
function Greet {
    param (
        [string]$name
    )
  
    Write-Host "Hello, $name!"
}

# Call the function with an argument
Greet -name "John"
```

## 3. Return Values

Functions can return values using the `return` keyword. You can return any data type, such as strings, numbers, arrays, or hash tables.

```powershell
function AddNumbers {
    param (
        [int]$num1,
        [int]$num2
    )
  
    return ($num1 + $num2)
}

# Call the function and store the result
$result = AddNumbers -num1 10 -num2 5
Write-Host "Result: $result"
```

## 4. Function Scope

Variables declared inside a function have local scope, meaning they are only accessible within that function. Variables declared outside a function have global scope.

```powershell
$globalVariable = "I am global"

function TestScope {
    $localVariable = "I am local"
    Write-Host "Inside function: $localVariable"
    Write-Host "Inside function (global): $globalVariable"
}

# Call the function
TestScope

# Try to access local variable outside the function (will throw an error)
Write-Host "Outside function: $localVariable"
```

This concludes our tutorial on functions in PowerShell. Practice these concepts to become proficient in PowerShell scripting!
