# Software Requirement Specifications
## Revision History
|Date Created|Author|Distributed to|Version|
|----|:----:|:-----------:|:-----:|
|4/20/2023|Team|Team & Supervisor|6|
|3/10/2023|Team|Team & Supervisor|5|
|2/15/2023|Team|Team & Supervisor|4|
|1/27/2023|Team|Team & Supervisor|3|
|12/8/2022|Team|Team & Supervisor|2|
|10/24/2022|Team|Team & Supervisor|1|

## 1.0 Introduction
Our goal is to create a centralized location for collaboration in the classroom setting and beyond. Schedule events for your team and find the best team to tackle your toughest goals. Save notes for classes and share with your group to always be on the same page. Create servers for any group like a club, a group of friends, or your tri-annual family reunion.

The purpose of this document is to establish a common understanding between the development team and supervisor. Included are all our diagrams and documentation outlining what is needed to consider this a complete project. In turn, this document will be a single source of truth to make sure everyone is up to date on any changes. Along with requirements for project is also who will be responsible for what. This document may change, and revision will be noted above and tracked with Git to view previous information. 

### Scope
![System Context Diagram](./Images/system_context.jpg)

#### Use Case Diagram
![Use Case Diagram](./Images/usecase_diagram.png)

- [Personas](./design_document.md#personas)

## 2.0 Related Documents
- [Software Development Plan](./design_document.md#vox)

![Pert Chart](./Images/pertchart.png)

### Responsibility Matrix
| Skills          | Hamad | Gabe | Ben | 
| --------------- |:-----:|:----:|:---:|
| Git             | X | X | X | 
| Frontend        | X | X |   | 
| Backend         |   |   | X | 
| UI              |   |   | X | 
| Database (SQL)  | X | X | X | 
| HTML/CSS        | X | X |   | 
| Web server      | X | X | X | 

## 3.0 Requirements
#### As a user I want to:
- Create an account
- Login 
- Chat on servers
- View/Edit Notebook
- Create Calendar Events
- Invite Users
- Create a Server
- Make events for myself

#### As a server admin I want to:
- Do everything that a user can do 
- Remove users from my server
- Delete my server
- Create events for a server I own

## Use Cases
### 3.1 Create Account
- Actors: User
- Preconditions: none
- Flow of events:
  1. User clicks `Register` on landing page
  2. User enters username and password
  3. Data is validated
  4. Data is stored in a database
- Postconditions: User gets access to the homepage screen
- Requirements: If step 2 fails, account is not created with invalid data, create account form is cleared and errors are displayed.
- Interface Requirements: A create account screen and landing page

### 3.2 User Login
- Actors: User and Server Admin
- Preconditions: Must have an existing account
- Flow of events:
  1. User clicks `Login` on landing page
  2. User inputs login information
  3. Input is validated 
- Postconditions: None
- Requirements: If step 3 fails, display errors and reload login page
- Interface Requirements: A login screen

### 3.3 Create Vox Server
- Actors: User and Server Admin
- Preconditions: Must have an existing account
- Flow of events:
  1. Enter information about the server.
  2. Data is validated
  3. Data is stored in a database
- Postconditions: Server is established, User becomes the server admin of the created server.
- Requirements: If step 2 fails, display an error message about what is invalid and try again.
- Interface Requirements: Create Server button and input box

### 3.4 Chat on Servers
- Actors: Users and Server Admin
- Preconditions: Must be in a server
- Flow of events:
  1. Select server
  2. Enter messages in chat box and send
  3. Receive messages from other users
- Postconditions: None
- Requirements: None
- Interface Requirements: A server chatroom

### 3.5 View/edit notebook
- Actors: Users and Server Admin
- Preconditions: Must have an account and be a part of a server
- Flow of events:
  1. Select server
  2. Click `Notepad`
  3. Open notebook from the left panel or name a new notepad
  4. Make changes
  5. Enable share notebook with other users
  6. Click `Save` to save the notebook
- Postconditions: Save notebook in database if save was selected
- Requirements: None
- Interface Requirements: Server screen, and notebook screen

### 3.6 Calendar
- Actors: Users and Server Admin 

![Calendar Use Cases](./Images/calendar_usecase.jpg)

#### 3.6.1 Create event
##### 3.6.1.1 Create personal event
- Preconditions: Must have an account
- Flow of events:
  1. Go to home screen
  2. Click `Create Personal Event`
  3. Enter name and date for event
- Postconditions: Event is added to calendar
- Requirements: None
- Other requirements: None
- Interface Requirements: Home page screen

##### 3.6.1.1 Create server event
- Preconditions: Must have an account and own the server you wish to make the event for
- Flow of events:
  1. Go to server
  2. Click `Create Event` in hamburger menu
  3. Enter name and date for event
- Postconditions: Event is added to calendar
- Requirements: None
- Other requirements: None
- Interface Requirements: Server page screen

#### 3.6.2 Remove event 
- Preconditions: Must have an existing event and be a server admin if it's a server event
- Flow of events:
  1. Select `Delete Event` on homepage or in server
  2. Click the event you wish to delete
  3. Confirm deletion 
- Postconditions: Event is deleted from database and no user can see the event
- Requirements: None
- Interface Requirements: Home page screen and server page screen

### 3.7 Remove Users
- Actors: Server Admin
- Preconditions: Have users in a server
- Flow of events:
  1. Select `Remove User`
  1. Select user from list
  3. Confirm you wish to remove the user
- Postconditions: Remove user from record of server
- Requirements: None
- Interface Requirements: Server screen, message to confirm

### 3.8 Delete Server
- Actors: Server Admin
- Preconditions: None
- Flow of events:
  1. Go to server
  1. Select `Delete Server` from hamburger menu
  3. Confirm to delete server
- Postconditions: Deletes the server and related records 
- Requirements: None
- Interface Requirements: Server screen, message to confirm

### 3.9 Invite users to server
- Actors: Server Admin
- Preconditions: Created a server
- Flow of events:
  1. Go to server
  2. Select `Invite Users`
  3. Send code to people via alternative source
- Postconditions: None
- Requirements: None
- Interface Requirements: Server screen

## 4.0 Non-functional Requirements

### 4.1 Other systems
- Database server
- Web Server System

### 4.2 Security
- SSL Certificate
- Encrypted sensitive information should have **2048** bits of entropy

### 4.3 Performance 
- Responses sent between users should be received in **< 500 ms**
- For self testing purposes the application can be self hosted and ran without external parties needing to set up anything
- We would like to support up to 10 concurrent users. We believe this is enough to demonstrate the features listed and provide a better proof of concept before scaling the application would be required.

### 4.4 Maintainability
- The program will have an open source license on Github. This will allow for a central location for issues regarding the application to be stored. On a per issue basis, we will try to fix any security critical or performance critical bugs. Quality of life and small improvements will be left up to the community or the team's discretion to add unless an overwhelming demand is presented.

## 5.0 Architecture
![Hardware Architecture](./Images/architecture.jpg)

## AGREED TO:

### Supervisor

#### Signature

#### Name: Dr Schwesinger

#### Title:

#### Date:

## AGREED TO:

#### Team members

#### Signature

#### Name: Hamad Ahmed

#### Title:

#### Date:

#### Signature

#### Name: Gabe Leffew

#### Title:

#### Date:

#### Signature

#### Name: Ben Lloyd

#### Title:

#### Date: