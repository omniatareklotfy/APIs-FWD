# API Automation Testing

## FWD API Automation Testing
### Firstly, there are 2 projects (Test fakerestapi.azurewebsites APIs , Test TRELLO REST APIs)
-- Any Folder has (Test Cases File , Collection, Environment , Test Run by Postman, Generated Report by Newman)
### First One (Test fakerestapi.azurewebsites APIs)
- Go to this website http://fakerestapi.azurewebsites.net/index.html
- You need to get familiar with how to execute requests on Swagger before going to Postman.
- We will focus on requests under the "Authors" section.
- Now, let's get started with Swagger to execute a request and check the response.
- Under "Authors" click on any request like GET /api/v1/Authors.
- Click on "Try it out" then click on "Execute".
- "Responses" section will be displayed including some response components like (Code, Response body then Response headers).
- Note that you won't be able to write test cases on Swagger unlike Postman, so we are only testing with our eyes and use Notepad or any Editor to log our test case results.

### Second One (Test TRELLO REST APIs)
- SignUp with a new account on https://trello.com/.
- Login and explore Trello UI before working on APIs.
- Learn how to add boards inside the default workspace.
- Inside each Board, there are 3 lists created by default [To Do, Doing, Done], you could also add new lists if you wish.
- Under each list, you could add cards, move cards from one list to another, Archive Cards, and many other actions.
- Take a screenshot of the new lists, and cards you have created.

#### Get your credential values and try the first Trello API.
- Create a workspace for "Trello".
- Create a new collection with any name.
- Try this first request, https://api.trello.com/1/members/me.
- The response will be an "invalid token" which means you don't have the authority to access this API.
--  So now you realize that you need to get your account credentials which will be sent with every request so the server will detect who you are and execute your request - if you have permission to make this request.
- To get your account credentials, go to this website https://developer.atlassian.com/cloud/trello/, and log in with the same account you're using to log in to Trello.
- After login, open the same URL, https://developer.atlassian.com/cloud/trello/, and make sure you're selecting "Guides" at the top of the page.
- On the left side click on the option "TRELLO'S REST API" and click on "Authorization" under it, if you get lost, navigate directly to this URL, https://developer.atlassian.com/cloud/trello/guides/rest-api/authorization/, but make sure first you're already logged in.
- Remember we need to get account credentials and know how to use them inside the request (for e.x should we send it with query parameters or headers, etc), in this page, you will realize that those credentials consist of two things
* key=value
* token=value
* You will also realize that those two should be used as query parameters (you will find this info under this section "Authorization via Query Parameters" on this page at the end).
- So now we already know how Authorization works but we need to know how to get those key, token values for your account, click on this link shown on the page, https://trello.com/app-key/, you will find it at the beginning of the page under the section "Authorizing A Client". It should direct you to another page that contains your credentials, key, and token.


### Using Postman Scripts

### Using Newman to Generate Reports

#### Installation
 - npm install -g newman
 - npm install -g newman-reporter-htmlextra
#### Running
 - newman run collection.json -e environment.json
#### Running with Generate Report
 - newman run collection.json -r htmlextra
 - newman run collection.json -e env.json --reporters cli,junit,htmlextra --reporter-htmlextra-export reportName.html
 /*newman run WATCHiT_APIs_Testing.json -e WATCHiT_Staging.json --reporters cli,junit,htmlextra --reporter-htmlextra-export Automation-APIs-WatchIT.html*/
