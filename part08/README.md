# Process Control

In this tutorial, we'll explore process control in PowerShell, including starting and stopping processes, managing services, monitoring processes, and controlling jobs.

## 1. Start-Process and Stop-Process

The `Start-Process` cmdlet is used to start a new process, and `Stop-Process` is used to stop one or more running processes.

### Starting a Process

```powershell
# Start a new process
Start-Process -FilePath "notepad.exe"
```

### Stopping a Process

```powershell
# Stop a process by name
Stop-Process -Name "notepad"

# Stop a process by process ID
Stop-Process -Id 1234
```

## 2. Working with Services

PowerShell provides cmdlets to manage services, such as `Get-Service`, `Start-Service`, `Stop-Service`, and `Restart-Service`.

```powershell
# Get a list of all services
Get-Service

# Start a service
Start-Service -Name "MyService"

# Stop a service
Stop-Service -Name "MyService"
```

## 3. Process Monitoring

You can monitor running processes using cmdlets like `Get-Process` and `Wait-Process`.

```powershell
# Get a list of running processes
Get-Process

# Wait for a process to exit
Wait-Process -Name "notepad"
```

## 4. Job Control

PowerShell allows you to run background jobs asynchronously using `Start-Job`, `Get-Job`, `Wait-Job`, and `Receive-Job`.

```powershell
# Start a background job
Start-Job -ScriptBlock { Get-Process }

# Get a list of running jobs
Get-Job

# Wait for a job to complete
Wait-Job -Id 1

# Retrieve results from a completed job
Receive-Job -Id 1
```

This concludes our tutorial on process control in PowerShell. With these commands, you can effectively manage processes, services, and jobs within your PowerShell scripts. Experiment with these commands to automate your process management tasks efficiently!
