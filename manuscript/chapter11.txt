{book: true, sample: false}

# Chapter 11 - Exception Handling

#### What do you mean by an exception?

An exception is a problem that arised during the execution of a program. When an Exception occurs the normal flow of the program is disrupted and the program or application terminates abnormally.

#### Define Exception class Hierarchy.

Throwable
 -- Error
   -- Arithmetic Error
   -- Parse Error
 -- Exception
   -- Logic Exception
   -- Runtime Exception


#### How do we handle exceptions?

When an exception is thrown, code following the statement will not be executed, and PHP will attempt to find the first matching catch block. If an exception is not caught, a PHP Fatal Error will be issued with an "Uncaught Exception".
An exception can be thrown, and caught within PHP. 

To handle exceptions, code may be surrounded in a try block.
Each try must have at least one corresponding catch block. Multiple catch blocks can be used to catch different classes of exceptions.
Exceptions can be thrown (or re-thrown) within a catch block.

Consider:

```php
try {
    print "this is our try block n";
    throw new Exception();
} catch (Exception $e) {
    print "something went wrong, caught yah! n";
} finally {
    print "this part is always executed n";
}
```

#### Differentiate between exception and error.

- Recovering from Error is not possible. The only solution to errors is to terminate the execution. Where as you can recover from Exception by using either try-catch blocks or throwing exception back to caller.
- You will not be able to handle the Errors using try-catch blocks. Even if you handle them using try-catch blocks, your application will not recover if they happen. On the other hand, Exceptions can be handled using try-catch blocks and can make program flow normal if they happen.
- Exceptions are related to application where as Errors are related to environment in which application is running.


#### What do we mean by error log?

By default, PHP sends an error log to the server's logging system or a file, depending on how the `error_log` configuration is set in the php.ini file. By using the error_log() function you can send error logs to a specified file or a remote destination.


#### How do we see PHP errors?

Display errors could be turned off in the php.ini or your Apache config file. You can turn it on in the script: `error_reporting(E_ALL);` `ini_set('display_errors', 1);` You should see the same messages in the PHP error log.


#### What are the exception class functions?

There are following functions which can be used from Exception class.
`getMessage()` − message of exception
`getCode()` − code of exception
`getFile()` − source filename
`getLine()` − source line
`getTrace()` − n array of the `backtrace()`
`getTraceAsString()` − formated string of trace

#### What does the expression `Exception::__toString` means?

`Exception::__toString` gives the string representation of the exception.