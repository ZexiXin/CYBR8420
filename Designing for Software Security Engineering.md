# Designing for Software Security Engineering


## Part 1: Threat Modeling

* Draw and analyze the DFDs using the Microsoft Threat Modeling tool (TMT)
* Generate a full HTML report using TMT
* Host the HTML reports in your project github repo and link from your markdown submission.

1. 
2. 
3. [The DFD of Generating File Report in the Croc](https://htmlpreview.github.io/?https://github.com/ZexiXin/CYBR8420/blob/master/DFD%20report/The%20DFD%20of%20Generating%20File%20Report%20in%20Croc%202.htm)
4. [The DFD of Generating Passcode in the Croc](https://htmlpreview.github.io/?https://github.com/ZexiXin/CYBR8420/blob/master/DFD%20report/Level%200%20Report.htm)
5. 
## Part 2: Observation


### Summarization


### Internal Collaboration
[Google Doc](https://docs.google.com/document/d/12EbnDpuQff2Qv3mEIP6GIVfT_WmlxSaez4pV_MRjUlI/edit?usp=sharing)  
[Project Board]()


### Reflection

Each of our teammates analyzed and created a model for Croc using the Microsoft threat modeling tool version 7.3. We created a new template using the SDL TM Base Core (4.1) and created level 0 and level 1 DFD (Data flow Diagram) for the croc software. 

Level 0: Level 0 contains single process representing the whole system this includes external interactors which are senders and receivers. The main process (Code) is Croc, its main two data flows are uploading file/ message and download file/ message as well as generate passcode and regenerate passcode. The generated passcode is created by Croc.

Level 1: Level 1 contains major process and stored identifies this includes external interactors which are senders and receivers. The main process (Code) is Croc, its main two data flows are uploading file/ message and download file/ message as well as generate passcode and regenerate passcode. The generated passcode is created by Croc. Crocs Data store is the peer to peer encryption algorithm, Croc uses to generated and decrypt passcode. For the sender to protect and assure his uploaded file/message is safe and secure and the receiver to ensure the file/message was downloaded between the two external interactors and Crocs processes. 

We then used analyzed view for Level 0 and Level 1 DFD (Data flow Diagram) as a team and created a status for each generated scenario as well as the justification and priority for each case. Lastly a full report was created for each level using Microsoft threat modeling repot tool located on the top left corner.  A HTML Report is automatically created and fully functional for the viewer to see each case scenario as well as threat model summary and number of states used.


