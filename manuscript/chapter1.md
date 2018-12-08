{book: true, sample: false}

# Chapter 1 - PHP Platform

#### What is PHP?

PHP or Hypertext Pre-processor is a general purpose programming language written in C and used by developers to create dynamic web applications. PHP Supports both Procedural Programming and Object Oriented Programming.

PHP files generally have extension .php and PHP code is generally written between `<?php ... ?>` tags. 
A hello world program is:
    
```php
<?php
    echo "hello world";
?>
```

#### Is PHP case sensitive?

In PHP, variable names are case-sensitive but function names are not case sensitive. If we define function name in lowercase, but calling them in uppercase it will work. So, PHP can be called as partially case-sensitive language.

#### Is PHP weakly typed language?

Yes, because we don’t need to mention the datatype of variables while declaring it. Variables are automatically type casted when the values are inserted in it.

#### How do we install PHP?

PHP is a cross-platform language and we do have multiple choices to install PHP on different operating systems. We can download PHP from official website and install it or we can make use of popular bundles like XAMPP and WAMP for Windows, LAMP for Linux and MAMP for iOS.


#### What is Composer?

Composer is an application-level package manager for the PHP applications that provides a standard system for managing dependencies of different libraries and others. Some of the features of composer are: 

- dependency resolution for PHP packages
- keeping all packages updated
- support autoloading out of the box
- hooks to execute pre and post commands

To manage dependencies, composer uses composer.json file, which looks like:

```javascript
{
    "autoload": {
        "psr-0": {
            "": "src/"
        }
    },
    "require": {
        "php": ">=5.3.2"
    },
    "config": {
        "bin-dir": "bin"
    }
}
```

#### What is Packagist?

Packagist is the primary package repository for Composer. This is where developers publish their packages or libraries that can be used by other developers which are using composer.

#### How do we execute a PHP script from the command line?

To execute PHP files from command line, we can use any CLI or shell and pass the .php file to the php executable. An example is below:

```
~ /path/to/php /path/to/script.php
```

#### What is virtual host?

Virtual hosting is a method for hosting multiple domain names (with separate handling of each name) on a single server (or pool of servers). This allows one server to share its resources, such as memory and processor cycles, without requiring all services provided to use the same host name. 

#### What are XAMPP & WAMP?

These are installable packages that can be used to setup development environments on windows machines easily.

WAMP: acronym for Windows Operating System, Apache(Web server), MySQL Database and PHP Language.
XAMPP: acronym for X (any Operating System), Apache (Web server), MySQL Database, PHP Language and PERL.

#### What is Apache server?

Apache is a web server used to handle HTTP Request/Response. After we enable PHP module in Apache, it accepts HTTP requests from the client and passes it to PHP interpreter. PHP interpreter performs actions according to HTTP Request and sends back the response to Apache. Apache then wraps it as a HTTP response and sends back to client. 

#### How to check current PHP version and other information about our system?

We can use function `php_info();` inside scripts and using command `php -v` from command line.


#### What is interpreter?

PHP interpreter executes command from a PHP script line by line and provides the output to the executer.


#### Is PHP compiled or interpreted?

Both, PHP is compiled down to an intermediate bytecode that is then interpreted by the runtime engine.

*PHP compiler* is responsible for:
- convert code to a bytecode that can be used by runtime engine.
- resolve functions, names and classes names
- creating symbol table

then, *PHP Interpretor* does: 
- Goes through the bytecode line by line and executes it
- Handles runtime exception

#### What do we mean by a Framework?

A framework is a layered structure indicating what kind of programs can or should be built and how they would interrelate. Some computer system frameworks also include actual programs, specify programming interfaces, or offer programming tools for using the frameworks.
Example: Laravel, Zend, CakePHP

#### What is MVC?

MVC is an application design pattern that separates the application data and business logic (model) from the presentation (view). MVC stands for Model, View & Controller. The controller mediates between the models and views.