# Introduction to PowerShell

## What is PowerShell? ❓

PowerShell is a powerful scripting language and command-line shell developed by Microsoft for task automation and configuration management. It is built on the .NET framework and initially released in 2006. PowerShell provides a command-line interface (CLI) where users can execute commands, called cmdlets, to perform various tasks. It combines the flexibility of scripting languages like Python with the power of the Windows operating system.

## Why PowerShell for Scripting? 🚀

There are several reasons why PowerShell is a preferred choice for scripting:

1. **Integration with Windows**: PowerShell is tightly integrated with the Windows operating system, providing access to a wide range of system management functions and APIs. This makes it an ideal choice for automating administrative tasks on Windows servers and workstations.
2. **Object-Oriented Pipeline**: PowerShell uses an object-oriented pipeline, allowing the output of one cmdlet to be passed as input to another cmdlet. This enables complex data manipulation and processing with simple and concise commands.
3. **Rich Standard Library**: PowerShell comes with a rich standard library of cmdlets for managing various aspects of the Windows environment, such as file system, registry, services, processes, and more. Additionally, it supports modules that extend its functionality further.
4. **.NET Integration**: Since PowerShell is built on the .NET framework, it seamlessly integrates with other .NET languages and libraries, allowing developers to leverage existing .NET code within PowerShell scripts.
5. **Cross-Platform Support**: While PowerShell was initially designed for Windows, Microsoft has made efforts to expand its support to other platforms. PowerShell Core is a cross-platform version of PowerShell that runs on macOS, Linux, and Windows, making it versatile for managing heterogeneous environments.

## PowerShell vs. Command Prompt 🔄

While both PowerShell and Command Prompt are command-line interfaces available on Windows, they have significant differences:

### PowerShell:

- **Object-Oriented**: PowerShell operates on objects rather than plain text, allowing for richer data manipulation and processing.
- **Scripting Language**: PowerShell is a full-fledged scripting language with support for variables, loops, conditional statements, functions, and error handling.
- **Extensibility**: PowerShell can be extended with custom cmdlets, scripts, and modules, providing flexibility and scalability.
- **.NET Integration**: PowerShell is built on the .NET framework, enabling seamless integration with .NET libraries and languages.
- **Cross-Platform**: PowerShell Core is cross-platform, allowing it to run on macOS, Linux, and Windows.

### Command Prompt:

- **Text-Based**: Command Prompt operates primarily on plain text input and output, limiting its ability to process complex data structures.
- **Limited Scripting Capabilities**: While Command Prompt supports batch scripting with batch files (.bat), it lacks many features found in modern scripting languages like PowerShell.
- **Command Syntax**: Command Prompt uses commands and utilities with simple syntax, often based on legacy conventions.
- **Windows-Centric**: Command Prompt is tightly integrated with Windows and lacks native support for other platforms.
- **Legacy Support**: Command Prompt maintains compatibility with older Windows applications and workflows.

## Code Snippets:

### PowerShell Example:

```powershell
# Get a list of running processes sorted by memory usage
Get-Process | Sort-Object -Property WorkingSet -Descending

# Create a new directory and change into it
New-Item -ItemType Directory -Path "C:\Example"
Set-Location -Path "C:\Example"

# Get help for a cmdlet
Get-Help Get-Process
```

### Command Prompt Example:

```batch
REM Display a directory listing
dir /b

REM Create a new directory
mkdir C:\Example

REM Change into the new directory
cd C:\Example

REM Display help for a command
help dir
```

In conclusion, PowerShell provides a robust and versatile environment for scripting and automation on Windows and beyond. While Command Prompt remains a staple for many Windows users, PowerShell offers enhanced capabilities and flexibility, making it a preferred choice for modern scripting tasks.

## Same Example

Let's create a complex example for both PowerShell and Command Prompt to showcase their capabilities.

### PowerShell Complex Example:

```powershell
# This PowerShell script retrieves a list of processes, filters out system processes,
# calculates the average CPU and memory usage, and exports the results to a CSV file.

# Get a list of all processes
$processes = Get-Process

# Filter out system processes
$filteredProcesses = $processes | Where-Object { $_.Name -notlike "System*" }

# Calculate average CPU and memory usage
$avgCPU = ($filteredProcesses | Measure-Object -Property CPU -Average).Average
$avgMemory = ($filteredProcesses | Measure-Object -Property WorkingSet -Average).Average

# Create a custom object to store the results
$results = [PSCustomObject]@{
    AverageCPU = $avgCPU
    AverageMemory = $avgMemory
}

# Export results to a CSV file
$results | Export-Csv -Path "C:\ProcessStats.csv" -NoTypeInformation

Write-Host "Process statistics exported to C:\ProcessStats.csv"
```

### Command Prompt Complex Example:

```batch
REM This batch script retrieves a list of running processes, filters out system processes,
REM calculates the average CPU and memory usage, and exports the results to a CSV file.

@echo off
setlocal enabledelayedexpansion

REM Get list of running processes
tasklist /fo csv /nh > temp.csv

REM Filter out system processes
for /f "tokens=1,2,3,4,5,6,7,8,9,10 delims=," %%a in (temp.csv) do (
    set "name=%%a"
    set "pid=%%b"
    set "session=%%c"
    set "sessionName=%%d"
    set "memUsage=%%e"
    set "status=%%f"
    set "username=%%g"
    set "cpuTime=%%h"
    set "windowTitle=%%i"
  
    REM Check if the process name doesn't start with "System"
    if "!name:~0,6!" neq "System" (
        echo !name!,!pid!,!session!,!sessionName!,!memUsage!,!status!,!username!,!cpuTime!,!windowTitle! >> filtered.csv
    )
)

REM Calculate average CPU and memory usage
set "totalCPU=0"
set "totalMemory=0"
set "count=0"

for /f "tokens=5 delims=," %%a in (filtered.csv) do (
    set /a totalMemory+=%%a
    set /a count+=1
)

set /a avgMemory=totalMemory/count

echo Average Memory Usage: %avgMemory% KB

REM Export results to a CSV file
echo AverageMemory,%avgMemory% KB > ProcessStats.csv
echo Process statistics exported to ProcessStats.csv

REM Clean up temporary files
del temp.csv
del filtered.csv
```

In this example, both PowerShell and Command Prompt scripts retrieve a list of running processes, filter out system processes, calculate the average CPU and memory usage, and export the results to a CSV file. This showcases the capabilities of both scripting environments for complex tasks.
