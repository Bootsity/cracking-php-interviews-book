{book: true, sample: false}

# Chapter 8 - Filesystem management

#### How to create a file?

`touch()` function is used to create a file.

Example:

```php
// create text file
touch("data.txt");
```

#### What are the other way to write in a file?

An alternative way to write data to a file is to create a file pointer with `fopen()`, and then write data to the pointer using PHP’s `fwrite()` function.

Example:

```php
// open and lock file 
$fo=fopen("output.txt","w");
flock($fo,LOCK_EX) or die('ERROR:cannot lock file');

// write string to file
$data="A fish out of water";
fwrite($fo, $data);

// unlock and close file
flock($fo,LOCK_UN) or die('ERROR:cannot unlock file');
fclose($fo);
echo "Data written to file";
```

#### How will you check if a file exists or not using php?

File's existence can be confirmed using `file_exist()` function which takes file name as an argument.

#### How to delete a file?

unlink( ) function is used to delete a file.

Example:
```
// delete text file
unlink("data.txt");
```

#### How to copy a file?

Example:
```php
// copy text file
copy("data.txt","update data.txt");
```

#### How to rename file?

`rename()` function is used to rename file.

Example:
```php
// rename text file
rename("data.txt","update data.txt");
```


#### How to check whether a file or directory exists?

`file_exists()` function is used to check file or directory existence.

Example:
```php
// check file existence
echo file_exists("Update resume.doc");
```

Output: 
```
1
```

#### How to check path of the file in PHP?

`realpath()` function is used to check real path of the file.

Example:
```php
// check real path of the file
echo realpath("Update resume.doc");
```

#### How to check size of the file in PHP?

The files length can be found using the `filesize()` function which takes the file name as its argument and returns the size of the file expressed in bytes.

Example:
```php	
// check file size
echo filesize("notes.txt")." Bytes";
```

Output:
```
190 Bytes
```

#### How to write the contents inside file?

`file_put_contents()` accepts a filename and path, together with the data to be written to the file, and then writes the latter to the former

Example:
```php
// write string to file
$data = "A fish out of water";
file_put_contents("output.txt", $data) or die('ERROR: Can not write file');
echo "data written inside  this file";
```

#### Explain `file()` method.

A way of reading data from a file is file() function, which accepts the name and path to a file and reads the entire file into an array,
with each element of the array representing one line of the file.
Here’s an example which reads a file into an array and then displays it using foreach loop.

Example:
```php
// read file into array
$arr = file('output.txt') or die('ERROR: cannot file file');
foreach ($arr as $line) {
    echo $line;
} 
```

#### How To change the file permissions?

Permissions in PHP are very similar to UNIX. Each file has following three types of permissions.
- Read
- Write and
- Execute.
PHP uses the `chmod()` function to change the permissions of a specific file. It returns TRUE on success and FALSE on failure.

Following is the Syntax:
```
chmod(file,mode)
```

#### What are different ways to get the extension of a file?

There are following two ways to retrieve the file extension.

```php
$filename = $_FILES['image']['name'];
$ext = pathinfo($filename, PATHINFO_EXTENSION);`
```

#### How to create a directory using PHP?

Example:

```php
 mkdir("mydocs");
```

In this program we use mkdir()function . Pass the directory name inside this function to create the directory.

#### How to get files(contents) from directory?

```php
$files =  scandir("mydocs");
print_r($files);
```
in the above example we get the contents of a directory. use scandir() function , directory name declare inside this.
scandir() function returns the files in array so stored the return value in a variable( $files).
Now print this using print_r($files) function i.e specially used to print the value and index of array.
it gives an output of an array type with index and their corresponding value.

#### How to open a directory?

```php
$od =  openddir("mydocs");
```

In the above example if we open the directory use opendir() function with directory name (“mydocs”).
store in variable $files because these open directory variable is going to used in further communication(for reading the contents).

#### What is include in php?

Files are included based on the file path given or, if none is given, the `include_path` specified. If the file isn't found in the include_path, include will finally check in the calling script's own directory and the current working directory before failing. The include construct will emit a warning if it cannot find a file; this is different behavior from require, which will emit a fatal error.

If a path is defined — whether absolute (starting with a drive letter or \ on Windows, or / on Unix/Linux systems) or relative to the current directory (starting with . or ..) — the include_path will be ignored altogether. For example, if a filename begins with ../, the parser will look in the parent directory to find the requested file.


#### What is require_once in php?

The require_once statement is identical to require except PHP will check if the file has already been included, and if so, not include (require) it again.

"require_once" and "require" are language constructs and not functions. Therefore they should be written without "()" brackets!

#### What is include_once in php?

The `include_once` statement includes and evaluates the specified file during the execution of the script. This is a behavior similar to the include statement, with the only difference being that if the code from a file has already been included, it will not be included again, and "include_once" returns TRUE. As the name suggests, the file will be included just once.

include_once may be used in cases where the same file might be included and evaluated more than once during a particular execution of a script, so in this case it may help avoid problems such as function redefinitions, variable value reassignments, etc.

#### What is require() in PHP?

require() statement takes all the text/code/markup that exists in the specified file and copies it into the file that uses the include statement.
require will produce a fatal error (`E_COMPILE_ERROR`) and stop the script.

#### What is difference between require and include?

The require() function is identical to include(), except that it handles errors differently. If an error occurs, the include() function generates a warning, but the script will continue execution. The require() generates a fatal error, and the script will stop.