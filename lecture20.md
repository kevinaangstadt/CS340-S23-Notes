# Notes Lecture 20
# 4/3/2023

Quick Summary of class 19: 
- fault localization - implicating lines of code in a bug/fault/defect
- techniques:
    - add print statements -> detect where code is reaching, risk of
      flushing output buffers
    - using debugger

Code Tracing
- Problem of scale in big code bases

Instead, write script that can help with this
Automatically filter using coverage to minimize lines of code to analyze
Bug will be in covered lines
 - deprioritize passing test coverage
 - prioritize failing test coverage

 Class 20:
 Example of writing a tool that can help us with automitcally filter bugs.
 Wrote Python script that can run unittest and calculate coverage 
 and weight. 

Looked at a commit we knew had a bug but all tests were passing
    - verified defect by creating test that will expose bug
    - Checked out test file from commit that fixed the bug
    - ran unittest again, failed!
    - Looked at stacktrace, had a format error.

 We will write localize.py which can run on any python program
 and unitest.
  - GOAL: Localize which line the bug is on using our program

 Handling command lines using argparse, similar to GetOpt in Java
 
