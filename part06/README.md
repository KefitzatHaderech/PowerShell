# Text Processing Tools

In this tutorial, we will explore various text processing tools available in PowerShell, including `Select-String`, the `-replace` operator, regular expressions (Regex), and formatting output.

## 1. Select-String

`Select-String` cmdlet is used to search through text and return matching lines.

```powershell
# Search for a specific pattern in a file
Select-String -Path "C:\path\to\file.txt" -Pattern "keyword"

# Search recursively in all files in a directory
Select-String -Path "C:\path\to\directory\*" -Pattern "keyword" -Recurse
```

## 2. -replace Operator

The `-replace` operator is used to replace text matching a specified pattern.

```powershell
# Replace a word in a string
$text = "Hello, World!"
$newText = $text -replace "Hello", "Hi"
Write-Host $newText
```

## 3. Regular Expressions (Regex)

Regular expressions are powerful tools for pattern matching. PowerShell supports regex patterns for various text processing tasks.

```powershell
# Using regex with Select-String
Select-String -Path "C:\path\to\file.txt" -Pattern "\b\d{3}\b"

# Using regex with -replace operator
$text = "The quick brown fox jumps over the lazy dog."
$newText = $text -replace "\b\w{5}\b", "*****"
Write-Host $newText
```

## 4. Formatting Output

PowerShell provides various ways to format text output using cmdlets like `Format-Table`, `Format-List`, and `Out-String`.

```powershell
# Format output as a table
Get-Process | Format-Table -Property Name, CPU, Handles

# Format output as a list
Get-Service | Format-List -Property DisplayName, Status

# Convert output to a string
$output = Get-ChildItem | Out-String
Write-Host $output
```

This concludes our tutorial on text processing tools in PowerShell. Practice these techniques to efficiently process and manipulate text data in PowerShell!
