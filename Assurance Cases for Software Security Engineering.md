# Assurance Cases for Software Security Engineering



## Part 1
   1. Upload - Uploaded files to Croc are not accessible by un-Authorized users.
      [LucidChart Link](https://app.lucidchart.com/invitations/accept/7079316e-3b01-42e8-bbcb-bd587a221f16)
      ![](/image/AssuranceCase1F.jpeg)
   2. Generate Passcode  
   3. View report - Higher risk claim 3: Transferring files/messages in Croc will not leak any user’s personal information.  
      [Lucidchart](https://app.lucidchart.com/documents/edit/b5b8e48e-4509-4c06-af8e-b96f973c6692/0_0#?folder_id=home&browser=icon)
      ![](/image/AssuranceCase3-4.png)
   4. Enterpasscode - Sender or croc provides a weak algorithm passcode for potential vulnerabilities.  
      [Lucidchart](https://app.lucidchart.com/invitations/accept/3f2f4c62-431d-4c30-9084-83a1b404ebd7)
  5. Download   
      [Lucidchart]( https://app.lucidchart.com/invitations/accept/6bb8951f-1d10-47c0-84ec-3351def6c628 )
      ![](/image/AssuranceCase5.png)
  



## Part 2
 * Assess the alignment of the evidence you identified in your diagrams, with that available (or can be made available) from the OSS project. Highlight the gaps.

 
 
 
#### Assurance Case 1:
* E1: Croc Usage Guide – The usage guide is a descriptive section within the Croc OSS documentation on github and shows both usage parameters and step-by-step instructions with illustrations.  The commands for initiating Croc’s strengthened, secret key are found here alongside a number of configurable options while doing so.  The documentation, the feature, and the security requirement are aligned.  
* E2: Croc Usage Guide – The usage guide once again demonstrates, and shows illustrations, of the enforcement of the passcode prompt.  There is no way to use Croc without designating a manual, or algorithmically generated, passcode. The documentation, the feature, and the security requirement are aligned.  
* E3: Croc Readme – To qualify the quality of the generated passcode is trickier to prove due to the more qualitative nature of the feature.  The readme file on the project github page showcases this feature, but the degree to which it satisfies the security requirement is less clear.  The feature and the requirement align, but the documentation does not provide quite enough detail to prove that the codes are indeed “hard-to-crack”.
* E4: Croc Project Owner Blog – The OSS project documentation on github directly links to an ongoing blog from the projects foremost contributor.  Here, he writes about more environmental aspects about the usage of Croc.  Rebuttal R5 relates to the environment of the users because Croc itself is not a communication channel one could use to easily send a passcode to an intended user.  The Project Owner Blog discusses this type of usage. The documentation, the feature, and the security requirement are aligned.

#### Assurance Case 3:
* Evidence E1: Croc download URL:
* Evidence E2: Corc -help:
* Evidence E3: Self-host relay process:
* Evidence E4: Report in the Croc directory: 
* Evidence E5: Croc Dockerfile:
* Evidence E6: Croc requirements:
 

### Collaborations:  
* Via Zoom Meetings
* [Via Google Docs](https://docs.google.com/document/d/1Vv0kSrD5M8hSyjTQmaJnvpghe5GGj-RwnCdF9dxKRZU/edit?usp=sharing)
* [Via Project Borad](https://github.com/ZexiXin/CYBR8420/projects/1)



### Reflection:
* Include a reflection of your teamwork for this assignment. What issues occurred? How did you resolve them? What did you plan to change moving forward? 

   This section had the team taking a more "divide and conquer" approach, with less direct collaboration on each diagram and more individualized work.  Team insights and review were still readily available nonetheless.  One issue that occurred was a general misunderstanding of how to approach the "evidence" portions of the assurance cases, but this misunderstanding was clarified by the professor during our deliverable team check-in.   This section we also converged our team meetings into a regular occurring event, with less effort to plan meetings because they were already pre-scheduled.  Moving forward, we plan finalize rough draft documents sooner so that there is less work needed towards the end of the assignment period.

