
# Project Analyzer sample macros

## NOTE Enterprise Edition only

Simple Problem report example
This example analyzes a project, generates the problem report, shows the report and closes Project Analyzer.

```vb
' Analyze myproj.vbproj 
' in the Release configuration
Analyze "myproj.vbproj" Release

' Set reports to a text file report.txt.
' Delete any existing file.
SetReport txt "report.txt" DELETEOLD

' Use the <Default> problem filter and
' generate a Problem report
ProbFilter <Default>
Report Problems

' Open the report with Notepad 
' or other configured editor
OpenReport

' Close Project Analyzer
Quit
```

Master-child macro example
This example uses two files, Analyze.pam and Report.pam. You execute Analyze.pam which in turn includes the commands defined in Report.pam. If you have two or more projects, you could write a master macro for each project and include the same Report.pam in all of them. This way you can put common actions in the child macro and project specific actions in the master macros.

Analyze.pam
```vb
' Write all actions in a log file
Log "analyze.log"

' Analyze a project
Analyze "myproject.vbp"

' Run the commands in report.pam
Include "report.pam"
```

Report.pam

```vb
' Generic reporting macro for all projects

' Save Project Metrics in a new database
SaveMTX

' Generate a project web site in 
' sub-directory "projectsite"
ProjectPrinter htmlsite "projectsite"

' Select the html report type, 
' auto-pick the report filename 
' (in the same folder as Analyze.pam)
SetReport html

' Run duplicate code analysis
FindDuplicateCode 10 IGNORECOMMENTS

' Generate Summary report
Report Summary

' Open the reports 
' (Find duplicate code and Summary)
OpenReport
```

---
