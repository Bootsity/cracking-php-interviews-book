{book: true, sample: true}

# Chapter 5 - Functions

#### What is a function?

A named section of a program that performs a specific task is called a function. In this sense, a function is a type of procedure or routine.

A valid function name starts with a letter or underscore, followed by any number of letters, numbers, or underscores.

Example:

```php  
// Function to say hello
function functionToSayHello() {  
    echo "Hello";
}  

// Function to find length of the string
echo strlen ("Earth");
```

#### What are different types of functions?

Types of functions on basis of definition

1. Built-in functions
2. User defined functions

Types of functions on the basis on parameters

1. Non parameterized function
2. Parameterized function

Example:

```php  
// Declaring user-defined function
function thisIsUserDefinedFunc() {  
    echo "Hello! from user defined function" 
}  

function thisIsAnotherUserDefinedFunc($name) {  
    echo "Hello! $name from user defined function" 
} 

// Calling user defined function
thisIsUserDefinedFunc();

// Calling Built-in function
echo strlen ("Earth");

// Non parameterized function 
thisIsUserDefinedFunc();

// Parameterised function 
thisIsAnotherUserDefinedFunc("Rohit");
?>
```

#### What do we mean by "call by value" of function

When we call a function by value, the value of the parameterised variable is passed to the called function. Any changes to variable inside the called functions are not reflected to the original parameterised variable.

Example:

```php  
function adder($str2) {  
    $str2 .= 'Call By Value';  
}  
$str = 'Hello ';  
adder($str);  
echo $str;  
```

Output:

```
Hello
```

#### What do we mean by "call by reference"

In case of call by reference, actual value is modified if it is modified inside the function. In such case, we need to use `&` symbol with formal arguments. The & represents reference of the variable.

Example:

```php  
function adder(&$str2) {  
    $str2 .= 'Call By Reference';  
}
$str = 'This is ';  
adder($str);  
echo $str;  
```

Output:
```
This is Call By Reference
```

#### What do we mean by actual and formal parameters?

Arguments which are mentioned in the function call is known as the actual arguments. For example:

`func1(12, 23);`

here 12 and 23 are actual arguments.
Actual arguments can be constant, variables, expressions etc.

Arguments which are mentioned in the definition of the function is called formal arguments. Formal arguments are very similar to local variables inside the function. Just like local variables, formal arguments are destroyed when the function ends.

```php
function factorial($n) {
    // write logic here
}
```
Here n is the formal parameters.

#### Maximum how many arguments are allowed in a function in PHP?

There is no limit but you can use `func_get_args()`, `func_get_arg()` and `func_num_args()` to avoid writing all the arguments in the function definition.

#### Explain header().

The header() function sends a raw HTTP header to a client.

Syntax:

```php
header(string,replace,http_response_code)
```

Here the `string` specifies the header string to send.

#### What do we mean by return type of a function?

The return type is similar to a datatype of a function. The common return types are: int, string, float, boolean etc. All the functions don't always need to have a return type.

#### What is the return type of a function that doesn't return anything?

`void` which mean nothing.

#### Do we need to mention the return type of a function explicitly in PHP?

No need to specify return type upon declaration but needs to use `return` statement within the body of the function.

#### What is function that can be used to build a function that accepts any number of arguments?

`func_num_args()` returns the number of arguments passed to the function.
`func_get_args(void)`
Gets an array of the function's argument list.

#### Explain the `return` statement.

return statement immediately terminates the execution of a function when it is called from within that function.
If no parameter is supplied	NULL is returned.

#### Can we use multiple return statements in a function?

Yes but not in consecutive lines. We should then use the statements upon different conditions otherwise it will throw an error.

Example:
```php
function demo() {
    if (condition)
        return expression1;
    else
        return expression2;
}
```

#### What is the use of ini_set()?

PHP allows the user to modify some of its settings mentioned in php.ini using ini_set(). This function requires two string arguments. First one is the name of the setting to be modified and the second one is the new value to be assigned to it.

Given line of code will enable the display_error setting for the script if it’s disabled.

`ini_set('display_errors', '1');`

We need to put the above statement, at the top of the script so that, the setting remains enabled till the end. Also, the values set via ini_set() are applicable, only to the current script. Thereafter, PHP will start using the original values from php.ini.

#### What is the difference between unlink and unset functions?

`unlink()` function is useful for file system handling. We use this function when we want to delete the files (physically). Example:

```php
$xx = fopen('sample.html', 'a');
fwrite($xx, '<h1>Hello !!</h1>');
fclose($xx);
unlink('sample.html');
```

`unset()` function performs variable management. It makes a variable undefined. Or we can say that unset() changes the value of a given variable to null. Thus, in PHP if a user wants to destroy a variable, it uses unset(). It can remove a single variable, multiple variables, or an element from an array. Let’s see a sample code.

```php
$val = 200;
echo $val; // Output will be 200
$val1 = unset($val);
echo $val1; // Output will be null
```

```php
unset($val);  // remove a single variable
unset($val1, $val2, $val3); // remove multiple variables
```

#### How ereg() function works?

The ereg() function searches a string specified by string for a string specified by pattern, returning true if the pattern is found, and false otherwise.

#### How eregi() function works?

eregi() − The eregi() function searches throughout a string specified by pattern for a string specified by string. The search is not case sensitive.

#### What is the purpose of getdate() function?

The function getdate() optionally accepts a time stamp and returns an associative array containing information about the date. If you omit the time stamp, it works with the current time stamp as returned by time().

#### What is the purpose of date() function?

The date() function returns a formatted string representing a date. You can exercise an enormous amount of control over the format that date() returns with a string argument that you must pass to it.

#### How will you call member functions of a class?

After creating your objects, you will be able to call member functions related to that object. One member function will be able to process member variable of related object only. Following example shows how to set title and prices for the three books by calling member functions.

```php
$physics−>setTitle("Physics for High School");
$chemistry−>setTitle("Advanced Chemistry");
$maths−>setTitle("Algebra");
$physics−>setPrice(10);
$chemistry−>setPrice(15);
$maths−>setPrice(7);
```
