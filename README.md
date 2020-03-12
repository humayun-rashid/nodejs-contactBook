What is RESTful API?
REST stands for REpresentational State Transfer and is used to access and manipulate data using several stateless operations. These operations are integral to the HTTP protocol and represent an essential CRUD functionality (Create, Read, Update, Delete).Using the above-listed operations and a resource name as an address, we can build a REST API by basically creating an endpoint for each operation.
https://www.toptal.com/nodejs/secure-rest-api-in-nodejs

The HTTP operations available are:

POST (create a resource or generally provide data)
GET (retrieve an index of resources or an individual resource)
PUT (create or replace a resource)
PATCH (update/modify a resource)
DELETE (remove a resource)

# nodejs-contactBook
Install Following things.
  1. Node and NPM
  2. Visual Studio Code 
  3. Git 
Configure your git profile. 
Create a git repo. Name it with your project name. In my case I named it "NodeJs-ContactBook". Now, open a terminal. Write down the following command. 


```
git clone "your repo link"
```

Replace the repo link with your link. Go to the directory and open visual studio code by folloing command.

```
cd nodejs-ContactBook
code .
```

Let's do -

```
npm init -y
```
It will create package.json and package-lock.json.

Let's install express Now install Express in the myapp directory and save it in the dependencies list.

```
npm install express --save
```
We will use nodemon. Let's install nodemon globally.
nodemon is a tool that helps develop node.js based applications by automatically restarting the node application when file changes in the directory are detected. nodemon does not require any additional changes to your code or method of development. nodemon is a replacement wrapper for node, to use nodemon replace the word node on the command line when executing your script.
Either through cloning with git or by using npm (the recommended way):

npm install -g nodemon
And nodemon will be installed globally to your system path.

You can also install nodemon as a development dependency:

npm install --save-dev nodemon

Basic Express
LEt's create basic example that's also available in Express website.

```
const express = require('express')
const app = express()
const port = 3000

app.get('/', function (req, res) {
  res.send('Hello World!')
} )

app.listen(port, function () {
  console.log(`Example app listening on port ${port}!`)
})
```
Lets run the app. First try with node and then we will try it with nodemon and try to understand what is the difference.
What's happening here?

This app starts a server and listens on port 3000 for connections. The app responds with “Hello World!” for requests to the root URL (/) or route. For every other path, it will respond with a 404 Not Found.

HTTP Method 
HTTP defines a set of request methods to indicate the desired action to be performed for a given resource. Although they can also be nouns, these request methods are sometimes referred to as HTTP verbs. Each of them implements a different semantic, but some common features are shared by a group of them: e.g. a request method can be safe, idempotent, or cacheable.

GET
The GET method requests a representation of the specified resource. Requests using GET should only retrieve data.
HEAD
The HEAD method asks for a response identical to that of a GET request, but without the response body.
POST
The POST method is used to submit an entity to the specified resource, often causing a change in state or side effects on the server.HTTP defines a set of request methods to indicate the desired action to be performed for a given resource. Although they can also be nouns, these request methods are sometimes referred to as HTTP verbs. Each of them implements a different semantic, but some common features are shared by a group of them: e.g. a request method can be safe, idempotent, or cacheable.

GET
The GET method requests a representation of the specified resource. Requests using GET should only retrieve data.
HEAD
The HEAD method asks for a response identical to that of a GET request, but without the response body.
POST
The POST method is used to submit an entity to the specified resource, often causing a change in state or side effects on the server.

Routing 

Routing refers to determining how an application responds to a client request to a particular endpoint, which is a URI (or path) and a specific HTTP request method (GET, POST, and so on).

Each route can have one or more handler functions, which are executed when the route is matched.

Route definition takes the following structure:

app.METHOD(PATH, HANDLER)
Where:

app is an instance of express.
METHOD is an HTTP request method, in lowercase.
PATH is a path on the server.
HANDLER is the function executed when the route is matched.

Create Basic Routing and test
app.get('/', function (req, res) {
  res.send('Hello World!')
})
Respond to POST request on the root route (/), the application’s home page:

app.post('/', function (req, res) {
  res.send('Got a POST request')
})
Respond to a PUT request to the /user route:

app.put('/user', function (req, res) {
  res.send('Got a PUT request at /user')
})
Respond to a DELETE request to the /user route:

app.delete('/user', function (req, res) {
  res.send('Got a DELETE request at /user')
})

Test them using .rest, Insomonia or Postman. 
 Will be updated.

Contact Book
In this tutorial, we are going to create a pretty common but practical REST API for a resource called users.

Our resource will have the following basic structure:

id (an auto-generated UUID)
firstName
lastName
email
password
permissionLevel (used to control user’s permissions)
And we will create the following operations for that resource:

[POST] endpoint/users
[GET] endpoint/users (list users)
[GET] endpoint/users/:userId (get specific user)
[PATCH] endpoint/users/:userId (update the data for the specified user)
[DELETE] endpoint/users/:userId (remove the specified user)

