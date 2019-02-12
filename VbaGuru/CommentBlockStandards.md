
# Comment Blocks - Good v Bad v Ugly

## Serious 1

```vb
'''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''
' ShellAndWait
'
' This function calls Shell and passes to it the command text in ShellCommand. The function
' then waits for TimeOutMs (in milliseconds) to expire.
'
'   Parameters:
'       ShellCommand
'           is the command text to pass to the Shell function.
'
'       TimeOutMs
'           is the number of milliseconds to wait for the shell'd program to wait. If the
'           shell'd program terminates before TimeOutMs has expired, the function returns
'           ShellAndWaitResult.Success = 0. If TimeOutMs expires before the shell'd program
'           terminates, the return value is ShellAndWaitResult.TimeOut = 2.
'
'       ShellWindowState
'           is an item in VbAppWinStyle specifying the window state for the shell'd program.
'
'       BreakKey
'           is an item in ActionOnBreak indicating how to handle the application's cancel key
'           (Ctrl Break). If BreakKey is ActionOnBreak.AbandonWait and the user cancels, the
'           wait is abandoned and the result is ShellAndWaitResult.UserWaitAbandoned = 5.
'           If BreakKey is ActionOnBreak.IgnoreBreak, the cancel key is ignored. If
'           BreakKey is ActionOnBreak.PromptUser, the user is given a ?Continue? message. If the
'           user selects "do not continue", the function returns ShellAndWaitResult.UserBreak = 6.
'           If the user selects "continue", the wait is continued.
'
'   Return values:
'            ShellAndWaitResult.Success = 0
'               indicates the the process completed successfully.
'            ShellAndWaitResult.Failure = 1
'               indicates that the Wait operation failed due to a Windows error.
'            ShellAndWaitResult.TimeOut = 2
'               indicates that the TimeOutMs interval timed out the Wait.
'            ShellAndWaitResult.InvalidParameter = 3
'               indicates that an invalid value was passed to the procedure.
'            ShellAndWaitResult.SysWaitAbandoned = 4
'               indicates that the system abandoned the wait.
'            ShellAndWaitResult.UserWaitAbandoned = 5
'               indicates that the user abandoned the wait via the cancel key (Ctrl+Break).
'               This happens only if BreakKey is set to ActionOnBreak.AbandonWait.
'            ShellAndWaitResult.UserBreak = 6
'               indicates that the user broke out of the wait after being prompted with
'               a ?Continue message. This happens only if BreakKey is set to
'               ActionOnBreak.PromptUser.

'''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''
```

