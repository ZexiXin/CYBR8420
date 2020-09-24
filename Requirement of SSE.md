# Requirement of Software Security Engineering

### Part 1: 
* Identify **5 essential** interactions from Crocdeile application.

  ![User case diagram](image/userdigram.png)

* Misuse case analysis
  1. Sender uploads file/message **VS** attacker either spoofs or listens in file choice(Dong).
  ![Misuse of uploading phase](image/misuse.png)
  
  2. Sender chooses passcode **VS** attackers attempts to upload his own malicious document, then sends code to malicious document to unsuspecting users. (Adam)
  ![Misuse of receivers passcode](image/MisuseCase2.png)
  
  3. User view reports **VS** attacker modifies the report by changing the app source code and embedding backdoors (Xing)
  ![Misuse of view report](image/misusereport.png)
  
  4. Receiver enters generated passcode **VS** attacker attempts to get remote control and gather data on users.
  ![Misuse of receivers passcode](image/MisuseCase4.jpeg)
  5. Receiver attempts to download file **VS** attacker attempts to change/swap file.


* Assess alignment of security requirements derived from mis-use case analysis with advertised features of the open-source software. Review OSS project documentation and         codebase to support your observations. 

### Part 2: 
* Review OSS project documentation for security-related configuration and installation issues

* Internal collaboration link:  
  [Google doc shared folder](https://drive.google.com/drive/folders/1KaGGMMrWPBGJOGmv-B71ekzhYPtE84PG)  
  [Github project board](https://github.com/ZexiXin/CYBR8420/projects/1)


* Reflection of teamwork for SSE assignement
  At the beginning, we had doubts about five essential interactions of our open-source software. Just a simple list of 5 points, without expansion. 
  The most fundamental reason is that we have not thoroughly understood the overall software process. After that, each of us came to a conclusion after using the Croc software.
  Some of the issues that occurred were identifying proper misuse cases for the diagrams and identifying the treat level of each diagram.

  Since the project proposal was not good enough last time, I think each of us must devote 100% of our energy to face our project this time. 
  We are a team, I believe that the ability of a team can be competent for any of us.


