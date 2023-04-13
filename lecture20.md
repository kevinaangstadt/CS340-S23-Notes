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
