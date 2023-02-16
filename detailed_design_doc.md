# Detailed Design Document
# VOX - Realtime Groupchat App

February 24, 2023

Version 1

**INSERT LOGO HERE**

**Presented to**  
Dr Schwesinger

**Submitted By:**  
Hamad Ahmed  
Gabe Leffew  
Jesse Fullington  
Benjamin Lloyd  


## Revision History
| Date Created  | Version # |
| ------------- |:---------:|
| 2/15/2023     | 1         |


## 1.0 Introduction


## 1.2 Scope


## 2.0 Related Documents
- [Requirements Traceability Matrix](./Requirements_Traceability_Matrix.xlsx)
- [Software Requirements Specification](./software_requirements.md)

## 3.0 Design
### 3.1 Component Diagram

### 3.2 Entity Relationship Diagram
- [Entity Relationship Diagram](./Design%20Files/er_diagram.drawio)

#### 3.2.1 Database Setup

#### 3.2.2 How to utilize the methods
- To access the database, external software are available for this purpose. The software is utilizing is called DB Browser (SQLite). This provide us with a user interface that allows us to look at the tables. Moreover, sql queries can also be inputted to manipulate data. To run our application, the command "flask init-db" has to be executed in order to initialize the database. This is how it works with flask, a python's web framework.
### 3.3 Major Use Cases
#### 3.3.1 Create Account
- Story:
- Description: 
- Preconditions: none
- Postconditions: User gets access to the homepage screen
- Design Details:
- Constraints:
- Assumptions:

#### 3.3.2 User Login
- Story:
- Description:
- Preconditions: Must have an existing account
- Postconditions: none
- Design Details:
- Constraints:
- Assumptions:

#### 3.3.3 Create Vox Server
- Story:
- Description:
- Preconditions: Must have an existing account
- Postconditions: Server is established, User becomes the server admin of the created server.
- Design Details:
- Constraints:
- Assumptions:

#### 3.3.4 Chat on Servers
- Story:
- Description:
- Preconditions: Must have/be in a server
- Postconditions: None
- Design Details:
- Constraints:
- Assumptions:

#### 3.3.5 View/edit notebook
- Story:
- Description:
- Preconditions: Must have an account and be a part of a server
- Postconditions: Save notebook if changes were made
- Design Details:
- Constraints:
- Assumptions:

#### 3.3.6 Calendar
##### 3.3.6.1 Create event
- Story:
- Description:
- Preconditions: Must have an account
- Postconditions: Event is added to calendar
- Design Details:
- Constraints:
- Assumptions:

##### 3.3.6.2 Remove event 
- Story:
- Description:
- Preconditions: Must have an existing event
- Postconditions: Event is deleted from calendar
- Design Details:
- Constraints:
- Assumptions:

#### 3.3.8 Remove Users
- Story:
- Description:
- Preconditions: Have users in a server
- Postconditions: remove user from record of server
- Design Details:
- Constraints:
- Assumptions:

#### 3.3.9 Delete Server
- Story:
- Description:
- Preconditions: None
- Postconditions: deletes the server 
- Design Details:
- Constraints:
- Assumptions:

#### 3.3.10 Invite users to server
- Story:
- Description:
- Preconditions: Must have received a code 
- Postconditions: Sends invite notification to user asking them to join the server. 
- Design Details:
- Constraints:
- Assumptions:

### 3.4 Minor Use Cases
#### 3.4.1 Configure server permissions
- Story:
- Description:
- Preconditions: None
- Postconditions: The server preferences will be updated if anything changed.
- Design Details:
- Constraints:
- Assumptions:

#### 3.4.2 Set preferences/settings
- Story:
- Description:
- Preconditions: Must have an account
- Postconditions: Changes are saved if any were made
- Design Details:
- Constraints:
- Assumptions:


## 4.0 Systems
### 4.1 Architecture
Note: Remove these directions and replace with content
- diagram of architecture 
- description of overall architecture and what is running on each component 
- identify development, staging, and production environments 
- scripts to deploy to staging & production 


## 5.0 Non Functional Requirements
### 5.1 SSL Certificate
*Certificate is currently pending*

### 5.2 Performance Criteria
We would like to support up to 10 concurrent users. We believe this is enough to demonstrate the features listed and provide a better proof of concept before scaling the application would be required.