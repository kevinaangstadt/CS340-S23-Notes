# Notes for Software ENgineering Class 3/27/23
Jax Lubkowitz 

# Defect Reporting and Triaging 
Mozzilla in 2005 reported 300 bugs a day that needed to be triaged.

Def/n Fault: exceptional situation at runtime
Def/n Defect: any character of a product that hinders its usabiulity for intended purposes 
                (ex. design defect or a bug (static defect))
Def/n Defect Report: provides info about fault or bug created by tester, user, tool containing lots of detail
Def/n Feature Request: potential change to indended purpose of software

An issue is the union of a defect report and feature request.

Def/n Defect Report Life Cycle: made of possible stages & actions, including reporting confirmation, triage, assignment resolution and verification. 

See bug diagrams on course webstie from lecture 18.
There are many paths through life cycle and reports follow differant paths. Ie not a linear process
Status of a report tracks position in lifecycle

1.) How does report enter system?
Internal - Developers Qaulity Assuarance, Testers
External - Beta-tester, end user, 

Anatomy of a bug report - 
    summarry/title 
    Description of bug/defect
    Component
    Version
    OS
    Steps to reproduce faults
    Attachments such as datafiles, screenshots, stacktraces, videos

2.) Triaging: Which bugs get fixed first?
Assignment of degrees of urgency 
Severity - degree of impact on developer or operation of component.
Priority - Importance or urgancy of fixing defect. 
Severity and priority are correlated but independant 
Triaging helps cost benefit analysis as more reports then resources
    How expensive is bug to fix?
    How expensive is bug to NOT fix?

