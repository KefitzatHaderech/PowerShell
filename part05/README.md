# File Processing

In this tutorial, we will cover file processing in PowerShell, including reading from and writing to files, working with file attributes, filesystem navigation, and filesystem operations.

## 1. Reading from and Writing to Files

You can easily read from and write to files using PowerShell cmdlets like `Get-Content` and `Set-Content`.

### Reading from a File

```powershell
# Read the content of a file
$content = Get-Content -Path "C:\path\to\file.txt"
Write-Host $content
```

### Writing to a File

```powershell
# Write content to a file
$content = "This is some text to write to the file."
Set-Content -Path "C:\path\to\newfile.txt" -Value $content
```

## 2. Working with File Attributes

PowerShell provides various cmdlets to work with file attributes, such as `Get-Item` and `Set-ItemProperty`.

### Retrieving File Attributes

```powershell
# Get file attributes
$file = Get-Item -Path "C:\path\to\file.txt"
Write-Host "Name: $($file.Name)"
Write-Host "Size: $($file.Length) bytes"
Write-Host "Last Modified: $($file.LastWriteTime)"
```

### Modifying File Attributes

```powershell
# Modify file attributes
$file = Get-Item -Path "C:\path\to\file.txt"
$file.LastWriteTime = Get-Date
```

## 3. Filesystem Navigation

You can navigate through the filesystem using cmdlets like `Get-ChildItem` and `Set-Location`.

### Listing Files and Directories

```powershell
# List files and directories in a directory
Get-ChildItem -Path "C:\path\to\directory"
```

### Changing Current Directory

```powershell
# Change current directory
Set-Location -Path "C:\new\directory"
```

## 4. Filesystem Operations

PowerShell offers various filesystem operations, such as copying, moving, and deleting files and directories.

### Copying Files

```powershell
# Copy a file
Copy-Item -Path "C:\source\file.txt" -Destination "C:\destination\file.txt"
```

### Moving Files

```powershell
# Move a file
Move-Item -Path "C:\source\file.txt" -Destination "C:\destination\file.txt"
```

### Deleting Files

```powershell
# Delete a file
Remove-Item -Path "C:\path\to\file.txt"
```

This concludes our tutorial on file processing in PowerShell. Experiment with these concepts to manage files and directories effectively using PowerShell!
