# Detailed Design Document
# VOX - Real-time Group Chat App

May 2nd, 2023

**Version** 2

![Logo](./Images/small_VOXLOGO.png)

**Presented to**  
Dr Schwesinger

**Submitted By:**  
Hamad Ahmed  
Gabe Leffew  
Benjamin Lloyd  


## Revision History
| Date Created  | Version # |
| ------------- |:---------:|
| 4/20/2023     | 3         |
| 4/12/2023     | 2         |
| 2/15/2023     | 1         |


## 1.0 Introduction
Our goal is to create a centralized location for collaboration in the classroom setting and beyond. Schedule events for your team and find the best team to tackle your toughest goals. Save notes for classes and share with your group to always be on the same page. Create servers for any group like a club, a group of friends, or your tri-annual family reunion.

## 1.2 Scope

![Use Case Diagram](./Images/usecase_diagram.png)

### Personas

- I am a college student who always forgets my due dates and can’t communicate effectively with my team members. If only there was one spot to see all this information, I would excel in my academic career.

- I am a football coach and can’t keep up with my rowdy team. Some of my dogs forget to come to practice sometimes and other times they don't hand in their chicken barbecue fundraisers. I need a place to collaborate with my team and help my boys succeed.

## 2.0 Related Documents
- [Requirements Traceability Matrix](./Requirements_Traceability_Matrix.xlsx)
- [Software Requirements Specification](./software_requirements.md)


## 3.0 Design
### 3.1 Component Diagram
![Component Diagram](./Images/component_diagram.png)

### 3.2 Entity Relationship Diagram
![Entity Relationship Diagram](./Images/er_diagram.png)

### 3.3 Major Use Cases
#### 3.3.1 Create Account
- Story: I want to identify myself within the application. Creating an account is a way to fullfil this.
- Description: User goes on to the website for the first time. To acccess the features, an account must be created. The user would hit ceate account button, and fill out the information with valid input. After that, user get access to the homepage.
- Preconditions: none
- Postconditions: User gets access to the homepage screen
- Design Details: Do not forget to enter valid account information.
- Constraints: Can only enter alphanumeric characters for username.
- Assumptions: none  
![Sequence Diagram for create account](./Images/Sequence%20Diagrams/Create_Account_SD.jpg)

#### 3.3.2 User Login
- Story: To keep using the application more than time, you can login into your account and continue where you left off.
- Description: User visits the website after they already have an account. User would hit the login button, and enter their account information to log in. Then, they would be taken to the homepage.
- Preconditions: Must have an existing account
- Postconditions: none
- Design Details: Enter your valid account information
- Constraints: none
- Assumptions: none  
![Sequence Diagram for User Login](./Images/Sequence%20Diagrams/User_Login_SD.jpg)

#### 3.3.3 Create Vox Server
- Story: To interact with another user, both users need to be in the same server. One user needs to create a server or be invited to one. If the user wants to be a server admin, they must create a server themself. Moreover, the first user of the application must create a server.
- Description: After the user logs in to their account, they will arrive at the homepage. On the left panel, the user would fill in a textbox and click `Create`. Then, a server is created with the user as the admin and no pre-existing users.
- Preconditions: Must have an existing account
- Postconditions: Server is created in db, user becomes the server admin of the created server. 
- Design Details: Do not forget to enter a valid server name.
- Constraints: Can only enter alphanumeric and spaces characters for server name but not exclusively whitespace.
- Assumptions: None  
![Sequence Diagram for Create VOX Server](./Images/Sequence%20Diagrams/Create_VOX_Server_SD.jpg)

#### 3.3.4 Chat on Servers
- Story: I want to ask a general question, but I don't know when the Professor is going to get back to me, hopefully one of my classsmates will be able to get back to me soon, I need a way to message everyone!
- Description:The Server will have a general chat for everyone to communicate
- Preconditions: Must be in a server
- Postconditions: None
- Design Details: Message is pushed through the socket for a live update of whoever is in the server at the time and the message is sent to the database for users to see if they join later.
- Constraints: Message will be converted to ascii so no special symbols can be used.
- Assumptions:None  
![Chatting Sequence Diagram](./Images/Sequence%20Diagrams/ChatOnServersSequence.png)

#### 3.3.5 Notebook
##### 3.3.5.1 View/edit notebook
- Story: I wish I could be more organized. I've been stuffing my bookbag with loose papers and I lose them regularly. I may have to drop out of college because of this. If only they could be kept in a centralized digital location.
- Description: A user may create a notebook for each server they are in. The contents would be saved in the cloud so they can access it anywhere they go.
- Preconditions: Must have an account and be a part of a server
- Postconditions: Save notebook if changes were made
- Design Details: User has a seperate notebooks for each server they are part of. The notebook should be able to be saved manually. 
- Constraints: None
- Assumptions: None  
![View/ Edit Notebook Sequence Diagram](./Images/Sequence%20Diagrams/Notebook%20Viewing_Editing.png)

##### 3.3.5.2 Share notebook
- Story: My classmate missed class and didn't get the notes. Since we are in the same server for the class I would like to be able to share the notes with them.
- Description: A user of a server may share their notebook with other users of the same server. This would be viewable in a column that would show who all in the server shares their notes and the user would be able to choose any of them.
- Preconditions: Must have an account and be a part of a server 
- Postconditions: None
- Design Details: A user viewing a shared notebook may not make edits to the notebook, READ ONLY. 
- Constraints: Only owner of notebook may edit the notebook, shared users may only view notes
- Assumptions: None  
![Share Notebook Sequence Diagram](./Images/Sequence%20Diagrams/Notebook%20Sharing.png)

#### 3.3.6 Calendar
##### 3.3.6.1 Create event
- Story:I am a professor that is having an assignemnt due this sunday, and I want to put it on the calendar so my pupils are aware of it.
- Description:Add an event to the calendar either for personal planning or for a whole server to see
- Preconditions: Must have an Account
- Postconditions: Event is added to calendar
- Design Details: Date, Description, either personal or server-based
- Constraints: If the event is for a server then only the admin may create the event.
- Assumptions:None  
![Create Event Sequence Diagram](./Images/Sequence%20Diagrams/CreateEventSequence.png)

##### 3.3.6.2 Remove event 
- Story: We were going to have an exam on Friday, but my students are not ready for it, I need a way to remove it from the Calendar
- Description: Delete an already-existing event from a calendar if plans change
- Preconditions: Must have an existing event
- Postconditions: Event is deleted from calendar and the record of the server in the db
- Design Details: None
- Constraints: Only server admins may remove server events.
- Assumptions:None  
![Remove event Sequence Diagram](./Images/Sequence%20Diagrams/RemoveEventSequence.png)

#### 3.3.7 Remove Users
- Story: There is someone being a nuisance in my server. It is distracting the other users from excelling in their academic career. As a teacher, I need a way to get these hooligans out.
- Description: There should be the ability to remove a user from a server.
- Preconditions: Have users in a server and be the owner of the server 
- Postconditions: Remove user from record of server along with their messages and notebooks.
- Design Details: Admins should be the only ones allowed to remove users.
- Constraints: None
- Assumptions: None  
![Share Notebook Sequence Diagram](./Images/Sequence%20Diagrams/Remove%20User.png)

#### 3.3.8 Delete Server
- Story: No one uses my server anymore and there is no point of having it so I want to get rid of it.
- Description: The admin of the server will select the settings option in the top right hand corner of their server page; once there they will be able to select `Delete Server` and will be prompted with a window to confirm this deletion. 
- Preconditions: Be an admin of the server
- Postconditions: Deletes the server and any records in the db related to the server including messages and notebooks.
- Design Details: This will delete the server and everything associated with it in the database.
- Constraints: Only the server owner can delete the server.
- Assumptions: None  
![Delete a Server SD](./Images/Sequence%20Diagrams/Delete_a_serverSD.png)

#### 3.3.9 Invite users to server
- Story: I want to invite my friends to the server to chat with them.
- Description: The admin of the server will select the settings option in the top right hand corner of their server page; they can then get an invite code then can send to their friends to join the server.
- Preconditions: None 
- Postconditions: None
- Design Details: The invite code is only accessible to the server admin and must be distributed by them outside of the VOX application.
- Constraints: Only the server owner is able to invite other users to the server.
- Assumptions: None  
![Invite a User](./Images/Sequence%20Diagrams/inviteuserSD.png)


## 4.0 Systems
### 4.1 Architecture
The architecture is defined in the SRS document.
- [Software Requirements Specification](./software_requirements.md/#50-architecture)


## 5.0 Non Functional Requirements
The nonfunctional requirements are defined in the SRS document.
- [Software Requirements Specification](./software_requirements.md/#40-non-functional-requirements)
