# vba.guru - Automated VBA Scan Tools no DATA leaves the organisation

Allow 2 - 4 weeks per agency, multiple Air-Gapped networks are a problem here, probably most value from just scanning the one with the highest user base.


Passwords will be sanitised where obvious.

What Leaves is for aggregate purposes only to provide hard evidence to the Department of Finance to justify a spend on improving office capability.


IDEAL INFORMATION TO COLLECT FROM SCCM/OTHER not strictly for IP audit but helpful in confirming usage.

- List of OS with Bitness eg (x86/x64)
- RAM Size, Hardware Model/VM Ware VDI etc.
- List of Installed Office Versions
- List of Add-Ins per machine, Machine Names ANONYMISED



- List of Files with VBA code in them other files not retained only the count of those files for ratio between files with code and those without.
- Statistics from the Static Analysis of the VBA code files but no actual code leaves.


ALL CODE IS VIEWABLE SOURCE A Mix of VBScripts, PowerShell and VBA as well as the Microsoft Supplied OFFSCAN program.

Workflow:

These code files are introduced to a Virtual or Physical Machine that is provided and a member of your domain.

Some Minor Configuration will be needed of key configuration files.

An existing Administrator will need to run the tool-set, a sample or all files is more than acceptable extrapolation is less accurate than full
file set but will still prove valuable in the trend.



ACQUIRING FILES

INCLUDED FILE EXTENSIONS, ALL OTHERS WILL NOT BE COLLATED.
MINIMUM FILE OF 10 Kb to exclude basically empty/stray file types.

.xls
.xlam
.xlsm
.xltm
.xlsb

.doc
.docm
.dotm

Each File is Copied into a RANDOMLY Pre-Generated Folder Name and Named a RANDOM FILE NAME there is a PreDefined Dictionary list of each
to be used sequentially this will permit the files to all be created in a CENTRAL folder without any collisions.

An Index of the Original File Name and Path will be created but not permitted to leave the organisation.

We then do a SHA1 File Hashing of all files and delete the duplicates for purposes of post processing it will not matter which one is deleted.

We then delete resulting Empty folders.

NEXT PHASE OF CULL

FILE HEADER/TYPE ANALYSIS eg some .CSV files are called .XLS and Excel will open them.
DELETE ALL FILES WITHOUT THE RIGHT HEADERS {2/4/8 BYTE Check}
.XLS Files without Code in Them will be deleted.
.DOC Files without Code in Them will be deleted.
DELETE EMPTY FOLDERS AGAIN

NEXT PHASE IS TO OPEN IN EXCEL each File
.xls
.xlsm
And Delete All Sheets except Sheets that do not contain Code, Remaining Sheets
will Have a ".CLEAR ALL CONTENTS" run to perform Static Code Analysis the code need
not be able to function.

NEXT PHASE IS TO OPEN IN WORD each File
.doc
.docm
And Delete All Sections and PAGES CONTENT to perform Static Code Analysis the code need not be able to function.

For each Office File left we now perform a Series of Operations over the Source Code to assist in the reliability of
the next round of Static Analysis Pattern Parsing.
- JOIN LINES
- CONSISTENT INDENTING
- REMOVE EXCESSIVE WHITE SPACE LINES

We now have a set of unique files to analyse in detail.

We Extract only
- Type References List
- API Functions Used
- Module/Class Object Names
- Procedure/Method Names
- Aggregate Statistics
- Database Connections

and that's it, Code Reliability and Maintainability metrics require human analysis to be reliable and that can be done for files of concern interest as a second phase,
also to make sense of them the DATA and relationships to other files/databases may need to be followed.


