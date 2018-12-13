{book: true, sample: false}

# Chapter 2 - Datatypes and variables

#### What is a datatype?

A data type is a classification that specifies which type of value a variable has and what type of mathematical, relational or logical operations can be applied to it without causing an error.

#### How many datatypes are there?

Built-in datatypes in PHP:
**Integer** - whole numbers
**String** - alphanumeric text
**Float** - decimal point numbers(also called double)
**Boolean** - represents logical values(TRUE or FALSE)
**Array** - collection of elements having same datatype
**Object** - stores data and information on how to process that data
**NULL** - no value
**Resource** - stores a reference to functions and resources external to PHP

#### What are rules for naming a variable?

Rules for naming a variable are following −

- Variable names must begin with a letter or underscore character.
- A variable name can consist of numbers, letters, underscores but you cannot use characters like + , - , % , ( , ) . & , etc.

#### How will you define a constant?

To define a constant you have to use `define()` function and to retrieve the value of a constant, you have to simply specifying its name. Unlike with variables, you do not need to have a constant with a $.

```php
define("MINSIZE", 50);
echo MINSIZE;
```

#### What is the purpose of constant() function?

As indicated by the name, this function will return the value of the constant. This is useful when you want to retrieve value of a constant, but you do not know its name, i.e. It is stored in a variable or returned by a function.

```php
define("MINSIZE", 50);
echo MINSIZE;
echo constant("MINSIZE"); // same thing as the previous line
```

Only scalar data (boolean, integer, float and string) can be contained in constants.

#### What are the differences between constants and variables?

- There is no need to write a dollar sign ($) before a constant, where as in variable one has to write a dollar sign.
- Constants cannot be defined by simple assignment, they may only be defined using the `define()` function.
- Constants may be defined and accessed anywhere without regard to variable scoping rules.
- Once the constants have been set, may not be redefined or undefined.

#### What are the different scopes of variables?

Variable scope is known as its boundary within which it can be visible or accessed from code. In other words, it is the context within which a variable is defined. There are only two scopes available in PHP namely local and global scopes.

- Local variables (local scope)
- Global variables (special global scope)
- Static variables (local scope)
- Function parameters (local scope)
When a variable is accessed outside its scope it will cause PHP error undefined variable.

#### What is string?

A string is a data type used to represent text. It is a set of characters that can also contain spaces and numbers. For example, the word "Bootsity" and the phrase "Bootsity PHP Tutorials" are both strings.
To declare strings we can write:

```php
$string = "bootsity";
```

#### What is the difference between single quoted string and double quoted string?

Singly quoted strings are treated almost literally, whereas doubly quoted strings replace variables with their values as well as specially interpreting certain character sequences.

```php
$variable = "name";
$stringEx = 'My $variable will not print!\\n';
print($stringEx);
$stringEx = "My $variable will print!\\n";
print($stringEx);
```

Output:

```
My $variable will not print!
My name will print
```

#### How can you convert string into array elements?

`explode()` function breaks a string into an array. Each of the array elements is a substring of string formed by splitting it on boundaries formed by the string delimiter.

Syntax: 

```php
explode(separator,string,limit);
```

#### How can you convert array into strings?
 
The `implode()` function returns a string from the elements of an array.
The `implode()` function accept its parameters in either order.
The separator parameter of `implode()` is optional. However, it is recommended to always use two parameters for backwards compatibility.

Syntax:

```php
implode(separator,array)
```

#### How can you concatenate two or more strings?

To concatenate two string variables together, use the dot (.) operator.

Example:

```php
$string1 = "Hi! i am";
$string2 = "50";
echo $string1 . " " . $string2;
```

Output:

```
Hi! i am 50
```

#### Differentiate between echo and print().

echo and print are more or less the same. They are both used to output data to the screen.

The differences are: 
- echo has no return value while print has a return value of 1 so it can be used in expressions. 
- echo can take multiple parameters (although such usage is rare) while print can take one argument. 
- echo is faster than print.


#### Explain static variables.

When a function is completed, all of its variables are normally deleted.

However, sometimes you want a local variable to not be deleted then use static keyword.

Example:

```php
function Test() {		
	static $x = 0;		
	echo $x;		
	$x++;		
}			
Test();		
Test();		
Test();	
```

Output:
```
0 1 2
```

#### What are PHP magic constants?

PHP provides a large number of predefined constants to any script which it runs known as magic constants. PHP magic constants start and end with underscore _

Example:

`_LINE_` gives the current line number of the file.

`_FILE_` denotes the full path and filename of the file. If used inside an include,the name of the included file is returned. Since PHP 4.0.2, `_FILE_` always contains an absolute path whereas in older versions it contained relative path under some circumstances.


#### Why do we need trim() function?

The trim() function removes whitespaces or other predefined characters from either of the sides(beginning and ending) of a string.


#### Can you count the number of words in a string?

The `str_word_count()` function counts the number of words in a string.

Example:

```php
echo str_word_count("Hello world!");
```

Output:

```
2
```

#### How to reverse a string?

`strrev()` reverses a string.

Example:

```php
echo strrev("Hello World!");
```

Output:

```
!dlroW olleH
```

#### How to find the position of a specific text in a string?

`strpos()` returns the position of the first occurrence of a string inside another string (case-sensitive). Also note that string positions start at 0, and not 1.

```php
echo strpos("I love Bootsity, PHP tutorials!","Bootsity");
```

Output:

```
7
```

#### How can you change cases in a string?

The `strtoupper()` function converts a string to uppercase and `strtolower()` function converts a string to uppercase.

Example:

```php
echo strtoupper("Hello WORLD!") . PHP_EOL;
echo strtolower("Hello WORLD!");
```

Output:

```
HELLO WORLD!
hello world!
```

#### Can you replace a substring?

The built-in function `str_replace()` replaces some characters in a string (case-sensitive).

Example:

```php
echo str_replace("world","Peter","Hello world!");
```

Here we have replaced the characters "world" in the string "Hello world!" with "Peter":

#### Differentiate between str_replace() and str_ireplace().

The `str_ireplace()` function php is not sensitive rule and will treat "abc","ABC" all combination as a single. 
The `str_ireplace()` will be less faster becuse it need to convert to the same case. But the difference will be very little event in a large data.
The `str_replace()` function is a case sensitive which means that it replaces the string that exactly matches the string exactly.

#### Differentiate between printf() and print().

`printf()` outputs a formatted string whereas `print()` outputs one or more strings.

Example:

```php
print "Hello world!";
```

Output:

```
Hello world!
```

Example:

```php
$number = 9;
$str = "Beijing";
printf("There are %u million bicycles in %s.", $number, $str);
```

Output:

```
There are 9 million bicycles in Beijing.
```

#### Differentiate between strstr() & strchr() functions.

Both the functions finds the first occurrence of a string inside another string so there is no difference. both are alias of each other.

#### Differentiate between strstr() and stristr().

`stristr()` and `strstr()` both finds the first occurrence of a string inside another string where stristr is case-insensitive but `strstr()` is case sensitive.

#### Can you encode a string in PHP?

`string urlencode (string $str )` function is used to encode a string in PHP. This function is convenient when encoding a string to be used in a query part of a URL, as a convenient way to pass variables to the next page.


#### Differentiate between strcmp() and strncmp().

Both the functions compare 2 strings(case-sensitive) but `strncmp()` compares the strings upto N numbers.

Example:

```php
echo strcmp("Hello world!","Hello earth!");
```

Output:

```
18 (As the strings are not fully same)
```

Example:

```php
echo strncmp("Hello world!","Hello earth!",6);
```

Output:

```
0 (As the strings are same upto first 6 characters)
```

#### Is it possible to remove the HTML tags from data?

The `strip_tags()` function strips a string from HTML, XML, and PHP tags.

#### What is the use of gettype() in PHP?

The `gettype()` is a predefined PHP function which is used to know the datatype of any variable.

#### What is heredoc and nowdoc?

heredoc and nowdoc allows strings to be defined in more than one line without string concatenation. A nowdoc is specified similarly to a heredoc, but no parsing is done inside a nowdoc. The construct is ideal for embedding PHP code or other large blocks of text without the need for escaping.

heredoc example:

```php
$name = "Bootsity";

$here_doc = <<<EOT
This is $name website
for PHP, Laravel and Angular Tutorials

EOT;

echo $here_doc;
```

Output:

```
This is Bootsity website
for PHP, Laravel and Angular Tutorials
```

nowdoc example:

```php
$name = "Bootsity";

$here_doc = <<<'EOT'
This is $name website
for PHP, Laravel and Angular Tutorials

EOT;

echo $here_doc;
```

Output:

```
This is $name website
for PHP, Laravel and Angular Tutorials
```

#### What is the function file_get_contents() useful for?

`file_get_contents()` lets reading a file and storing it in a string variable.


#### How is it possible to remove escape characters from a string?

The `stripslashes()` function enables us to remove the escape characters before apostrophes in a string.


#### Will a comparison of an integer 12 and a string "13" work in PHP?
"13" and 12 can be compared in PHP since it casts everything to the integer type.

#### Is it possible to protect special characters in a query string?

Yes, we use the `urlencode()` function can be used to protect special characters.

#### How to find the position of the first occurrence of a substring in a string
`strpos()` is used to find the position of the first occurrence of a substring in a string.


#### Distinguish between urlencode() and urldecode()?

The `urlencode()` method is best while encoding a string to be used in a query part of a URL. It returns a string in which all non-alphanumeric characters except -_. is replaced with a percentege(%) sign.

The `urldecode()` encodes URL to encode string as any % and other symbols are decoded.

#### Is it possible to remove the HTML tags from data?

The `strip_tags()` function enables us to clean a string from the HTML tags.

