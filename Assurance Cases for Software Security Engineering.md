# Assurance Cases for Software Security Engineering



## Part 1
   1. Upload - Uploaded files to Croc are not accessible by un-Authorized users.
      [LucidChart Link](https://app.lucidchart.com/invitations/accept/7079316e-3b01-42e8-bbcb-bd587a221f16)
      ![](/image/AssuranceCase1F.jpeg)
   2. Generate Passcode - Croc can improve secure file transfer by using passcode generation mechanism 
      [LucidChart Link](https://app.lucidchart.com/lucidchart/c93b562a-a307-4b1d-aeba-0374937dd24c/edit?shared=true&page=0_0#?folder_id=home&browser=icon)
      ![](/image/AssuranceCase2.png)
   3. View report - Higher risk claim 3: Croc minimizes the sensitive information leakage while transferring files/messages.  
      [Lucidchart](https://app.lucidchart.com/documents/edit/b5b8e48e-4509-4c06-af8e-b96f973c6692/0_0#?folder_id=home&browser=icon)
      ![](/image/AssuranceCase3-4.png)
   4. Enterpasscode - Croc insures a stong generated passcode to prevent potential vulnerabilities.
      [Lucidchart](https://app.lucidchart.com/invitations/accept/3f2f4c62-431d-4c30-9084-83a1b404ebd7)
      ![](/image/AssuranceCase-4.jpeg)
  5. Download - Croc can download multiple files/messages at the same time without compromise.
      [Lucidchart]( https://app.lucidchart.com/invitations/accept/6bb8951f-1d10-47c0-84ec-3351def6c628 )
      ![](/image/AssuranceCase5F.png)
  



## Part 2
 * Assess the alignment of the evidence you identified in your diagrams, with that available (or can be made available) from the OSS project. Highlight the gaps.

 
 
 
#### Assurance Case 1:
* E1: Croc Usage Guide – The usage guide is a descriptive section within the Croc OSS documentation on github and shows both usage parameters and step-by-step instructions with illustrations.  The commands for initiating Croc’s strengthened, secret key are found here alongside a number of configurable options while doing so.  The documentation, the feature, and the security requirement are aligned.  
* E2: Croc Usage Guide – The usage guide once again demonstrates, and shows illustrations, of the enforcement of the passcode prompt.  There is no way to use Croc without designating a manual, or algorithmically generated, passcode. The documentation, the feature, and the security requirement are aligned.  
* E3: Croc Readme – To qualify the quality of the generated passcode is trickier to prove due to the more qualitative nature of the feature.  The readme file on the project github page showcases this feature, but the degree to which it satisfies the security requirement is less clear.  The feature and the requirement align, but the documentation does not provide quite enough detail to prove that the codes are indeed “hard-to-crack”.
* E4: Croc Project Owner Blog – The OSS project documentation on github directly links to an ongoing blog from the projects foremost contributor.  Here, he writes about more environmental aspects about the usage of Croc.  Rebuttal R5 relates to the environment of the users because Croc itself is not a communication channel one could use to easily send a passcode to an intended user.  The Project Owner Blog discusses this type of usage. The documentation, the feature, and the security requirement are aligned.

#### Assurance Case 3:

* Evidence E1: Croc download URL - Croc download URL - Croc has provided a specific download URL which contains the most recent Corc version v8.2.0, and the Croc developed just   released it 6 days ago. Hence, the instruction and the security requirement are aligned.  

* Evidence E2: Corc -help: Corc -help - “Croc -help” is a command line syntax which will list all available commands in Croc UI and provides detailed instructions for each       command. One of the most powerful commands is specifying handshaking protocol like TCP (TCP.go has been fully developed in the /src directory) during files or messages         transferring. Hence, the instruction and the security requirement are aligned.  

* Evidence E3: Self-host relay process- The self host relay process is a security function that can forcibly designate a port number between sender and receiver while             transferring files or messages. However, it does not have passcode protection because the relay function never transfers passcode through the network. Hence, even though the   Relay function can set a specific tunnel to protect the file transmission, it cannot provide passcode protection because we don’t know how the sender will hand out the         passcode. Therefore, the basic file transmission can be guaranteed, but the Relay function hasn’t developed a passcode transmission function.  

* Evidence E4: Report in the Croc directory - Every time when a user initiates a file or message to the others. Croc will automatically generate a transmission summary inside     of Croc directory to let the user verify what exactly he/she has sent to the receiver.  Hence, the instruction and the security requirement are aligned.  

* Evidence E5: Croc Dockerfile - Croc Dockerfile has almost everything that Relay function has, so Dockerfile can maintain the files/messages transmission security as well.       Besides, Croc Dockfile’s command line syntax provides an extra parameter to transfer passcode and sender’s through the network. In this case, Dockfile complements Relay         functions’ shortcomings by adding passcode transmission functions. Nevertheless, when we explore the internal code view of Dockfile even its command line syntax, we didn’t     find any cryptographic algorithm to protect passcode transferring. As a result, the basic transmission and passcode transmission can be guaranteed, but the passcode             protection mechanism has been fully developed.   

* Evidence E6: Croc requirements - While the user downloads the Croc, Croc is requiring the user to install itself into a normal directory which the user has full access to,     but the other users who share the same devices with the user don’t have access to. Hence, if a user can send a file/message to the other folks in the network, he ought to       have full access to the Croc directory. Hence, the instruction and the security requirement are aligned.

 #### Assurance Case 4:
 
* E1: Evidence created by me- If senders Passcode is weak(Not Sufficient) then Passcode prompt will appear on the screen, hence giving the user warning message of passcode not being strong enough.

* E2:Croc Project Owner Blog- PAKE is a cryptographic method where two people share a password which is then used – via back-and-forth communication – to generate a strong key. The strong key can then be used for all further encryption. Since the two people generate the strong key by exchanging information, no one else could possibly learn the strong key even if they have the original password.

* E3: Evidence created by me- If a user sends a strong passcode, but the receiver does not type in the correct passcode a prompt message will appear on the screen to the receiver, hence incorrect passcode.

 
 
 
 
#### Assurance Case 5:
* Evidence E1: Croc readme: Croc allows resuming transfers that are interrupted. All files can be restored during the interruption, so that the user files will not disappear. Of course, the security performance of Croc is further improved, that is, user files cannot be tampered with during the process
* Evidence E2: Croc configuration: Croc does not require a server or port forwarding. File transfers can be easier by eliminating the need for hosting a server or port forwarding. And using a relay server allows any two computers to connect to one another without resorting to port forwarding or fiddling with a server.  
* Evidence E3: Relay functions: Croc use a relay server to create a full-duplex real-time communication layer between the two computers so that “uploading” and “downloading” occur simultaneously between the two computers, and then files can be download safely.
* Evidence E4: Croc requirements:  Croc parameter input field requirements. It is written in the user guide that each command and parameter has a designated function, and bad goals cannot be achieved by tampering with the command.
* Evidence E5: Croc report: Croc provides a user guide to ensure that users can use the software normally. Reduce the misuse rate and strengthen the security of the software

 

### Collaborations:  
* Via Zoom Meetings
* [Via Google Docs](https://docs.google.com/document/d/1Vv0kSrD5M8hSyjTQmaJnvpghe5GGj-RwnCdF9dxKRZU/edit?usp=sharing)
* [Via Project Borad](https://github.com/ZexiXin/CYBR8420/projects/1)



### Reflection:
* Include a reflection of your teamwork for this assignment. What issues occurred? How did you resolve them? What did you plan to change moving forward? 

   This section had the team taking a more "divide and conquer" approach, with less direct collaboration on each diagram and more individualized work.  Team insights and review were still readily available nonetheless.  One issue that occurred was a general misunderstanding of how to approach the "evidence" portions of the assurance cases, but this misunderstanding was clarified by the professor during our deliverable team check-in.   This section we also converged our team meetings into a regular occurring event, with less effort to plan meetings because they were already pre-scheduled.  Moving forward, we plan finalize rough draft documents sooner so that there is less work needed towards the end of the assignment period.

