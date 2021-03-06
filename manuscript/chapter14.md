{book: true, sample: false}

# Chapter 14 - PHP and SQL

#### What is SQL?

SQL stands for Structured Query Language. SQL is a standardized query language for requesting information from different databases

#### Why do we need SQL with PHP?

In web applications, we need to store data. This data may relate to user, his activity, transaction and others. Modern applications store this data in RDBMS like MySQL or Oracle. To manage the data in these systems, we need SQL. Consider example of storing some user information in database:

```php
$data = "INSERT INTO users(firstname, lastname, email)
VALUES ('Maya', 'Sharma', 'maya@bootsity.com')";`
```


#### How many types of database connections possible in PHP.

- MySQLi (object-oriented)
- MySQLi (procedural)
- PDO

#### Adavantages of PDO over MySQLi approach.

1. Object Oriented
2. Bind parameters in statements (security)
3. Allows for prepared statements and rollback functionality (consistency)
4. Throws catcheable exceptions for better error handling (quality)
5. One API for a multiple of RDBMS brands

#### How connect to the database using PDO?

```php
$servername = "localhost";
$username = "username";
$password = "password";

try {
        $conn = new PDO("mysql:host=$servername", $username, $password);
        // set the PDO error mode to exception
        $conn->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
        $sql = "CREATE DATABASE myDBPDO";
        // use exec() because no results are returned
        $conn->exec($sql);
        echo "Database created successfully<br>";
    } catch(PDOException $e) {
        echo $sql . "<br>" . $e->getMessage();
    }
    $conn = null;
```

#### What is SQL injection?

SQL injection is a code injection technique that might destroy your database.
It usually occurs when you ask a user for input, like their username/userid, and instead of a name/id, the user gives you an SQL statement that you will unknowingly run on your database.

Consider: 

`SELECT * FROM Users WHERE UserId = 105 OR 1=1;`

The SQL above is valid and will return ALL rows from the "Users" table, since OR 1=1 is always TRUE.
A hacker might get access to all the user names and passwords in a database, by simply inserting 105 OR 1=1 into the input field.
Does the example above look dangerous? What if the "Users" table contains names and passwords?

