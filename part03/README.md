# Conditions and Loops ⚙️

In this tutorial, we will cover conditions and loops in PowerShell, including if...else statements, switch statements, and various types of loops.

## 1. If...Else Statements

If...else statements are used to execute different code blocks based on certain conditions.

```powershell
$age = 25

if ($age -ge 18) {
    Write-Host "You are an adult."
} else {
    Write-Host "You are a minor."
}
```

## 2. Switch Statements

Switch statements are useful when you have multiple conditions to evaluate.

```powershell
$fruit = "apple"

switch ($fruit) {
    "apple" {
        Write-Host "It's an apple."
    }
    "banana" {
        Write-Host "It's a banana."
    }
    Default {
        Write-Host "Unknown fruit."
    }
}
```

## 3. For, ForEach, and While Loops

### For Loop

For loops are used to iterate a specific number of times.

```powershell
for ($i = 1; $i -le 5; $i++) {
    Write-Host "Iteration $i"
}
```

### ForEach Loop

ForEach loops iterate through each item in a collection.

```powershell
$fruits = @("apple", "banana", "cherry")

foreach ($fruit in $fruits) {
    Write-Host "Current fruit: $fruit"
}
```

### While Loop

While loops continue to execute a block of code while a specified condition is true.

```powershell
$count = 1

while ($count -le 5) {
    Write-Host "Count: $count"
    $count++
}
```

## 4. Break and Continue Statements

### Break Statement

Break statement is used to exit a loop prematurely.

```powershell
for ($i = 1; $i -le 10; $i++) {
    if ($i -eq 5) {
        Write-Host "Reached 5. Exiting loop."
        break
    }
    Write-Host "Current value: $i"
}
```

### Continue Statement

Continue statement skips the remaining code in the loop and moves to the next iteration.

```powershell
for ($i = 1; $i -le 5; $i++) {
    if ($i -eq 3) {
        Write-Host "Skipping 3."
        continue
    }
    Write-Host "Current value: $i"
}
```

This concludes our tutorial on conditions and loops in PowerShell. Experiment with these concepts to gain proficiency in PowerShell scripting!
