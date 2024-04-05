# Advanced Text Processing

In this tutorial, we'll delve into advanced text processing techniques in PowerShell. We'll cover using the `-split` operator, string manipulation, parsing text files, and working with XML and JSON data.

## 1. Using -split Operator

The `-split` operator is used to split a string into substrings based on a delimiter.

```powershell
# Split a string into an array based on whitespace
$string = "Hello World"
$words = $string -split " "
Write-Host $words[0]  # Output: Hello
Write-Host $words[1]  # Output: World
```

## 2. String Manipulation

PowerShell provides various methods and operators for string manipulation, such as concatenation, substring extraction, and string formatting.

```powershell
# Concatenation
$greeting = "Hello"
$name = "John"
$fullGreeting = "$greeting, $name!"
Write-Host $fullGreeting  # Output: Hello, John!

# Substring
$string = "Hello World"
$substring = $string.Substring(0, 5)
Write-Host $substring  # Output: Hello
```

## 3. Parsing Text Files

PowerShell allows parsing text files line by line, extracting relevant information as needed.

```powershell
# Read a text file line by line
Get-Content -Path "C:\path\to\file.txt" | ForEach-Object {
    if ($_ -match "pattern") {
        Write-Host $_
    }
}
```

## 4. Working with XML and JSON

PowerShell provides cmdlets to parse and manipulate XML and JSON data.

### XML

```powershell
# Parse XML from a file
$xml = [xml](Get-Content -Path "C:\path\to\data.xml")

# Access elements
$name = $xml.Root.ElementName
$value = $xml.Root.ElementValue
```

### JSON

```powershell
# Parse JSON from a file
$json = Get-Content -Path "C:\path\to\data.json" | ConvertFrom-Json

# Access properties
$name = $json.PropertyName
$value = $json.PropertyValue
```

This concludes our tutorial on advanced text processing in PowerShell. Experiment with these techniques to efficiently handle and manipulate text data in your PowerShell scripts!
