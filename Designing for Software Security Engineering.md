# Designing for Software Security Engineering


## Part 1: Threat Modeling

* Draw and analyze the DFDs using the Microsoft Threat Modeling tool (TMT)
* Generate a full HTML report using TMT
* Host the HTML reports in your project github repo and link from your markdown submission.


### [**Use this link to generate a Host view of your report**](https://htmlpreview.github.io/)

1. [The DFD of Generating File Report in the Croc](https://htmlpreview.github.io/?https://github.com/ZexiXin/CYBR8420/blob/master/DFD%20report/DFD%20Report%20Croc.htm)
<!-- 4. [The DFD of Generating Passcode in the Croc](https://htmlpreview.github.io/?https://github.com/ZexiXin/CYBR8420/blob/master/DFD%20report/Level%200%20Report.htm) -->
<!-- 5. [The DFD of Downloading in the Croc](https://htmlpreview.github.io/?https://github.com/ZexiXin/CYBR8420/blob/master/DFD%20report/Download.htm) -->

## Part 2: Observation


### Summarization


### Internal Collaboration
[Google Doc](https://docs.google.com/document/d/12EbnDpuQff2Qv3mEIP6GIVfT_WmlxSaez4pV_MRjUlI/edit?usp=sharing)  
[Project Board](https://github.com/ZexiXin/CYBR8420/projects/1)


### Reflection

Each of our teammates analyzed and created a model for Croc using the Microsoft threat modeling tool version 7.3. We created a new template using the SDL TM Base Core (4.1) and created level 0 and level 1 DFD (Data flow Diagram) for the croc software. 

Level 0: Level 0 contains single process representing the whole system this includes external interactors which are senders and receivers. The main process (Code) is Croc, its main two data flows are uploading file/ message and download file/ message as well as generate passcode and regenerate passcode. The generated passcode is created by Croc.

Level 1: Level 1 contains major process and stored identifies this includes external interactors which are senders and receivers. The main process (Code) is Croc, its main two data flows are uploading file/ message and download file/ message as well as generate passcode and regenerate passcode. The generated passcode is created by Croc. Crocs Data store is the peer to peer encryption algorithm, Croc uses to generated and decrypt passcode. For the sender to protect and assure his uploaded file/message is safe and secure and the receiver to ensure the file/message was downloaded between the two external interactors and Crocs processes. 

Level 2: Level 2 contains three major process which are: Croc Application 1.0, Network Socket, Password Authentication.Sender and Reciver are the external interactors just like the previos levels (Level 0, Level 1) .The data flow between the two external interactors with crocs proccees 1.0 , is similar to the previous leves (level 0 , level 1).The Network Socket 2.0 and Password Authentcation 3.0 , are the new processes we implemented in level 2 of our combined DFD.The data flow for the Network Socket 2.0 and Password Authentcation 3.0 are synchronized with our data store, which is Croc file system.Lastly the data flow for The Network Socket 2.0 and Password Authentcation 3.0 are synchronized with Crocs Application 1.0 Process which we mention earlier.

We then used analyzed view for Level 0, Level 1 and Level 2 DFD (Data flow Diagram) as a team and created one generated scenario for the whole system, as well as the justification and priority for each case. Lastly a full report was created for each level using Microsoft threat modeling repot tool located on the top left corner.  A HTML Report is automatically created and fully functional for the viewer to see each case scenario as well as threat model summary and number of states used.

Based on feedback from the professor, we decided to merge all diagrams into one in order to curb redundancy.  After doing this, we still had upwards of 200+ generated threats which made things difficult to process.  During this period there were also some personal changes.  Adam and his wife Yara spent a week in the hospital after the birth of their firstborn son Leon, and the subsequent week after has many sleepless nights adjusting to a new lifestyle.


