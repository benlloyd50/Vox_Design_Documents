# Test Cases
## Project: Vox Realtime Groupchat App

### Test Title: Create Account
#### Executed by:
#### SRS Section Id:
- Description:
- Preconditions:
- Dependencies:

| Step # | Test Step | Data | Expected | Actual | Status | Notes |
|-:|-|-|-|-|-|-|
|change|me|not|the|above|line|-|

### Test Title: User Login
#### Executed by:
#### SRS Section Id:
- Description:
- Preconditions:
- Dependencies:

| Step # | Test Step | Data | Expected | Actual | Status | Notes |
|-:|-|-|-|-|-|-|
|change|me|not|the|above|line|-|

### Test Title: Create Vox Server
#### Executed by:
#### SRS Section Id:
- Description:
- Preconditions:
- Dependencies:

| Step # | Test Step | Data | Expected | Actual | Status | Notes |
|-:|-|-|-|-|-|-|
|change|me|not|the|above|line|-|

### Test Title: Chat on Servers
#### Executed by:
#### SRS Section Id:
- Description:
- Preconditions:
- Dependencies:

| Step # | Test Step | Data | Expected | Actual | Status | Notes |
|-:|-|-|-|-|-|-|
|change|me|not|the|above|line|-|

### Test Title: View/Edit Notebook
#### Executed by:
#### SRS Section Id: 3.5.1
- Description: A user may create a notebook for each server they are in. 
    The contents should be able to be saved manually or when they close the notebook.
- Preconditions: Must have an account and be part of a server
- Dependencies: Database for holding notebook entries

| Step # | Test Step | Data | Expected | Actual | Status | Notes |
|-:|-|-|-|-|-|-|
|1| Open notebook in server | User credentials and DB | The user should recieve their notes from the db if any | | | |
|2| Edit notebook and make changes if needed | | | | | This step is optional since they may not have changes to make |
|3| Close notebook | Notebook entry will be sent to DB | | | | PUT (Update or Create) the notebook entry |

### Test Title: View Shared Notebook
#### Executed by:
#### SRS Section Id: 3.5.2
- Description: A user of a server may share their notebook with other users of the same server. 
    This would be viewable in a column that would show who all in the server shares their notes and the 
    user would be able to choose any of them.
- Preconditions: A user must be part of a server and another user must have shared their notebook
- Dependencies: Database for holding notebook entries

| Step # | Test Step | Data | Expected | Actual | Status | Notes |
|-:|-|-|-|-|-|-|
|1| Open shared notebook in server | User credentials and DB | The user should recieve a copy of another person's notes| | | This may be outdated if the other user is updating the notes, this is intended |
|2| View notes | | | | | READ ONLY on other user's notes|
|3| Close notes | | | | | Does not update entry |

### Test Title: Share Notebook with Server
#### Executed by:
#### SRS Section Id: 3.5.2
- Description: A user of a server may share their notebook with other users of the same server. 
- Preconditions: A user must be part of a server
- Dependencies: Database for holding notebook entries

| Step # | Test Step | Data | Expected | Actual | Status | Notes |
|-:|-|-|-|-|-|-|
|1| Open notebook in server | User credentials and DB | To be able to see their notebook | | | |
|2| Enable sharing | | User checks option to enable sharing on notebook | | | |
|3| Close notes | | Notebook is updated in DB to enable sharing | | | |

### Test Title: Create Event
#### Executed by:
#### SRS Section Id:
- Description:
- Preconditions:
- Dependencies:

| Step # | Test Step | Data | Expected | Actual | Status | Notes |
|-:|-|-|-|-|-|-|
|change|me|not|the|above|line|-|

### Test Title: Remove Event
#### Executed by:
#### SRS Section Id:
- Description:
- Preconditions:
- Dependencies:

| Step # | Test Step | Data | Expected | Actual | Status | Notes |
|-:|-|-|-|-|-|-|
|change|me|not|the|above|line|-|

### Test Title: Remove Users
#### Executed by:
#### SRS Section Id: 3.3.8
- Description: There should be the ability to remove a user from a server and possibly prevent them from being able to rejoin.
- Preconditions: Have users in a server other than the owner and be the owner of the server
- Dependencies: Database containing the server information

| Step # | Test Step | Data | Expected | Actual | Status | Notes |
|-:|-|-|-|-|-|-|
|1| Go to server| User credentials and DB | To see the users of a server | | | |
|2| Select user and click remove | | The user will get a confirmation on removing the user | | | |
|3| Confirm removal | | The user will no longer appear in the server | | | |

### Test Title: Delete Server
#### Executed by:
#### SRS Section Id:
- Description:
- Preconditions:
- Dependencies:

| Step # | Test Step | Data | Expected | Actual | Status | Notes |
|-:|-|-|-|-|-|-|
|change|me|not|the|above|line|-|

### Test Title: Invite User to server
#### Executed by:
#### SRS Section Id:
- Description:
- Preconditions:
- Dependencies:

| Step # | Test Step | Data | Expected | Actual | Status | Notes |
|-:|-|-|-|-|-|-|
|change|me|not|the|above|line|-|
