{book: true, sample: false}

# Chapter 4 - Arrays
 
#### What is an array?

An array is a data structure which is a collection of elements having same datatype stored in a contiguous memory location.

There are 3 types of arrays:

*Indexed or Numeric Arrays* : An array with a numeric index where values are stored linearly.

*Associative Arrays* : An array with a string index where instead of linear storage, each value can be assigned a specific key.

*Multidimensional Arrays* : An array which contains single or multiple array within it and can be accessed via multiple indices.

Example:

```php
$a = array(); // declaration
$cars = array("Volvo", "BMW", "Toyota"); // initialization
```

#### How can you print an array in PHP?

1. Using print_r() method:

```php
$a = array ('a' => 'apple', 'b' => 'banana', 'c' => array ('x', 'y', 'z'));
print_r ($a);
```

Output:

```php
Array
(
    [a] => apple
    [b] => banana
    [c] => Array
        (
            [0] => x
            [1] => y
            [2] => z
        )
)
```

2. Using var_dump() method: This method is good at the time of debugging.

```php
$a = array(1, 2, array("a", "b", "c"));
var_dump($a);
```

Output:

```php
array(3) {
	[0]=>
	int(1)
	[1]=>
	int(2)
	[2]=>
	array(3) {
    [0]=>
    string(1) "a"
    [1]=>
    string(1) "b"
    [2]=>
    string(1) "c"
	}
}
```

#### What do we mean by the base address of an array?

The base address of an array is the memory location of the first element present in the array i.e., the 0th index element.

#### What do we mean by keys and values?

In arrays, keys are used to fetch the values at a certain location.
In associative arrays, we can use named key. 
Index arrays use numbers starting from 0 by default.

```php
// Method 1:
$age['Peter'] = "35"; //Peter, Ben & Joe are keys
$age['Ben'] = "37"; //35, 37 & 43 are values
$age['Joe'] = "43";

// Shorthand:
$age = array("Peter"=>"35", "Ben"=>"37", "Joe"=>"43");

// New in PHP 7:
$age = [35,37,43];

```

#### How can we convert array into string?

The implode() function returns a string from the elements of an array.
The implode() function accept its parameters in either order. However, for consistency with explode(), you should use the documented order of arguments.

Example:

```php
$arr = array('Hello','World!','Beautiful','Day!');
echo implode(" ",$arr);
```

Output:

```
Hello World! Beautiful Day!
```

#### How can we convert a string into an array elements?

The explode() function breaks a string into an array.

Syntax:

```php
explode(separator,string,limit)
```

The "separator" parameter cannot be an empty string.

Example:

```php
$str = "Hello world. It's a beautiful day.";
print_r (explode(" ",$str));
```

Output:

```
Array (
        [0] => Hello 
        [1] => world. 
        [2] => It's 
        [3] => a 
        [4] => beautiful 
        [5] => day.
    )
```

#### How can we concatenate arrays in PHP?

Using the `array_merge()` method. The array_merge() function merges one or more arrays into one array.

Example:

```php
$a1 = array("red", "green");
$a2 = array("blue", "yellow");
print_r(array_merge($a1, $a2));
```

Output:

```php
Array (
    [0] => red 
    [1] => green 
    [2] => blue 
    [3] => yellow
    );
```

#### Which function counts all the values of an array?

`array_count_values()` function is used to count all the values of an array. PHP `array_count_values()` returns an array that has the values of given array as keys and their frequency in the array as values.

```php
<?php
$a=array("Delhi","Pune","Agra","Delhi","Agra");
print_r(array_count_values($a));
```

Output:
```
Array
(
    [Delhi] => 2
    [Pune] => 1
    [Agra] => 2
)
```

#### How can we check if an element exists in an array?

The `in_array()` function is used to search for the given string in an array. It returns TRUE if the given string is found in the array, and FALSE otherwise.

#### Which function inserts an element to the end of an array?

PHP `array_push()` function is used to insert one or more elements to the end of an array.

#### What is the use of array_chunk() function?

The `array_chunk()` function is used to split an array into parts or chunks of new arrays.

Example:

```php
array_chunk(array,size);
```

The first parameter specifies an array and the second parameter defines the size of each chunk.

#### Why do we use extract()?

The `extract()` function imports variables into the local symbol table from an array.
This function uses array keys as variable names and values as variable values. For each element it will create a variable in the current symbol table.
This function returns the number of variables extracted on success.

Example:

```php
$a = "Original";
$my_array = array("a" => "Cat","b" => "Dog", "c" => "Horse");
extract($my_array);
echo "\$a = $a; \$b = $b; \$c = $c";
```

Output:

```
$a = Cat; $b = Dog; $c = Horse
```
