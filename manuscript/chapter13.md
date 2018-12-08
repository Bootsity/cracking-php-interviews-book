{book: true, sample: false}

# Chapter 13 - PHP and HTML

#### What is HTML?

Hypertext Markup Language (HTML) is the standard markup language for creating web pages and web applications.

```html
<HTML>
   <HEAD>
      <TITLE>Your Title Here</TITLE>
   </HEAD>
   <BODY BGCOLOR="FFFFFF">
      contents of page
   </BODY>
</HTML>
```

#### Differentiate between PHP and HTML.

- PHP is like the machinery behind a dynamic website whereas HTML is the structure and backbone of a website.
- HTML isn’t a programming language; it is a markup language that is used to create the structure of a webpage. PHP however is a full-blown programming language that is used to create most of the advanced functionality you see on modern webpages.

#### What are the different methods or HTTP verbs of sending data to the server?

| HTTP Verb      | Use           |
| ------------- |-------------|
| GET      | used to request data from a specified resource |
| POST     | used to send data to a server to create/update a resource   |
| PUT     | used to send data to a server to create/update a resource   |
| HEAD     | almost identical to GET, but without the response body   |
| OPTIONS     | describes the communication options for the target resource   |
| DELETE     | deletes the specified resource   |

#### What's the difference between GET and POST methods.

- For GET, parameters remain in browser history because they are part of the URL. POST parameters are not saved in browser history.
- GET data can be bookmarked.	In POST method, data can not be bookmarked.
- GET requests are re-executed but may not be re-submitted to server if the HTML is stored in the browser cache.	In POST method, the browser usually alerts the user that data will need to be re-submitted.
- Encoding type (enctype attribute)	application/x-www-form-urlencoded	multipart/form-data or application/x-www-form-urlencoded Use multipart encoding for binary data.
- Parameters	can send but the parameter data is limited to what we can stuff into the request line (URL). Safest to use less than 2K of parameters, some servers handle up to 64K	Can send parameters, including uploading files, to the server.
- GET data is easier to hack for script kiddies but POST data is more difficult to hack
- For GET, only ASCII characters are allowed.	No restrictions for POST. Binary data is also allowed.
Security	GET is less secure compared to POST because data sent 8.GET data is saved in browser history and server logs in plaintext.	POST is a little safer than GET because the parameters are not stored in browser history or in web server logs.
- Since form data is in the URL(for GET) and URL length is restricted. A safe URL length limit is often 2048 characters but varies by browser and web server.	No restrictions for POST method.
- GET method should not be used when sending passwords or other sensitive information.	POST method used when sending passwords or other sensitive information.
- GET method is visible to everyone (it will be displayed in the browser's address bar) and has limits on the amount of information to send. POST method variables are not displayed in the URL.
- GET can be cached whereas POST is not cached.


#### How can we send email?

The mail() function is used to send emails in PHP. Inside mail() function you can pass three basic and one optional parameters.
 
1. Three Basic Parameters : The email address to send(Receiver email), Subject of mail, Content/message of the mail.

2. Optional Parameters: additional headers you want to include(headers and sender mail)

```php
extract($_POST);
if (isset($sendmail)) {
	
    $subject = "Mail Function in PHP";
	$from = "info@bootsity.com";
	$message = $name. " " . $mobile . " " . $query;
    $headers = "From: ".$from;
    mail($email, $subject, $message, $headers);
  
	echo "<h3 align='center'>Mail Sent Successfully</h3>";
}	
 
```

HTML Form:


```html
<html>
<head>
	<title>Mail function in php - Bootsity</title>
</head>
<body>
<form method="post">
 <table align="center" border="1">
	<Tr>
	<th>Enter Your name</th>
	<td><input type="text" name="name"/></td>
	</tr>
	<tr>
		<th>Enter Your mobile</th>
		<td><input type="text" name="mobile"/></td>
	</tr>
	
	<tr>
		<th>Enter Your email</th>
		<td><input type="email" name="email"/></td>
	</tr>
	
	<tr>
		<th>Enter Your Query</th>
		<td><textarea name="query"></textarea></td>
	</tr>
		
	<tr>
		<td align="center" colspan="2">
		<input type="submit" value="Send Mail" name="sendmail"/>
		
	</tr>
	</table>	
</form>
</body>
</html>
```

In above example , a mail is sent to info@gmail.com which is receiver address. Subject, messages and headers are also given.


#### How file upload works?

First, we define FORM method as POST and enctype='multipart/form-data' both property must be defined for uploading a file.


```html
<html>
   <body>
	<form action="upload.php" enctype="multipart/form-data" method="post">
	  Your File Name <input type="file" name="file"/><br/>
	  <input type="submit" value="Upload" name="upload"/>
	</form>
   </body>
  </html>
```

The enctype attribute of the <form> tag specifies which content-type to use when submitting the form.

'multipart/form-data' is used when a form requires binary data, like the contents of a file, to be uploaded.

The type='file' attribute of the <input> tag specifies that the input should be processed as a file.

For example, when viewed in a browser, there will be a browse-button next to the input field.

Below is the code for upload.php

```php
    if ($_POST['upload']) {
    move_uploaded_file(
        $_FILES["file"]["tmp_name"],
        "upload/" . $_FILES["file"]["name"]
    );  

    echo "Upload: " . $_FILES["file"]["name"] . "<br>";

    echo "Type: " . $_FILES["file"]["type"] . "<br>";

    echo "Size: " . ($_FILES["file"]["size"] / 1024) . " kB<br>";

    echo "Stored in: " . $_FILES["file"]["tmp_name"];
}
```