# Software Design
### *Lecture 24, 04/17/2023*
&nbsp;
## **Overview**
In lecture 24, we started thinking about software design and software design patterns. Diving into how we can design software to fit certain aspects of software development such as code review or maintainability.
___
&nbsp;
## What's the idea here?
70% to 90% of time in software development is spent on maintenance tasks. So, if you want to optimize your process of developing software to help you write new software faster, the maximum "speedup" or "imporvement" you can get is only 30%. But, we can design software to make a certain stage in the development lifecycle faster. This follows Amdahl's Law:
- [Amdahl's Law](https://en.wikipedia.org/wiki/Amdahl%27s_law) is the formula which gives the theoretical speedup of the execution of a task at fixed workload that can be expected of a system whose resources are improved.
## Design for Code Review
Since code review is reliant on code comprehension and readability, what are some things we can do to help?
- Avoid long lines of code.
- Reduce the number of variables in a region of code.
- Ensure to follow common naming patterns, for example:
  - CamelCase (java).
  - Snake_case (python).
  - Hungarian notation (lAccountNumber where "l" is for "long").
- Ensure to have ample comments and block comments/documentation.
- Have blank lines to space out code properly and keep your notation consistent by:
  - Using similar variable names.
  - Use consistent indentation.
  - Use consistent spacing between blocks of code.
## Design for Maintainability
Code is considered [*maintainable*](https://en.wikipedia.org/wiki/Maintainability) if it is organized well and is readable. Some things we can do are:
- Make it easy to change, extend, or refactor the program.
- Break the code into intepentent modules, units, or functions.
  - Avoid writing everything in your main program.
  - Avoid code duplication (two or more of the exact same lines).
- Use object oriented design:
  - Manages complexity well.
  - Allows for unit testing.
  - Breaks complex systems into simple pieces.
  - For extensibility, we want to program to [interfaces](https://en.wikipedia.org/wiki/Interface_(object-oriented_programming)):
    - Which will provide a list of functions/methods that are supported.
    - It will assume the absolute minimum about the classes we interact with.
## Software Design Patterns
So, now we've taken a look at software design usages and examples. It's time to dive into software design patters. What is a [software design pattern](https://en.wikipedia.org/wiki/Software_design_pattern) anyways?
> *A software design pattern is a general, reusable solution to a commonly-occurring problem within a given context in software design (kinda like a recipe).*

Essentially, we want to provide the best practices for problems that we've seen in the past. There is a book called "Design Patterns" by Erich Gamma, John Vlissides, Ralph Johnson, Richard Helm. The book is commonly referred to as the "Gang of Four", based off the four authors. They propose 23 different software design patterns, but for the sake of this lecture, we went over 9 of the 23 patterns:
1. Strategy Pattern.
2. Composite Pattern.
3. Factory Pattern.
4. Command Pattern.
5. Adapter Pattern.
6. Facade Pattern. 
7. Observer Pattern.
8. Iterator Pattern.
9. Visitor Pattern.