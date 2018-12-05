{book: true, sample: false}

# Chapter 7 - Sessions and Cookies

#### What is Session?

A session is a temporary and interactive information interchange between two or more communicating devices, or between a computer and user. Session is stored at the server side.

#### What is Cookie?

Cookie is a small text file (generally up to 4KB) created by a website that is stored in the user's computer either temporarily for that session only or permanently. Cookies provide a way for the website to recognize you and keep track of your preferences and other functionalities like shopping cart.

#### Differentiate between Session & Cookie.

| Cookies      | Sessions           |
| ------------- |-------------|
| stored in browser as text file.      | server side |
| can store limited data     | can store unlimited data      |
| data is on client side and hence easily accessible | data is on server side and is difficult ot access      |


#### How do we start a session?

Using `session_start()` method at the beginning of the script.

#### How can we set session variable?

Session variables are set with the PHP global variable $_SESSION

Example:

```php
// Set session variables
$_SESSION["favcolor"] = "green";
$_SESSION["favanimal"] = "cat";
echo "Session variables are set.";
```

#### How to destroy a session?

Using `session_destroy()` method at the end of the script.

#### How to remove value from session variable?

`session_unset()` method

#### When do we need to set session variables?

When a particular user signs in, adds items to cart - to track the particular user activity.
Session variables must be set after using `session_start();`

#### When do we need a session and not a cookie?

- Cookies are stored on the client side, so they can be viewed, edited and deleted by the user. So be careful to not store and sensitive information on cookies.
Sessions are used when more sensitive information like password or id is being passed. Sessions are not accessible by users and hence more secure.
- You want to store important information such as the user id more securely on the server where malicious users cannot temper with them.
- You want to pass values from one page to another.
- You want the alternative to cookies on browsers that do not support cookies.
- You want to store global variables in an efficient and more secure way compared to passing them in the URL
You are developing an application such as a shopping cart that has to temporary store information with a capacity larger than 4KB.

#### When do we need a cookie and not a session?

- Http is a stateless protocol; cookies allow us to track the state of the application using small files stored on the user’s computer.

The path were the cookies are stored depends on the browser.

Internet Explorer usually stores them in Temporal Internet Files folder.

- Personalizing the user experience – this is achieved by allowing users to select their preferences.

- The page requested that follow are personalized based on the set preferences in the cookies.

- Tracking the pages visited by a user

- Also, cookies last longer than that of a session.

#### How can we set a cookie?

Using 
`setcookie(name, value, expire, path, domain, secure, httponly);`

#### How to modify a cookie value?

To modify a cookie, just set (again) the cookie using the setcookie() function.

#### How will we make a check that a cookie is set or not?

You can use isset() function to check if a cookie is set or not.

#### How to retrieve all cookie values?

```php 
print_r($_COOKIE);
```

Output:
```
Array ([user] => abhi [age] => 25 [profile] => developer)
```

#### How to delete a cookie?

When deleting a cookie you should assure that the expiration date is in the past.

```php
// set the expiration date to one hour ago
setcookie("user", "abhi", time()-60*60);
```

#### How can we implement 'remember me' using PHP?

As the name indicate the meaning that cookies are the method to store the information of a web
page in a remote browser,those information can be retrieved form the browser itself,when the
same user comes back to that page.

The browser stores the message in a small text file that the server embeds on the user’s system.You can set cookies using the setcookie()function.

PHP transparently supports HTTP cookies,so setcookie() must be called before any
output is sent to the browser.

#### Classify cookies.

There are 2 types of cookies: 
1. Session Based which expire at the end of the session.
2. Persistent cookies which are written on harddisk.

#### How will you delete a cookie?

To delete a cookie you should call setcookie() with the name argument only.

#### How to track login and logout using PHP?

Session variable must be set when a user logs in and session needs to be destroyed upon logout.