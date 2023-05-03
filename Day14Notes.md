# **Lecture 14 Notes, 3/6/23**

## **Test Suite Quality Metrics**
----
- Determine "how good" a test suite is compared to another test suite.
- Higher quality test suite -> greater confidence in code.

#### Defintion
**Line Coverage** is one possible measurement that looks at statements that are executed as all tests are run.
- Coverage libraries will instrument the code to collect the data.
- What is wrong with line coverage?
    - Covering all lines ≠ finding all bugs.
    - Implicit control flow -> Code with hidden if statements.

#### Definition
**Interesting Tests** are those that trigger both implicit and explicit control flow changes.
- Cause different branches to execute.

#### Definition
**Branch Coverage**: Count the total number of conditional branches exercised by a test suite.
- Count each outcome of an if statement seperately.
- 100% branch coverage typically implies 100% line coverage.
- Branch coverage subsumes line coverage.
    - Comes at a cost: branch coverage is "more expensive" in that it is harder for a test suite to house high branch voverage than it is to have high line coverage.
