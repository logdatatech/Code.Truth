
# Open Two Instances of Excel.exe

## Why

Short Version is Instance 1 when running macro code, may become unresponsive and you may also want to restrict User Interactivity for some actions.

This means Instance 2 can still be responsive, and if you manage to crash your instance 2 it will not impact Instance 1
 
## How ?

> FIXME: Looks like this only Works on Windows 7 on Windows 10 with Office 2016 can't get this to work.

Pin Excel Shortcut to Start Menu

Right Click and Open Shortcut

Click on Excel Icon



Check you Have Different PID (process ID’s)

from a Command Prompt

```batch
tasklist /FI "IMAGENAME eq EXCEL.EXE"
```

If you only have 1 Instance Listed then it has not worked.


