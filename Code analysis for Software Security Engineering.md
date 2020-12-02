# Code analysis for Software Security Engineering



## Part 1
  
A short summary of your code review strategy.What challenges did you anticipate and how did your code review strategy attempt to address those challenges?

For the CWEs we choice as a team:

 * [3]	  CWE-20	Improper Input Validation
 * [24]	CWE-306	Missing Authentication for Critical Function
 * [25]	CWE-862	Missing Authorization
 * [15]	CWE-434	Unrestricted Upload of File with Dangerous Type
 * [7]	  CWE-200	Exposure of Sensitive Information to an Unauthorized Actor
 * [32]	CWE-401	Missing Release of Memory after Effective Lifetime
 * [36]	CWE-835	Loop with Unreachable Exit Condition ('Infinite Loop')
 * [37]	CWE-704	Incorrect Type Conversion or Cast

we then created a team template using this spesific CWEs and began analyzing each croc file individually each croc fil to cover more ground (code).

Peer Code Review Method (Light Review)

Each teammember reviewed fewer than 200 lines of code at a time , and analaysed and revied our code using SonarQuobe scanner tool. SonarQuobe is a multi-platform software tool and contains more than 60 plugin extensions. It is compatible with more than 25 programming languages. After each individual analyzed 200 lines of code. We reviewed our code as a team and took the time to properly see if there were any defaults that needed to be addressed or fixed. Our goal was to review and anayalis more then 500 lines a code per week and find any vulnerabilities issues or debugging the program might have. To do this we used SonarQuad scanner Tool for Golang. This allowed a fatser and more productive strategy for effective code inspection. This allowed to broaden our spectrum and allow for more effective and productive code review. Which ultimately allowed and improve the process of the code review.


Findings from manual code review of critical security functions identified in misuse cases, assurance cases, and threat models.

Findings from automated code scanning (if available). Include links to full reports.



## Part 2
 
Summary of key findings from manual and/or automated scanning. This summary should include mappings to CWEs to describe categories of major findings.

Planned or ongoing contributions to the upstream open-source project (documentation, design changes, code changes, communications, etc.) These can be based on any of the prior assignments in the class.

 

### Collaborations:  
* Via Zoom Meetings
* [Google Docs Link](https://docs.google.com/document/d/1HUrJewfo7kQ76LBDpRS7hcHfIfXYbmgBH6v3eCQF67I/edit?usp=sharing)
* [Via Project Board](https://github.com/ZexiXin/CYBR8420/projects/1)



### Reflection:

