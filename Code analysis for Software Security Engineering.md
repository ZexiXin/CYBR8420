# Code analysis for Software Security Engineering



## Part 1
  
A short summary of your code review strategy.What challenges did you anticipate and how did your code review strategy attempt to address those challenges?


 * [3]	  CWE-20	Improper Input Validation
 * [24]	CWE-306	Missing Authentication for Critical Function
 * [25]	CWE-862	Missing Authorization
 * [15]	CWE-434	Unrestricted Upload of File with Dangerous Type
 * [7]	  CWE-200	Exposure of Sensitive Information to an Unauthorized Actor
 * [32]	CWE-401	Missing Release of Memory after Effective Lifetime
 * [36]	CWE-835	Loop with Unreachable Exit Condition ('Infinite Loop')
 * [37]	CWE-704	Incorrect Type Conversion or Cast
 
 
### -Code Review Checklists of Croc Application
   * Reviewer: Zexi Xing, Zidong Liu
   * Review Date: 12/02/2020
   * Application: Croc in-network file transferring system

  Based on those previous misuse cases, assurance cases, and threat models, we figured out that Croc has not provide proper protection on input validating and users’             authorized access control. Hence, we need to go through the code view to see if Croc’s functions do have some weaknesses that have been defined in CWE checklist. 

#### **Static Code Analysis**
  | Checklist Item | Category | Notes |
  | --- | --- | --- |
  | Using CWE reference to analyze Croc’s structs and methods | Manual Code Analysis | If no automated Code Analysis is setup for Croc project, we do not use automatic analysis |

#### **Clean code**
  | Checklist Item | Category |
  | --- | --- |
  | Structs should be small | Structs |
  | Functions should be small   | Functions |
  | Avoid duplication functions | Functions |
  | Documentation properly | Comments |
  | Do not return nil | Exceptions |
  | Use intention-revealing names | Meaningful names |
  | No spelling error | Meaningful names |
  | File stream has been closed after used | Input Stream |

#### **Security Issue Checklist**
  | Checklist Item | Weakness | CWE number | Category |
  | --- | --- | --- | --- |
  | Has not check the input string size before outputting it | Improper Input Validation | CWE-20 | Input validation | 
  | Has not use check(err) method to check the input file size, also has not provide the malicious files validating algorithm | Unrestricted Upload of File with Dangerous Type | CWE-434 | Input validation | 
  | IsLocalIP() method always expose network configuration of Croc. | Exposure of Sensitive Information to an Unauthorized Actor | CWE-200 | Confidential information | 
  | Several hard-coded IP addresses always grant access to Croc file transferring and no other authentication is needed | Improper Authentication & Use of Hard-coded Credentials & Reliance on IP Address for Authentication | CWE-287 & CWE-798 & CWE-291 | Confidential information | 
  | All valid IP credentials are viewable inside of a method | Insufficiently Protected Credentials | CWE-522 | Confidential information | 
  | All user will have the same privileges because Croc does not assign, modify, check privileges for an actor | Improper Privilege Management | CWE-269 | Access control | 
  | As long as the IP address is correct, Croc will not verify the user identity | Missing Authorization | CWE-862 | Access control | 
  | Croc uses os.Open() to open the file and it is unsafe function. Hence, os.OpenFile() is a better choice | Use of Potentially Dangerous Function | CWE-676 | Functions | 
  | Only checked if the slice is nil, and empty slice has never been validated | Incorrect Check of Function Return Value | CWE-253 | Functions | 
  | Uncontrolled for loop which designed for finding the missing chunks of file is recursively calling an append () function | Uncontrolled Recursion & Excessive Iteration | CWE-834 & CWE-674 | Functions |
  | Croc does not validate or incorrectly validates | Improper Validation of Specified Type of Input | CWE-1287 | Input validation | 
  | Croc does not properly control the allocation and maintenance of a limited resource | leading to the exhaustion of available resources | CWE-400 | Resource |
  | Croc does not neutralize or incorrectly neutralizes special elements  | Code Injection | CWE-94 | Input validation |
  |The activity log does not show failed attempted passcode for each file | Improper Privilege Management | CWE-306 | Access control |
  |improperly implemented authentication schemes that are subject to spoofing attacks | Authentication Bypass by Spoofing | CWE-290| Spoofing |






we then created a team template using this spesific CWEs and began analyzing each croc file individually each croc fil to cover more ground (code).

Peer Code Review Method (Light Review)

Each team member reviewed sections of  200 lines of code at a time , and analyzed and reviewed our code using the SonarQube scanner tool. SonarQobe is a multi-platform software tool and contains more than 60 plugin extensions. It is compatible with more than 25 programming languages. After each individual manually analyzed core sections of Croc code, we reviewed our code as a team then took the time to properly see if there were any faults that needed to be addressed or fixed. Our goal was to review and analyze more then 500 lines a code per week and find any vulnerabilities, issues, or other debugging that Croc might need. We then ran our test tool, the SonarQuad scanner Tool for Golang. This allowed a for a faster and more productive strategy for effective code inspection. We were able to broaden our scope and allow for more effective, productive code review.  This ultimately allowed for us to improve the process of the code review.


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

