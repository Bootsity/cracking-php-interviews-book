{book: true, sample: false}

# Chapter 3 - Flow control and Iterations

#### Explain if-else statement.

The if statement is a way to make decisions based upon the result of a condition. 
For example:

```php
$result = 70;
if ($result >= 57) {
	echo "Pass";
} else {
	echo "Fail";
}
```

Output:

```
Pass
```

#### Explain switch statement with example.

Switch statement works same as if statements. However the difference is that they can check for multiple values. Also, you can do the same with multiple if..else statements, but this is not always the best approach.

```php
$flower = "rose";
switch ($flower) {
	case "rose" : 
 		echo $flower." costs $2.50";
 		break;
	case "daisy" : 
 		echo $flower." costs $1.25";
 		break;
	case "orchild" : 
 		echo $flower." costs $1.50";
 		break;
	default : 
 	    echo "There is no such flower in our shop";
 	break;
}
```

Output:

```
rose costs $2.50
```

#### Differentiate between switch and if-else statement.

- **Check the testing expression**: An if-then-else statement can test expressions based on ranges of values or conditions, whereas a switch statement tests expressions based only on a single integer, enumerated value, or string.

- **switch is better for multi way branching**: When compiler compiles a switch statement, it will inspect each of the case constants and create a *jump table* that it will use for selecting the path of execution depending on the value of the expression. Therefore, if we need to select among a large group of values, a switch statement will run much faster than the equivalent logic coded using a sequence of if-elses. The compiler can do this because it knows that the case constants are all the same type and simply must be compared for equality with the switch expression, while in case of if expressions, the compiler has no such knowledge.

- **if-else is better for boolean values**: if-else conditional branches are great for variable conditions that result into a boolean, whereas switch statements are great for fixed data values.

- **Speed**: A switch statement might prove to be faster sometimes when there are more if-else in if-else ladder.

- **Clarity in readability**: A switch looks much cleaner when you have to combine cases. if-else are quite vulnerable to errors too. Missing an else statement can land you up in havoc. Adding/removing labels is also easier with a switch and makes your code significantly easier to change and maintain.


#### What are the different types of operators?

1. Arithmetic operators
2. Assignment operators
3. Logical operators
4. Comparison operators
5. Unary operators

#### Explain arithmetic operators.

| Operator      | Use           |
| ------------- |-------------|
| +      | to add numbers |
| -     | subtract two numbers      |
| * | to multiply two numbers      |
| / | to divide one number by another      |
| % | to divide two numbers and return the remainder |


#### Explain the assignment operators.

`$a = 10;`

stores the value 10 in the variable $a

#### Explain the logical operators.

| Operator      | Use           |
| ------------- |-------------|
| &&      | It returns true, if both expression1 and expression2 are true. |
| !     | It returns true, if expression is false.      |
| `||` | It returns true, if either expression1 or expression2 or both of them are true.     |


#### Explain the unary operators.

| Operator      | Use           |
| ------------- |-------------|
| ++      | Used to increment the value of an operand by 1. |
| --     | Used to decrement the value of an operand by 1.      |

#### Explain the comparison operators.

| Operator      | Use           |
| ------------- |-------------|
| ==      | Equals |
| !=     | Doesn't equal      |
| >     | Is greater than      |
| <     | Is less than      |
| >=     | Is greater than or equal to      |
| <=     | Is less than or equal to      |
| ===     | Identical (same value and same type)      |
| !==     | Not Identical      |


#### Differentiate between === and == operators in PHP.

The operator == casts between two different types if they are different, while the === operator performs a typesafe comparison that means it will only return true if both operands have the same type and the same value.

Examples:

```php
1 === 1: true
1 == 1: true
1 === "1": false // 1 is an integer, "1" is a string
1 == "1": true // "1" gets casted to an integer, which is 1
"foo" === "foo": true // both operands are strings and have the same value
```

#### Explain pre and post increment with example.

| Operator      | Use           | Explanation |
| ------------- |-------------|---------------|
| Pre-increment     | ++$a | increments $a by one, then returns $a. |
| Post-increment     | $a++ | returns $a, then increments $a by one. |
| Pre-decrement     | --$a | decrements $a by one, then returns $a. |
| Post-decrement     | $a-- | returns $a, then decrements $a by one. |


#### What do you mean by operator overloading?

Operator overloading (less commonly known as ad-hoc polymorphism) is a specific case of polymorphism (part of the OO nature of the language) in which some or all operators like +, = or == are treated as polymorphic functions and as such have different behaviors depending on the types of its arguments. Operator overloading is usually only syntactic sugar. It can easily be emulated using function calls.

#### How many loops are available in PHP?

There are several types of loops in PHP.

- while
- do-while
- for
- foreach

#### Explain while loop with example.

- The while loop evaluates the test expression.
- If the test expression is true (nonzero), codes inside the body of while loop are executed. The test expression is evaluated again. The process goes on until the test expression is false.
- When the test expression is false, the while loop is terminated.

Example:

```php
$x = 1; 
while($x <= 5) {
    echo "The number is: $x <br>";
    $x++;
}
```

Output:

```
The number is: 1 
The number is: 2 
The number is: 3 
The number is: 4 
The number is: 5
```

#### Explain do-while loop with example.

The do...while loop will always execute the block of code once, it will then check the condition, and repeat the loop while the specified condition is true.

Example:

```php
$x = 1; 
do {
	echo "The number is: $x <br>";
	$x++;
} while ($x <= 5);
```

In the above example, first a variable $x is set to 1 ($x = 1). Then, the do while loop will write some output, and then increment the variable $x with 1. Then the condition is checked (is $x less than, or equal to 5?), and the loop will continue to run as long as $x is less than, or equal to 5.

#### Explain for loop with example.

```php
for (init counter; test counter; increment counter) {
	code to be executed;
}
``` 

loop has 3 arguments.
- init counter: Initialize the loop counter value
- test counter: Evaluated for each loop iteration. If it evaluates to TRUE, the loop continues. If it evaluates to FALSE, the loop ends.
- increment/decrement counter: Increases/decreases the loop counter value.

Example:

```php
for ($x = 0; $x <= 10; $x++) {
	echo "The number is: $x <br>";
} 
```

Output:

```
The number is: 0 
The number is: 1 
The number is: 2 
The number is: 3 
The number is: 4 
The number is: 5 
The number is: 6 
The number is: 7 
The number is: 8 
The number is: 9 
The number is: 10 
```

#### Explain foreach loop with example.

The foreach provides an easy way to iterate over associative arrays. foreach works only on arrays and objects, and will issue an error when you try to use it on a variable with a different data type or an uninitialized variable. There are two syntaxes:

```php
foreach (array_expression as $value)
	statement

foreach (array_expression as $key => $value)
    statement
```

The first foreach loops over the array given by array_expression. On each iteration, the value of the current element is assigned to $value and the internal array pointer is advanced by one (so on the next iteration, you'll be looking at the next element).

The second form will additionally assign the current element's key to the $key variable on each iteration.

#### How can you implement an infinite loop in PHP?

This 3 loops can be used to achieve infinite loops in PHP.
1. while
2. do-while
3. for

Examples:

```php
while (1)
//statement`

for (;;;)
//statement`

do {
//statement
}

while (1) {
}
```

In all the above 3 cases, the loops will execute infinite times as the condition is always true i.e., it returns 1 for `while` and `do-while` loops and no ending condition for the `for` loop.

#### How can you implement recursion in PHP?

Recursion is the phenomenon of calling a function from within itself.

```php
function factorial($n) {
	// Base case
	if ($n == 0) {
		echo "Base case: \$n = 0. Returning 1...<br>";
    	return 1;
	}
		
	// Recursion
	echo "\$n = $n: Computing $n * factorial(".($n-1).")...<br>";
	$result = ($n * factorial($n-1));
	echo "Result of $n * factorial(" .($n-1).") = $result. Returning $result...<br>";
	return $result;
}

echo "The factorial of 5 is: " . factorial(5);
```

Output:
```
The factorial of 5 is: 120
```

#### Differentiate between iteration and recursion.

- The primary difference between recursion and iteration is that is a recursion is a process, always applied to a function. The iteration is applied to the set of instructions which we want to get repeatedly executed.
- Recursion is usually much slower because all function calls must be stored in a stack to allow the return back to the caller functions. In many cases, memory has to be allocated and copied to implement scope isolation.

#### Explain break statement with example.

When a break statement is encountered inside a loop, the loop is immediately terminated and the program control resumes at the next statement following the loop. It can be used to terminate a case in the switch statement.

Example:

```php
for ($a = 1; $a < 6; $a++) {
	echo $a;
	if ($a > 3) {
	    break;
	}
}
```

Output:

```
1234
```

#### Explain continue statement with example.

The continue statement is used inside loops. When a continue statement is encountered inside a loop, control jumps to the beginning of the loop for next iteration, skipping the execution of statements inside the body of loop for the current iteration.

```php
for ($a = 1; $a < 6; $a++) {
	if ($a == 3) {
		continue;
	}
	echo $a;
}
```

Output:

```
1235 (As it skipped 4 due to the continue statement)
```

#### Give example of declaration in php?

The declare construct is used to set execution directives for a block of code. The syntax of declare is similar to the syntax of other flow control constructs:

```php
declare(ticks=1);

// A function called on each tick event
function tick_handler() {
	echo "tick_handler() called\n";
}

register_tick_function('tick_handler');

$a = 1;
if ($a > 0) {
	$a += 2;
	print($a);
}
```

Output:
```
tick_handler() called tick_handler() called tick_handler() called 3tick_handler() called tick_handler() called
```

#### What is require in PHP?
Require is identical to include except upon failure it will also produce a fatal E_COMPILE_ERROR level error. In other words, it will halt the script whereas include only emits a warning (E_WARNING) which allows the script to continue.

Syntax:
```php
require('somefile.php');
```

