# acsindent
Tool to automatically indent ACS routines.

Usage:
  1. Include the REXX file in your SYSPROC concatenation
  2. In ISPF edit, issue command ACSIND

Formatting information:
- Indents after DO, unindents after END
- Right-justifies in-line comments
- Converts block comments to one-line comments  
- If comment and indented code do not fit on one line, moves the comment to the line before 
- Lines up FILTLIST lines based on where INCLUDE or EXCLUDE starts  
- Does NOT auto-indent after IF or WHEN 
- Auto-indents after SELECT
- Will not indent the line off the page.. Pulls line back to where it fits

For Best Formatting results, code the following:
- For IF and WHEN lines, either include the resulting statement on the same line, or use a DO. 
  - Examples:
    a.) IF(&DSN(2)=MYSTUFF*) THEN SET &DATACLAS='MINE'
    b.) IF(&DSN(2)=MYSTUFF*) THEN DO
          SET &DATACLAS='MINE'
        END
- Keep in-line comments short, or put them on their own line

Author: Neal Bohling / bohling@us.ibm.com
This is an as-is tool! No support is implied or guaranteed.
Feel free to make changes and update the tool. If you make significant improvements, I'd like to see them! 
