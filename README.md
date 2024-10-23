# 🚀 PowerShell Quick Reference Guide

<div align="center">
  
![PowerShell Logo](https://raw.githubusercontent.com/PowerShell/PowerShell/master/assets/ps_black_128.svg)

[![Made with Love](https://img.shields.io/badge/Made%20with-❤-red.svg)]()
[![PowerShell](https://img.shields.io/badge/PowerShell-5.1+-blue.svg)]()
[![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20Linux%20%7C%20macOS-lightgrey.svg)]()

</div>

## 📋 Table of Contents
- [Basic Commands](#basic-commands)
- [File System Operations](#file-system-operations)
- [Process Management](#process-management)
- [Network Operations](#network-operations)
- [Variables and Data Types](#variables-and-data-types)
- [Flow Control](#flow-control)
- [Functions and Modules](#functions-and-modules)
- [Error Handling](#error-handling)
- [Best Practices](#best-practices)

## 🎯 Basic Commands
### System Information
```powershell
# Get System Information
Get-ComputerInfo

# Get PowerShell Version
$PSVersionTable

# Get Current Location
Get-Location    # or pwd
```

### Help System
```powershell
# Get help for a command
Get-Help Get-Process
Get-Help Get-Process -Examples
Get-Help Get-Process -Detailed
Get-Help Get-Process -Full

# Update help documentation
Update-Help
```

## 📂 File System Operations
### Directory Operations
```powershell
# Navigate directories
Set-Location path\to\directory    # or cd
Get-Location                      # or pwd

# Create/Remove directories
New-Item -ItemType Directory -Path "NewFolder"
Remove-Item -Path "FolderToDelete" -Recurse

# List items
Get-ChildItem    # or dir or ls
Get-ChildItem -Path C:\ -Recurse -Filter *.txt
```

### File Operations
```powershell
# Create/Delete files
New-Item -ItemType File -Path "test.txt"
Remove-Item "file.txt"

# Copy/Move files
Copy-Item "source.txt" -Destination "dest.txt"
Move-Item "old.txt" "new.txt"

# Read/Write files
Get-Content "file.txt"
Set-Content "file.txt" "New content"
Add-Content "file.txt" "Appended content"
```

## 🔄 Process Management
```powershell
# List all processes
Get-Process

# Start a new process
Start-Process notepad.exe

# Stop a process
Stop-Process -Name "notepad"
Stop-Process -Id 1234

# Get service status
Get-Service
```

## 🌐 Network Operations
```powershell
# Test network connection
Test-NetConnection google.com
Test-NetConnection -ComputerName server01 -Port 80

# Get IP configuration
Get-NetIPConfiguration
Get-NetAdapter

# Download file from internet
Invoke-WebRequest -Uri "https://example.com/file.zip" -OutFile "file.zip"
```

## 📊 Variables and Data Types
```powershell
# Variable declaration
$name = "John"
$age = 30
$isActive = $true
$numbers = @(1, 2, 3, 4, 5)
$hash = @{
    Key1 = "Value1"
    Key2 = "Value2"
}

# Type casting
[int]"123"
[string]256
[datetime]"2024-01-01"
```

## 🔀 Flow Control
### Conditionals
```powershell
# If statement
if ($age -gt 18) {
    "Adult"
} elseif ($age -eq 18) {
    "Just turned adult"
} else {
    "Minor"
}

# Switch statement
switch ($value) {
    1 { "One" }
    2 { "Two" }
    default { "Other" }
}
```

### Loops
```powershell
# ForEach loop
foreach ($item in $collection) {
    $item
}

# For loop
for ($i = 0; $i -lt 5; $i++) {
    "Iteration $i"
}

# While loop
while ($condition) {
    # code
}
```

## 📦 Functions and Modules
```powershell
# Function definition
function Get-Square {
    param(
        [Parameter(Mandatory=$true)]
        [int]$Number
    )
    return $Number * $Number
}

# Module operations
Get-Module -ListAvailable
Import-Module ModuleName
Get-Command -Module ModuleName
```

## ⚠️ Error Handling
```powershell
# Try-Catch block
try {
    # Risky operation
    $result = 1/0
} catch {
    Write-Error "An error occurred: $_"
} finally {
    # Cleanup code
}

# Error preference
$ErrorActionPreference = "Stop"    # or "Continue", "SilentlyContinue"
```

## 💡 Best Practices

### Code Style
- Use approved verbs for function names (Get-, Set-, New-, Remove-, etc.)
- Follow consistent naming conventions (PascalCase for functions, camelCase for variables)
- Add comments for complex operations
- Use proper indentation and spacing

### Performance
- Use pipeline operations when possible
- Avoid unnecessary type conversions
- Use proper filtering at the source
- Consider using background jobs for long-running operations

### Security
- Always validate input
- Use secure string for sensitive data
- Follow principle of least privilege
- Implement proper error handling

## 📚 Additional Resources

- [Official PowerShell Documentation](https://docs.microsoft.com/en-us/powershell/)
- [PowerShell Gallery](https://www.powershellgallery.com/)
- [PowerShell Community](https://discord.gg/powershell)

## 📄 License

This quick reference guide is released under the MIT License. Feel free to use, modify, and distribute as needed.

---
<div align="center">
Made with ❤️ by Selam
</div>
