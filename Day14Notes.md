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

#### **Other Types of Coverage**
- Function Coverage
- Condition Coverage
- Modified Condition / Decision Coverage (MC/DC)
    - Loosely: Function + Branch

**Is it worth maximizing these metrics?**
- Yes - It finds more corner case bugs in practice.

## **Alternative View on Testing**
----
- Bugs experienced by users are the bugs that matter.
- If user-experienced bugs are the ones that matter then testing should be devoted to sampling these inputs.
    - Exhaustive testing is usually too expensive.
- Potential options
    - Uniform random sample
    - Sample from most common
    - Sample from most harmful
- The problem with sampling
    - Bias or error
- Testing gives us confidence the same way sampling or pollion for a survey gives us confidence.
- Sampling Bias - Some members of a population are less likely to be selected.
    - Unrepresentative of that segment of population.
- Solutions to Sampling Bias
    - In stats -> Increase sample size or know something about the distribution.
    - In software Engineering -> We don't know possible distributions.

