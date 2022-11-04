# Process Listings

Process listings can be listed using the following commands in windows:

## Basic Task List

```
tasklist /v
```

## WMIC

```
wmic process list
wmic process list brief
wmic process get name, parentprocessid, processid, executablepath 
```

## PowerShell

```
Get-Process
Get-Process -IncludeUserName
Get-Process -FileVersionInfo
```

## Remote Tasklist

```
tasklist /s X.X.X.X /u <username>
```
 