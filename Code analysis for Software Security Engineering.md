# Code analysis for Software Security Engineering



## Part 1
  
### A short summary of your code review strategy. What challenges did you anticipate and how did your code review strategy attempt to address those challenges?

Based on those previous misuse cases, assurance cases, and threat models, we figured out that Croc has not provide proper protection on input validating and users’ authorized access control. Hence, we decided to first go through the code view to see if Croc’s functions do have some weaknesses that have been defined in CWE checklist.  To do this, our code review strategy was a checklist-based approach that leaned on some core CWEs we saw as probable vulnerabilities within Croc, while also being within the realm of programming concepts we were familiar with.  We started with the list of Top 25 CWEs, then expanded our usage of CWE references as we progressed through the code.  Each team member would review approximately 200 lines of code at a time, taken from core files within the Croc software environment. So, we decided to create a-two man group to review different Croc Application - tcp, Cli, Comm, Util and Croc code files. The table below shows the pairing of our teams:

### - Code Review Workshare
  | Groups | Team Members | Codes |
  | --- | --- | --- |
  | A | Dennis & Enersto | Comm |
  | B | Adam & Zexi |Croc |
  | C | Dong & Enersto |Util |
  | D | Adam & Dennis |Cli |
  | E | Zexi & Dong |TCP |
  
### - Justification for CWEs    
In previous deliverables for this project, we had identified that certain portions of Croc’s functionality might be more prone to vulnerabilities than others given their importance.  For example, a user interacting with Croc as a file sender or receiver does not have a great many options to interact with Croc other than basic input parameters.  So, input validation is a key factor (CWE-20).  Croc has no implementation for accounts or user authorization other than sourcing the sender or receiver to an IP address.  This led us to also focus on CWEs related to missing authorization (CWE-25) and authentication for critical functions (CWE-306).  Another aspect of Croc is the actual uploading and downloading of the user’s file, so CWEs like CWE-434 were also critical. Error handling was another concern that we identified, which is identified as CWE - 544. This process of reviewing past analysis of Croc and then mapping them to CWEs, then in turn scanning through the code and looking for related issues was our general approach to code review.

A much more efficient method of Code Review, indicated by our professor in our latest team check-in, was to utilize a software scanning tool to generate a configured report which would then give us terms, faults, and problems which would help us in our manual code review.  But, as is written in a later section of this document, we had several troubles with setting up our automated tool.  We had tried on several occasions to get SonarQube, a popular scanning tool compatible with Go, to work but were unsuccessful.  This led us to lean more on manual code review.  So, for the manual code review, we used the extensive documentation found on https://cwe.mitre.org/ for various CWEs and applied them as a checklist for us to manually review Croc’s code.


 
### -Code Review Checklists of Croc Application
   * Reviewer: Zexi Xing, Zidong Liu, Adam Mills, Ernesto Macias, Dennis Ugbebor
   * Review Date: 12/02/2020
   * Application: Croc in-network file transferring system



#### **Static Code Analysis**
  | Checklist Item | Category | Notes |
  | --- | --- | --- |
  | Using CWE reference to analyze Croc’s structs and methods | Manual Code Analysis | Automated Code Analysis was setup for Croc project but we could not successfully conduct automatic analysis; SonarQube was setup but Analysis was inconclusive due to subscription requirements for report scanning and repository commitment|

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
  | The activity log does not show failed attempted passcode for each file | Improper Privilege Management | CWE-306 | Access control |
  | Improperly implemented authentication schemes that are subject to spoofing attacks | Authentication Bypass by Spoofing | CWE-290| Spoofing |
  | sendData in Croc is not end-end encryption, only encrypts if certain conditions are met | Missing Encryption of Sensitive Data | CWE-311 | Confidential information |
  | Salt generation in Croc file is predictable | Use of Insufficiently Random Values | CWE-330 & CWE-340 | Confidential information |
  | Communication Channel Errors| Improper handling of communication channels/Paths| CWE-924 | Confidential information |
  | Inconsistent error handling and resultant weaknesses | Missing Standardized Error Handling Mechanism | CWE-544 | Error Handling |
  
 

### Findings from automated code scanning (if available). Include links to full reports.
At the begining, we selected a automatic scanning tool called Sonarcloud and SonarQube to analyze Croc App, but we have encountered several configuration problems while figuring out the file enviroment PATH and Snoar source. During the 12/04 group meeting, we decide to reconfigure it and see if the online resources could help us to solve this issue. Unfortunately, we haven't found many useful resources that specify the project root configuration file, so we Fork the Croc into out repository and use the URL as the root configuration file to start analyzing. 
![](/image/tool1.png)
![](/image/tool2.png)

Finally, we got some result, but it is not doing the correct scanning as we expected. Hence, we will not use this result that the image showing below as our reference. In other word, based on what we find, there is not a suitable tool to use for scanning Croc flaws. 
![](/image/tool3.png)


## Part 2
 
### Summary of key findings from manual and/or automated scanning. This summary should include mappings to CWEs to describe categories of major findings.

Our general findings were that Croc, for what the program seeks to do, does so with relative security.  This is made easier with Croc’s developmental goal of simplicity.  Seen in [Croc documentation](https://schollz.com/blog/croc6/) and emphasized throughout, croc is summarized by its authors as “croc = fast + secure +simple.”.  The “simple” aspect refers to Crocs narrow scope, it avoids feature creep and bloat.  The “secure” refers to its password-protected and encrypted file transfer service.  During our analysis, we found these features present and done so with software assurance in mind.

However, there were some key findings in our manual review.  There were several instances of weak input-validation we noted (CWE-20).  Give that the only real way to interact with Croc is the typing prompt, this was a disappointing find.  Certain confidential information, like IP addresses, are hard-coded into the process (CWE-287, CWE- CWE-291) which is lacking because the mere address is the only real authentication system that Croc uses outside of the password prompt.   Log messaging for error handling is also a weak point (CWE-544) in that it seems to be extremely inconsistent in the code.  Several locations were noted where one would think an error handler would be implemented in some way, even if just a basic exit condition.  

### Planned or ongoing contributions to the upstream open-source project (documentation, design changes, code changes, communications, etc.) These can be based on any of the prior assignments in the class.

Based on what we have analyzed so far, the Croc itself does exist few security issues need us to focus on. Hence, we plan to contribute some possible design changes like adding the user authentication process, specify file size boundary, or even use unpredictable passcode generation algorithm to the Crco developers. For example, We found a file similar to os.Open() function in the Croc file. Os.open () method is used to open a file, and set the desired options open, mode parameter mode parameter is optional and defaults to 0777. The Croc principle is that Croc uses os.Open() function to open the file, which is an unsafe function compared to os.OpenFile(). If we can use OpenFile function, Croc will be better. OpenFile is the generalized open call; most users will use Open or Create instead. It opens the named file with specified flag (O_RDONLY etc.). If the file does not exist, and the O_CREATE flag is passed, it is created with mode perm (before umask). If successful, methods on the returned File can be used for I/O. So, we suggest using os.OpenFile() will be a better choice. For another one example, Croc does not have input filtering. If the file we upload is a malicious script, it will threaten user safety. Therefore, we suggest that Croc can have a function that can identify whether the file uploaded by the user is a threatening file, This will ensure the safety of the receiver. In addition, The permissions of Croc are not specified, and all users can use it. Like owner, group, and anyone can access. This may cause sensitive information to be leaked, and the security of user information is not well guaranteed. Therefore, we recommend grouping permissions and separating permissions to manage users. The last point is the problem of Croc resource consumption. Whether it can withstand Dos, because it also has a network layer. The network layer may encounter such attacks, causing resource consumption, downtime or not working. This is also a software that can work normally. For this reason, this will be the subject of our continued research. We hope to work together to make Croc safer.
 

### Collaborations:  
* Via Zoom Meetings
* [Google Docs Link](https://docs.google.com/document/d/1HUrJewfo7kQ76LBDpRS7hcHfIfXYbmgBH6v3eCQF67I/edit?usp=sharing)
* [Via Project Board](https://github.com/ZexiXin/CYBR8420/projects/1)



### Reflection:
At first, we were confused about the classification of CWE. Originally, we wanted to use the "Class" category to represent the vulnerability description. Later, after discussion in our group, we found that we should refine the CWE to the lowest level.
For code review, we did not have any strategy to cause a huge workload, but after meeting with the professor, we had our own ideas and strategies. We should start with the previous work, starting with use cases and misuse cases, because we have previously analyzed where Croc has Gap, which will lead to Croc security flaws and vulnerable to attacks.
For the use of automated tools, we have encountered difficulties. Our project language is mainly GO, but the current lack of code tools for GO language causes us to use only a few tools. However, these types of tools have high requirements on different platforms, which led us to spend a lot of time to solve this problem. In general, we don't need to spend too much time on tools, but spend more time on the defects of Croc itself, which will greatly reduce our code review time.
