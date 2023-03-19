# User Stories

The following notes are loosely based on the book "Designing APIs with Swagger and OpenAPI" by Joshua S. Ponelat and Lukas L. Rosenstock (https://www.manning.com/books/designing-apis-with-swagger-and-openapi).

​	User stories are generally written using the following template, but the "so that" clause is optional and the prefix, "as a <*role*>" will be omitted from each of the sections below for brevity:

```
As a <role>, I can <capability>, so that <receive_benefit>.
```

User stories that depend on other stories will use the following template:

```
Given <prerequisite>, I can <capability>.
```



## Member Stories

###### A member is a registered user that can be found in the member directory.

- I can register a new account and choose my role, so that I can log in.
- I can log into my account, so that I can use the member directory and see private members and projects.
- I can post a project, so that other members can see what I'm working on.
- I can see a list of projects that I created.
- Given that I created a project, I can view and modify its details.
- Given that I created a project, I can delete it.
- Given that I created a project, I can post project updates.
- I can view a list of other users in the directory.
- I can send messages to other users.
- I can receive messages from other users.
- I can view a list of messages that I sent to other members.
- Given that I sent messages to other users, I can see a list of conversations with other members.
- I can modify my account details.
- I can delete my account.


## Organizer Stories

###### An organizer is a person that hosts events and/or manages a group/club consisting of members.

- I can register a new account and choose my role so that I can log in.
- I can log into my account, so that I can contact and manage members of my organization.
- I can modify my account details.
- I can delete my account.


## Admin Stories

- I can register a new account and choose my role so that I can log in.
- I can log into my account, so that I can access admin functionality.
- I can modify my account details.
- I can modify other users' account details.
- I can edit projects that other users have posted.
- I can delete my account.



```mermaid
---
title: Casual Coding - Member Directory Domain Model
---
classDiagram
    class User {
        - ID
        - Fullname
        - EmailAddress
        - Roles
        - Bio
        - ImageUrls
        - Experience
        - SocialLinks
        - CreatedAt
        (1) Register
        (2) Login
        (3) View
        (4) Modify
        (5) Delete
    }
    class Project {
    	- ID
    	- Title
    	- Description
    	- ImageUrls
    	- CreatedAt
    	() Create
    	() ListMyOwn
    	() ListAll
    	() View
    	() Modify
    	() Delete
    }
    class Message{
    	- ID
    	- Content
    	- SenderID
    	- RecipientID
    	- CreatedAt
    	(1) Create
    	(2) Delete
    }
	User --> Project : Creates
	User --> Message : Sends

    
```
