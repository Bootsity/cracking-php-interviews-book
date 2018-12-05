{book: true, sample: false}

# Chapter 9 - Regular Expressions

#### What is RegEx?

RegEx or Regular Expressions is a way to express how a computer program should look for a specified pattern in text and then what the program is to do when each pattern match is found. 
For example, a regular expression could tell a program to search for all text lines that contain the word "Windows 95" and then to print out each line in which a match is found or substitute another text sequence (for example, just "Windows") where any match occurs.

#### Why do we need RegEx?

- Regular expressions simplify identifying patterns in string data by calling a single function. This saves us coding time.
- When validating user input such as email address, domain names, telephone numbers, IP addresses,
Highlighting keywords in search results
- When creating a custom HTML template. Regular expressions can be used to identify the template tags and replace them with actual data.

#### How preg_match() function works?

The preg_match() function searches string for pattern, returning true if pattern exists, and false otherwise.

```php
$my_url = "www.bootsity.com";
echo preg_match("/boot/", $my_url); // prints true
```

#### Regualar Expression Notations.

| Expression      | Description           |
| ------------- |-------------|
| p+      | matches any string containing at least one p. |
| p*     | matches any string containing zero or more p's.      |
| p? | matches any string containing zero or one p's.      |
| p{N} | matches any string containing a sequence of N p's      |
| p{2,3} | matches any string containing a sequence of two or three p's.      |
| p{2, } | matches any string containing a sequence of at least two p's.      |
| p$ | matches any string with p at the end of it.     |
| ^p | matches any string with p at the beginning of it.     |


#### Regualar Expression Examples.

| Expression      | Description           |
| ------------- |-------------|
| [^a-zA-Z]      | matches any string not containing any of the characters ranging from a through z and A through Z. |
| p.p    | matches any string containing p, followed by any character, in turn followed by another p.     |
| ^.{2}$ | matches any string containing exactly two characters.     |
| <b>(.*)</b> | It matches any string enclosed within <b> and </b>.      |
| p(hp)* | matches any string containing a p followed by zero or more instances of the sequence php.      |
