# VOX
###### Realtime Group Chat App
Document Version V2

## Software Development Documents
Names: Gabe Leffew, Hamad Ahmed, Ben Lloyd

| Date Created  | Version # |
| ------------- |:---------:|
| 10/7/2022     | 2         |
| 9/23/2022     | 1         |

## Product Description
- Our goal is to create a centralized location for collaboration in the classroom setting and beyond.
- Schedule events for your team and find the best team to tackle your toughest goals. 
- Save notes for classes and share with your group to always be on the same page. 
- Manage your groups and create a hierarchy as you see fit, whether you want one to rule them all or total anarchy.
- Create servers for any group like a club, a group of friends, or your tri-annual family reunion.

## Team Description

| Skills          | Hamad | Gabe | Ben |
| --------------- |:-----:|:----:|:---:|
| Git             | X | X | X
| Frontend        | X | X |   
| Backend         |   |   | X  
| UI              |   |   | X
| Database (SQL)  | X | X | X
| HTML/CSS        | X | X | 
| Web server      | X | X | X

### Skills required:
- General systems design
- Time management (estimates, finishing work in a timely fashion)

## Software Process Model Description : AGILE
 We believe this is a flexible model that will enable us to make rapid changes throughout our development process. It will also allow us to react quickly as we plan to learn about our project through its duration which will present design challenges that we will need to adapt to.
It is the de facto standard in software so this allows us to get more comfortable with the process before using it in the industry.
We believe this is a flexible model that will enable us to make rapid changes throughout our development process.
It sets a good foundation with iterations for design and implementation and will integrate with aspects of other methodologies such as Kanban and PERT chart

## Product Definition
### Context Diagram
TODO: Add picture here for context diagram

### User Story/ Persona
I am a college student who always forgets my due dates and can’t communicate effectively with my team members. If only there was one spot to see all this information, I would excel in my academic career. 
I am a football coach and can’t keep up with my rowdy team. Some of my dogs forget to come to  practice sometimes and other times they dont hand in their chicken barbecue fundraisers. I need a place to collaborate with my team and help my boys succeed.

### Use Cases
TODO: Add picture here of use case diagram 
### Use Case Description
#### 1. Name: Create Account
- Actors: User
- Preconditions: none
- Flow of events:
  1. User enters data
  2. Data is validated
  3. Data is stored in a database
- Postconditions: User gets access to the homepage screen
- Requirements: if b fails, account is not created with invalid data

#### 2. Name: User Login
- Actors: User and Server Admin
- Preconditions: Must have an existing account
- Flow of events:
  1. User inputs login information
  2. Input is validated
  3. Data is stored in a database
- Postconditions: 
- Requirements: If data is invalid, display wrong login and prompt to create an account 

#### 3. Name: Create Server
- Actors: User and Server Admin
- Preconditions: Must have an existing account
- Flow of events:
  1. Enter information about the server.
  2. Data is validated
  3. Data is stored in a database
- Postconditions: Server is established, User becomes the server admin of the created server.
- Requirements: If the input is invalid, display an error message about what is invalid and try again.

#### 4. Name: Call/chat on Servers
- Actors: Users and Server Admin
- Preconditions: Must have/be in a server with at least one other user.
- Flow of events:
  1. Select server
  2. Start a call/chat with another user
  3. Communicate
  4. End the call/chat
- Postcondition: None
Requirements: Must have/be in a server

#### 5. Name: View/edit notebook
- Actors: Users and Server Admin
- Preconditions: Must have an account
- Flow of events:
  1. Open notebook
  2. View content
  3. Make changes
  4. Share notebook with other users
- Postconditions: Save notebook if changes were made
- Requirements: Must have an existing notebook

#### 6. Name: View/edit Calendar
- Actors: Users and Server Admin
- Preconditions: Must have an account
- Flow of events:
  1. Open calendar
  2. View content
  3. Delete/add events
  4. Respond to invites for events
- Postconditions: If changes were made, the calendar is updated
- Requirements: Cannot see server events if you are not in a server

#### 7. Name: Set preferences/settings
- Actors: User and Server Admin
- Preconditions: Must have an account
- Flow of events:
  1. Open settings menu
  2. Change settings
  3. Apply changes
- Postconditions: Changes are saved if any were made
- Requirements: none

#### 8. Name: Configure server permissions
- Actors: Server Admin
- Preconditions: 
- Server must be created
  1. Must be admin of server
  2. Flow of events:
  3. Open server settings
  4. Configure settings
  5. Save settings
- Postconditions: The server preferences will be updated if anything changed.
- Requirements: None  

#### 9. Name: Remove Users
- Actors: Server Admin
- Preconditions: 
- Have users in a server
  1. Must be admin of server
  2. Flow of events:
  3. Select user in server
  4. Confirmation on doing so
- Postconditions: remove user from record of server
- Requirements: None

#### 10. Name: Delete Server
- Actors: Server Admin
- Preconditions: 
- Server must be created
  1. Must be admin of server
  2. Flow of events:
  3. Go to settings
  4. Select to delete
  5. Confirmation to delete server, mention it is not reversible 
- Postconditions: deletes the server 
- Requirements: None

## Wireframes
TODO: add file to repo
WireFrame_Rough_Draft.pdf*see attached file

## Project Organization
### Responsibility Matrix
| Skills          | Hamad | Gabe | Ben |
| --------------- |:-----:|:----:|:---:|
| Git             | X | X | X
| Frontend        | X | X |   
| Backend         |   |   | X  
| UI              |   |   | X
| Database (SQL)  | X | X | X
| HTML/CSS        | X | X | 
| Web server      | X | X | X



## Validation Plan
The definition of done can be described as completing all use case conditions to allow users to communicate effectively while using features within the app. 
Success from our point of view is to have a functioning app where two users can communicate whether it be by sharing files, chatting, or calling. 

## Feasibility Study    
### Risk Identification
With being an online application, we need to make sure that we have security for users' personal data. Whether it be their login credentials or communications. Since chats and files exchanged between users will be saved, there will be a lot of personal data, and attacks on our database without a secure system are a big risk. 
Another risk is the lack of knowledge for creating our application, this is our first time creating an application of this scale, as well as our first time working with most of these technologies. So, when it comes time to create some of these features, we could find ourselves spending more time learning rather than developing a feature. This in turn may limit some of the features and capabilities of our application.
Since we’re planning on having so many features within our application, there is more room for bugs. If we have bugs and problems in our program it could question the reliability of the application. It may also pose difficulty when trying to implement new features into the application.

### Risk Prioritization
Lack of knowledge
Reliability
Security    

### Risk Mitigation
A way we can keep our knowledge up to date is to always keep learning about how to implement features within our application. For security, we can implement hash functions to encrypt the user’s personal data. Reliability can be held to a high standard by implementing code checks while creating the application to review and change code to be most reliable before finish. Security will not be of high priority in this project and instead we plan to focus on the system design.

## Configuration and Version Control
- Our application will utilize semantic versioning MAJOR.MINOR.PATCH
  - MAJOR - Major changes, Incompatible API changes
  - MINOR - Minor features
  - PATCH - Bug fixes
- Our documents will be versioned by the semantic MAJOR
  - MAJOR - changes after group reflection of documents
  - The design document will also be tracked by Git from V2 onwards

## Tools
- Programming Languages: Frontend language, backend language
- VS Code
- Database Management System: SQL
- Web Server

## Architecture
- Hardware:
  - System to host the server
  - Active internet connection
- Software:
  - Browser to use the application
- Research:
  - Deploying to a web server









