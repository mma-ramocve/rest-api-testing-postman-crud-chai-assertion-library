# Rest API - testing process using Postman

## Project 

<https://documenter.getpostman.com/view/10013377/TVeng9Y9>

This is a project to demonstate the Rest API testing process on locally set environment. Concept applied is CRUD. 
[Chai Assertion Library](###https://www.chaijs.com/) is used.
API calls are divided into 4 folders:
        -   auth
        -   city
        -   profile
        -   users

- There are 47 requests containing 130 tests.
- Each test section involves deleting test data and restoring the initial state.

## Localhost source

<https://github.com/davellanedam/node-express-mongodb-jwt-rest-api-skeleton>

-   baseUrl: http://localhost:3000

-   Requirements for localhost:
    -   Node.js **10+**
    -   MongoDB **3.6+**
    -   Redis **5.0+**


## Features

### auth tests
-	GET /		- it should GET home API url
-	POST /login	- it should NOT POST login if body is empty
-	POST /login	- it should GET token
-	POST /register	- it should POST register	
-	POST /register	- it should NOT POST a register if email already exist	
-	POST /verify	- it should POST verify
-	POST /verify	- it should NOT POST verify if user is already verified
-	POST /forgot	- it should POST forgot
-	POST /reset	- it should POST reset
-	GET /token	- it should NOT be able to consume the route since no token was sent
-	GET /token	- it should GET a fresh token

### city tests
-	POST /login		- it should GET token (city)
-	GET /cities		- it should NOT be able to consume the route since no token was sent
-	GET /cities		- it should GET all the cities
-	GET /cities?filter...	- it should GET the cities with filters
-	POST /cities		- it should NOT POST a city without name
-	POST /cities		- it should POST a city
-	POST /cities		- it should NOT POST a city that already exists
-	GET /cities/:id		- it should GET a city by the given id
-	PATCH /cities/:id	- it should UPDATE a city given the id
-	DELETE /cities/:id	- it should DELETE a city given the id

### profile tests
-	POST /register	- it should POST user
-	POST /login	- it should GET token (profile)
-	GET /profile	- it should NOT be able to consume the route since no token was sent
-	GET /profile	- it should GET profile
-	PATCH /profile	- it should NOT UPDATE profile empty name/email
-	PATCH /profile	- it should UPDATE profile	
-	PATCH /profile	- it should NOT UPDATE profile with not valid URL´s
-	POST profile/changePassword	- it should NOT change password
-	POST profile/changePassword	- it should NOT change a too short password	
-	POST profile/changePassword	- it should change password

### user tests
-	POST /login	- it should GET token as admin (user)
-	POST /users	- it should POST user
-	POST /login	- it should GET token as user (user)
-	GET /users	- it should NOT be able to consume the route since no token was sent
-	GET /users	- it should GET all the users
-	GET /users?filter...	- it should GET the users with filters
-	POST /users	- it should NOT POST a user without name
-	POST /users	- it should POST a user
-	POST /users	- it should NOT POST a user with email that already exists
-	POST /users	- it should NOT POST a user with not known role
-	GET /users/:id	- it should GET a user by the given id
-	PATCH /users/:id	- it should UPDATE a user given the id
-	PATCH /users/:id	- it should NOT UPDATE a user with email that already exists
-	PATCH /users/:id	- it should NOT UPDATE another user if not an admin
-	DELETE /users/:id	- it should DELETE a user given the id



