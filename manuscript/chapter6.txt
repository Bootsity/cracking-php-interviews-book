{book: true, sample: false}

# Chapter 6 - Requests and responses

#### How can we display the correct URL of the current webpage?

```php
echo 'http://' . $_SERVER['HTTP_HOST'] . $_SERVER['REQUEST_URI']; 
```
gives us the entire URL of the current webpage.

#### How to get the information about the uploaded file in the receiving script?

```php
$_FILES[$fieldName]['name'] // The Original file name on the browser system. 
$_FILES[$fieldName]['type'] // The file type determined by the browser. 
$_FILES[$fieldName]['size'] // The Number of bytes of the file content. 
$_FILES[$fieldName]['tmp_name'] // The temporary filename of the file in which the uploaded file was stored on the server. 
$_FILES[$fieldName]['error'] // The error code associated with this file upload.
```

#### What do we mean by server?

A server is a computer program that provides a service to another computer programs (and its user).
In the client/server programming model, a server program awaits and fulfills requests from client programs, which may be running in the same or other computers.

#### What is a client?

A client is the receiving end of a service or the requestor of a service in a client/server model type of system. The client is most often located on another system or computer, which can be accessed via a network. This term was first used for devices that could not run their own programs, and were connected to remote computers that could via a network.

#### What do you mean by a response?

Response to an event or to something that is generated according to the request from the client side to the server.

#### What is HTTP?

The Hypertext Transfer Protocol (HTTP) is designed to enable communications between clients and servers.

HTTP works as a request-response protocol between a client and server.
A web browser may be the client, and an application on a computer that hosts a web site may be the server.

Example: A client (browser) submits an HTTP request to the server; then the server returns a response to the client. The response contains status information about the request and may also contain the requested content.

#### What are PHP superglobals?

Several predefined variables in PHP are "superglobals", which means that they are always accessible, regardless of scope - and you can access them from any function, class or file without having to do anything special.

The PHP superglobal variables are:

$GLOBALS
$_SERVER
$_REQUEST
$_POST
$_GET
$_FILES
$_ENV
$_COOKIE
$_SESSION

#### How will we get information sent via GET method?

The PHP provides `$_GET` associative array to access all the sent information using GET method.

#### How will you get information sent via POST method?

The `$_POST` associative array to access all the sent information using POST method.

#### What is the purpse $_REQUEST variable?

The PHP `$_REQUEST` variable contains the contents of both `$_GET`, `$_POST`, and `$_COOKIE`. The PHP $_REQUEST variable can be used to get the result from form data sent with both the GET and POST methods.

#### What is the purpose of $_FILES variable?

This is a global PHP variable. This variable is an associate double dimension array and keeps all the information related to uploaded file.

#### What is the purpose of $GLOBALS variable in PHP?

It contains a reference to every variable which is currently available within the global scope of the script. The keys of this array are the names of the global variables.

#### What is the purpose of $_SERVER variable in PHP?

$_SERVER − This is an array containing information such as headers, paths, and script locations. The entries in this array are created by the web server. There is no guarantee that every web server will provide any of these. See next section for a complete list of all the SERVER variables.

#### What is the purpose of $_COOKIE variable in PHP?

An associative array of variables passed to the current script via HTTP cookies.

#### What do you mean by environment variable in PHP?

- PHP environment variables allow your scripts to glean certain types of data dynamically from the server. ...
- You can access these variables using the `$_SERVER` and `$_ENV` arrays.

#### What is the purpose of $_ENV variable in PHP?

$_ENV is a superglobal that contains environment variables. Environment variables are provided by the shell under which PHP is running, so they may vary according to different shells.

#### What is the purpose of $_SESSION variable in PHP?

$_SESSION − An associative array containing session variables available to the current script.

#### How will you redirect a page?

The header() function supplies raw HTTP headers to the browser and can be used to redirect it to another location. The redirection script should be at the very top of the page to prevent any other part of the page from loading. The target is specified by the Location: header as the argument to the header() function. After calling this function the exit() function can be used to halt parsing of rest of the code.

#### What is the purpose `$_PHP_SELF` variable?

The default variable `$_PHP_SELF` is used for the PHP script name and when you click "submit" button then same PHP script will be called.

#### How will you get the browser's details using PHP?

One of the environemnt variables set by PHP is `HTTP_USER_AGENT` which identifies the user's browser and operating system.

#### What do you mean by HTTP status codes?

Status codes are issued by a server in response to a client's request made to the server. The first digit of the status code specifies one of five standard classes of responses. The message phrases shown are typical, but any human-readable alternative may be provided.

#### What are the HTTP client error codes?

The HTTP client error codes start with 4. Example: 404 is used for 'not found' status.

#### What are the informational status codes?

1xx: Informational
It means the request has been received and the process is continuing.


#### What are the HTTP success codes?

2xx: Success
It means the action was successfully received, understood, and accepted.


#### How do you get the redirection related information?

3xx: Redirection
It means further action must be taken in order to complete the request.


#### What are the HTTP client error codes?

4xx: Client Error
It means the client sent an invalid request.

#### What are the HTTP server error codes?

5xx: Server Error
It means the server failed to fulfill an apparently valid request.


#### What is API?

Application Program Interface is a set of functions and procedures that allow the creation of applications which access the features or data of an operating system, application, or other service.

#### What is the use of an API?

Basically, an API specifies how software components should interact. Additionally, APIs are used when programming graphical user interface (GUI) components. A good API makes it easier to develop a program by providing all the building blocks. A programmer then puts the blocks together.

#### What are types of API?

Most often-used types of web service:
1. SOAP.
2. XML-RPC.
3. JSON-RPC.
4. REST.

#### What is REST API?

REST stands for "REpresentational State Transfer". It is a concept or architecture for managing information over the internet. REST concepts are referred to as resources. A representation of a resource must be stateless. It is usually represented by JSON.
API stands for "Application Programming Interface". It is a set of rules that allows one piece of software application to talk to another. Those "rules" can include create, read, update and delete operations.

####  Why do we need REST API?

In many applications, REST API is a need because this is the lightest way to create, read, update or delete information between different applications over the internet or HTTP protocol. This information is presented to the user in an instant especially if you use JavaScript to render the data on a webpage.

#### Where REST API is used?

REST API can be used by any application that can connect to the internet. If data from an application can be created, read, updated or deleted using another application, it usually means a REST API is used.

#### What is JSON?

JSON: JavaScript Object Notation.
JSON is a syntax for storing and exchanging data.
JSON is text, written with JavaScript object notation.

#### Why do we need JSON?

1. For sending data
2. For receiving data

#### How can you exchange data using JSON?

While exchanging data between a browser and a server, the data can only be text.
JSON is text, and we can convert any JavaScript object into JSON, and send JSON to the server.
We can also convert any JSON received from the server into JavaScript objects.
This way we can work with the data as JavaScript objects, with no complicated parsing and translations.

#### Differentiate between JSON & XML.

1. JSON doesn't use end tag
2. JSON is shorter
3. JSON is quicker to read and write
4. JSON can use arrays
5. XML has to be parsed with an XML parser. JSON can be parsed by a standard JavaScript function
 
#### What are the advantages of JSON?

JSON is easier to parse. JSON follows simple steps like:
1. Fetch a JSON string
2. JSON.Parse the JSON string

Using XML:

1. Fetch an XML document
2. Use the XML DOM to loop through the document
3. Extract values and store in variables