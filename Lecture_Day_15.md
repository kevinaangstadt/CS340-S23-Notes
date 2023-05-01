Lecture day 15

Soko Taonga

INTRODUCTION
The point of tests is to reveal and prevent bugs
Mutation Testing → Seed defects in the code and check which tests reveal the defects
How do we seed these defects?
 Change && —> | | —> —		(Make changes to parts of the program)
-Manually seed defects
-Easy to do
-Time consuming
-Potential for bias

-Automatically seed defects → Script/program to modify a program’s source code to seed defects. 
Mutation operators → templates for replacing code
(i) if (a < b) → if (a <= b)
(ii) if (a == b) → if (a |= b)
(iii) a = b + c → a = b - c
(iv) f(); g(); → g(); f();
(v) x = y  → y = x;
-Programs can be represented by trees → Abstract Syntax Trees (ASTs)
-After we apply a mutation operator, we have a mutant or variant of the project
- The order is the # of mo applied to a program

MAIN BODY
What does it mean if a variant is not detected by the test suite
-Test suite is not good?
-Mutant is actually semantics preserving (did not change the outcome of the program) →equivalent mutant programs that are semantically identical and this pass/fail same # of tests
-This idea of automatically mutating software is based on the competent programmer hypothesis: faults are syntactically small and can be corrected with a few keystrokes
NB: But - not all bugs are small!
Coupling effect hypothesis →Complex faults are combinations of small faults (high order mutant)
What are the drawbacks with  MT?
Make 1000 mutants
Run test suite against each mutant
Record % detected
Very expensive → run the whole suite 1000 times → more targeted testing
The Story so far…
1.	Scripting → automate tasks
2.	Version Control → collaborate and track changes in software
3.	Testing → gain confidence/assure quality

We want to automate all of the processes needed to take code from commits and move it into production
Production: code being run by uses.
The automated infinity loop lifecycle is called Continuous Integration/ Continuous Delivery CI/CD
Continuous Integration
-Practice of integrating code changes into the main branch of a shaped repository often automatically testing each change on both commits and merges, and automatically building each version .
-Push multiple times a day/ merge rebase into the main branch
-Encourages best practices with commits
-Reduce # of long lived branches 
-Reduce merge  conflicts     →PR and code review
-The main branch should always be working

CONCLUSION
Benefits of CI
Reverts are not costly - only a few changes 
Integration bugs are detected early
No “merge day”
Always have “current” version of the code that is built
Immediate feedback or system guide impacts
Continuous Delivery
Process of frequently generating exports / builds of code from the repository that are ready to be deployed.
(Implement → merge → validate )  —>  CI
(Deploy to pre-prod → Spot checks → Deploy to prod) → CD
This is a pipeline → Once a version of the source enters the pipeline, it is held constant until deployment
Version stays the same even if we continue to make commits
Continuous Deployment → automatically publishing/deployment to production (less common)
