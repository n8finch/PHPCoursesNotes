
##PHP Overview##
####What is PHP?####
PHP is a server side scripting language.

- Runs on an event. It's not a program. Programs continue to run even without instructions.
- Server side, runs entirely on the webserver. Cannot be run on it's own and needs a browser.
- Designed for use with HTML, provides more dynamic pages
- Syntax is similar to C, Java, Perl

####History####

- Binary in C
- PHP Hypertext Preprocessor
- Released in Zend Engine
- PHP 5 has better performance and OOP

####Why Choose PHP?####

- Opensource and free software
- Cross platform.
- Powerful, robust scalable
- Can be object-oriented
- php.net/docs.php
- Large and active developer community


##Installation##

On a Mac: Using Command line
` httpd -v` gives the version of Apache
Start, Stop and Restart Apache:
`sudo apachectl start
sudo apachectl stop
sudo apachectl restart`

Use the command line to reset mysql default root password. Navigate to mysql/bin. In command line:
`mysqladmin -u root password` will allow you to reset your password.


##First Steps##
Setup first page, index.php
Echo dynamic text
The operational trail
Inserting comments `// or /* */`


##Exploring Data Types##

####Variables####

- start with $
- can be followed by underscore/s
- can be up or lower case
- numbers can be in it
- first letter has to be letter or underscore, not number
- preferred 

- visit the reserved list at: php.net/manual/en/reserved.php

####Strings####

- defined in quotes
- can be a blank quote " "
- variable replacement
-- echo `$phrase Again` or `{$phrase} Again` will echo the variable in the string
-- `$third .= $second`

Some functions:

- `strtolower($var);` lowercase evertyhing
- `strtouppper($var);` all caps
- `ucfirst($var);` Just first word
- `ucwords($var);` upp
- `strlen($var);` tells length or string
- `trim(" B C D ") . "E";` removes spaces
- `strstr($var, "red"); Find, string within a string and returns everything after
- `str_replace("quick", "super-fast", $third);` Replaces first param with second param inside third param
- `str_repeat(($var, 2);` Repeats a string, first param is which string, second param is how many times to repeat
- `substring(($var, 5, 10);` Make a subsctring of first param starting at second param ending at third param
- `strpos($var, "red");` Finds the position of brown
- `strchr($var, "z");`Finds the position of a character, returns that and everything after it.

####Numbers: Integers and Floating Points####

- Absolute value: `abs(0 - 300);`
- Exponential: pow(2,8); 
- Square root: sqrt(100); 
- Modulo: fmod(20,7); 
- Random: rand(); 
- Random (min,max): rand(1,10)
- += : $var2 += 4; echo $var2; 
- -= : $var2 -= 4; echo $var2; 
- *= : $var2 *= 3; echo $var2; 
- /= : $var2 /= 4; echo $var2;
- Increment: $var2++; echo $var2; 
- Decrement: $var2--; echo $var2; 

- Round: echo round($float, 1);
- Ceiling: echo ceil($float);
- Floor: echo floor($float);

- "Is {$integer} integer? " . is_int($integer); 
echo "Is {$float} integer? " . is_int($float); 

echo "Is {$integer} float? " . is_float($integer); 
echo "Is {$float} float? " . is_float($float);

echo "Is {$integer} numeric? " . is_numeric($integer); 
echo "Is {$float} numeric? " . is_numeric($float);

####Arrays and Associative Arrays####

$numbers = array(4,8,15,16,23,42);
echo $numbers[0];

$mixed = array(6, "fox", "dog", array("x", "y", "z"));
echo $mixed[2]; 
echo $mixed[3]; 
echo $mixed 

$mixed[3][1]; 

$mixed[2] = "cat"; 
$mixed[4] = "mouse"; 
$mixed[] = "horse"; Will append to the end of the array

Associated arrays always have key-value pairs:

- array("first_name" => "Kevin", "last_name" => "Skoglund"); 
- $assoc["first_name"]; 
- $assoc["first_name"] . " " . $assoc["last_name"];

- $assoc["first_name"] = "Larry"; 
- $assoc["first_name"] . " " . $assoc["last_name"]; 

- $assoc[0]; 

- $numbers = array(4,8,15,16,23,42);
- $numbers = array(0 => 4, 1 => 8, 2 => 15, 3 => 16, 4 => 23, 5 => 42); 
- $numbers[0]; 

Array functions:

Count: echo count($numbers); 
Max value: echo max($numbers); 
Min value: echo min($numbers); 
<br />
<pre>
Sort: sort($numbers); print_r($numbers); 
Reverse sort: rsort($numbers); print_r($numbers); 
</pre>
<br />
Implode: echo $num_string = implode(" * ", $numbers); 
Explode:print_r(explode(" * ", $num_string)); 
<br />

15 in array?: echo in_array(15, $numbers); // returns T/F 
19 in array?: echo in_array(19, $numbers); // returns T/F 

####Booleans####

$result1 = true;
$result2 = false;

Result1: echo $result1; 
Result2: echo $result2; 

result2 is boolean? echo is_bool($result2); 

$number = 3.14;
if( is_float($number) ) {
echo "It is a float.";
}

####NULL and empty####

$var1 = null;
$var2 = "";

var1 null? echo is_null($var1); 
var2 null? echo is_null($var2); 
var3 null? echo is_null($var3); 

var1 is set? echo isset($var1); 
var2 is set? echo isset($var2); 
var3 is set? echo isset($var3); 


empty: "", null, 0, 0.0, "0", false, array() ?>

$var3 = "0"; 
var1 empty? echo empty($var1); 
var2 empty? echo empty($var2); 
var3 empty? echo empty($var3); 

***"Empty is one of the leading causes of bugs in PHP***

####Type juggling and casting####

What you can type cast:

- string
- int, integer
- float
- array
- bool, boolean

Type Juggling<br />
$count = "2 cats"; 
Type: echo gettype($count); 

$count += 3;
Type: echo gettype($count); 

$cats = "I have " . $count . " cats.";
Cats: echo gettype($cats); 


Type Casting
settype($count, "integer");
count: echo gettype($count); 

$count2 = (string) $count;
count: echo gettype($count); 
count2: echo gettype($count2); 


$test1 = 3;
$test2 = 3;
settype($test1, "string"); 
(string) $test2; ?> ***Note***: using (string) does not last.
test1: echo gettype($test1); 
test2: echo gettype($test2);


####Constants####

define("MAX_WIDTH", 980);
echo MAX_WIDTH;
// can't change the value
//MAX_WIDTH = MAX_WIDTH + 1
//echo MAX_WIDTH;


// can't even redefine it
define("MAX_WIDTH", 981);
echo MAX_WIDTH;


##Control Structures: Logical Expressions##

####If Statements####

`$a = 3;
$b = 4;

if ($a > $b) {
echo "a is larger than b";
} elseif ($a < $b) {
echo "a is smaller than b";
} else {
echo "a is equal to b";
}`

`$new_user = true;
if ($new_user) {
echo "<h1>Welcome!</h1>";
echo "<p>We are glad you decided to join us.</p>";
}`

`$numerator = 20;
$denominator = 0;
$result = 0;
if ($denominator > 0) {
$result = $numerator / $denominator;
}
echo "Result: {$result}";`

####Comaparison and Logical Operators####

- equal: ==
- identical: === (equal AND same type)
- compare < > <= >=
- not equal !==
- not identical: !===
- and: &&
- or: ||
- not: !

`$a = 4;
$b = 3;
$c = 1;
$d = 20;
if (($a >= $b) || ($c >= $d)) {
echo "a is larger than b OR ";
echo "c is larger than d";
}`

`$e = 100;
if (!isset($e)) {
$e = 200;
}
echo $e;`

`// don't reject 0 or 0.0
$quantity = "";
if (empty($quantity) && !is_numeric($quantity)) {
echo "You must enter a quantity.";
}`

####Switch Statements####

The return the statement that matches and every case after that, unless there is a break.

`$a = 2;

switch ($a) {
case 0:
echo "a equals 0<br />";
break;
case 1:
echo "a equals 1<br />";
break;
case 2:
echo "a equals 2<br />";
break;
case 3:
echo "a equals 3<br />";
break;
default:
echo "a is not 0, 1, 2, or 3<br />";
break;
}`

`$year = 2013;
switch (($year - 4) % 12) {
case 0: $zodiac = 'Rat'; break;
case 1: $zodiac = 'Ox'; break;
case 2: $zodiac = 'Tiger'; break;
case 3: $zodiac = 'Rabbit'; break;
case 4: $zodiac = 'Dragon'; break;
case 5: $zodiac = 'Snake'; break;
case 6: $zodiac = 'Horse'; break;
case 7: $zodiac = 'Goat'; break;
case 8: $zodiac = 'Monkey'; break;
case 9: $zodiac = 'Rooster'; break;
case 10: $zodiac = 'Dog'; break;
case 11: $zodiac = 'Pig'; break;
}
echo "{$year} is the year of the {$zodiac}.";`

$user_type = 'customer';

switch ($user_type) {
case 'student':
echo "Welcome!";
break;
case 'press':
case 'customer':
case 'admin':
echo "Hello!";
break;
}



##Control Structures: Loops##

####While Loops####

`while (test){
statement
}`

`$count = 0;
while ($count <= 10) {
echo $count . ", ";
$count++;
}`

####For Loops####

`for (initial; test; each){
statement
}`

`for($count = 0; $count <= 10; $count++) {
echo $count . ", ";
}`

####Foreach Loops####

Taylor made for arrays!

`for ($array as $value){
statement
}`
$value is assigned to the item in the array. It does not have a value outside the loop.
The condition for exiting is that the array ends. 

`$ages = array(4,8,15,16,23,42);
foreach($ages as $age) {
echo "Age: {$age}<br />";
}`

for associative arrays:
`for ($array as $key => $value){
statement
}`

`$person = array(
"first_name" => "Kevin", 
"last_name" => "Skoglund",
"address" => "123 Main Street",
"city" => "Beverly Hills",
"state" => "CA",
"zip_code" => "90210"
);`

`foreach($person as $attribute => $data) {
$attr_nice = ucwords(str_replace("_", " ", $attribute));
echo "{$attr_nice}: {$data}<br />";
}`


####Continue####

`for ($count=0; $count <= 10; $count++) {
if ($count % 2 == 0) { continue; }
echo $count . ", ";
}`

Once you get to the `continue`, then it starts the loop over again.

`for ($i=0; $i<=5; $i++) {
if ($i % 2 == 0) { continue(1); }
for ($k=0; $k<=5; $k++) {
if ($k == 3) { continue(2); }
echo $i . "-" . $k . "<br />";
}
}`

The "2" in the loop above, it tells it to go back "2" arrays.

####Break####

Break stops the whole process and moves on.

`for ($count=0; $count <= 10; $count++) {
if ($count == 5) {
break;
}
echo $count . ", ";
}`

####Array Pointers####

Current item. By default it is always the first item in the array.
`
$ages = array(4,8,15,16,23,42);
// current: current pointer value
echo "1: " . current($ages) . "<br />";
// next: move the pointer forward
// similar to using 'continue' inside a loop
next($ages);
echo "2: " . current($ages) . "<br />";
next($ages);
next($ages);
echo "3: " . current($ages) . "<br />";
// prev: move the pointer backward
prev($ages);
echo "4: " . current($ages) . "<br />";
// reset: move the pointer to the first element
reset($ages);
echo "5: " . current($ages) . "<br />";
// end: move the pointer to the last element
end($ages);
echo "6: " . current($ages) . "<br />";
// move the pointer past the last element
next($ages);
echo "7: " . current($ages) . "<br />";
`


`reset($ages);
// while loop that moves the array pointer
// similar to foreach
while($age = current($ages)) {
echo $age . ", ";
next($ages);
}`




##User-Defined Function##

####Defining Functions####

Define:
`function name($arg1, $arg2) {
statement
}`


####Function Arguments####

`function str_replace($find, $replace, $target) {...}`

for example:
`function better_hello($greeting, $target, $punct) {
echo $greeting . " " . $target . $punct . "<br />";
}
better_hello("Hello", $name, "!");
better_hello("Greetings", $name, "!!!");
better_hello("Greetings", $name, null);`



####Function Return Values####

Always want to return something from your functions! Maybe better to leave echos outside of functions? 
`
function add($val1, $val2) {
$sum = $val1 + $val2;
return $sum;
}
$result1 = add(3,4);
$result2 = add(5,$result1);
echo $result2;
`

####Multiple Return Values####

Functions should only return one value, but they can return more with an array...

`
function add_subt($val1, $val2) {
$add = $val1 + $val2;
$subt = $val1 - $val2;
return array($add, $subt);
}
$result_array = add_subt(10,5);
echo "Add: " . $result_array[0] . "<br />";
echo "Subt: " . $result_array[1] . "<br />";
list($add_result, $subt_result) = add_subt(20,7);
echo "Add: " . $add_result . "<br />";
echo "Subt: " . $subt_result . "<br />";
`
use `list()` function to assing array values to be returned. 

####Scope and Global Variables####

You probably won't use more than a few global variables in projects.
`
$bar = "outside"; // global scope
function foo() {
global $bar;
if (isset($bar)) {
echo "foo: " . $bar . "<br />";
}
$bar = "inside"; // local scope
}
echo "1: " . $bar . "<br />";
foo();
echo "2: " . $bar . "<br />";
`

####Setting Default Args####
`
function paint($room="office",$color="red") {
return "The color of the {$room} is {$color}.<br />";
}
echo paint();
echo paint("bedroom", "blue");
echo paint("bedroom", null);
echo paint("bedroom");
echo paint("blue");
`

##Debugging##

####Common Problems####

- No output at all
-- Try an HTML page
-- Then try a php page
-- try turning on errors
-- typos
-- missing semicolons, braces, quotes, etc.
-- case-sensitive variable names
-- confusing "=" with "=="


####Warnings and Errors####

- Turn on error reporting
-- php.ini file to turn on error reporting

-- http://php.net/manual/en/errorfunc.constants.php

Four main categories of errors:

1. Fatal error: understood but couldn't execute
2. Syntax error: unexpected something and couldn't process code
3. Warnings: PHP found a problem, but was able to recover, e.g. dividing by zero
4. Notices: PHP offering advice (something smells bad).

####Debugging and Troubleshooting####

Outputting the value to determine what's going on

- echo $variable;
- print_r($array);
- gettype($variable);
- var_dump($variable);
- get_defined _vars();
- debug_backtrace(); (also called a stacktrace)

`
$number = 99;
$string = "Bug?";
$array = array(1 => "Homepage", 2 => "About Us", 3 => "Services");
var_dump($number);
var_dump($string);
var_dump($array);
function say_hello_to($word) {
echo "Hello {$word}!<br />";
var_dump(debug_backtrace());
}
say_hello_to('Everyone');
`





##Building Web Pages with PHP##

####Links and URLs####

Basic ways to get information:

- URLs/Links => GET (contain query parameter, anthing after the ?, multiple use the &
- Forms => POST
- Cookies => COOKIE

Super Global Parameter: 
- $_GET : still a variable, 

####Encoding GET Values####

Reserved characters need to be encoded, e.g. !#$%&'()*/;:=?@[]
Convert to hexadecimal form:

- `urlencode()`: reserved characters become % + 2-digit hexidecimal, spaces become "+"
Raw URL Encoding: 
- `rawurlencode()` : reserved characters become % + 2-digit hexidecimal, spaces become "%20"

When to use raw or urlencode? 

- rawurlencode: on the path
-- Path is the part before the "?"
-- Spaces must be encoded as %20
- urlencode the query string
-- Query string is the part after the "?"
-- Spaces are better encoded as "+"

- rawurlcode is more compatible generally

####Encoding for HTML####

Eg, HTML tags:

Reserved characters in HTML: <>&"

- use `htmlspecialchars()` to transform them.
- use `htmlentities()` to transform special things like TM, (R), etc.

// What to use when
`
$url_page = "php/created/page/url.php";
$param1 = "This is a string with < >";
$param2 = "&#?*$[]+ are bad characters";
$linktext = "<Click> & learn more";
`
`
$url = "http://localhost/";
$url .= rawurlencode($url_page);
$url .= "?" . "param1=" . urlencode($param1);
$url .= "&" . "param2=" . urlencode($param2);
`

####Including and Requiring Files####

Using `include()`

- Funtions
- Layout sections (header, footer, ect.)
- Resuable HTML/PHP code
- CSS or Javascript

- `include()`
- `require()` : will cause an error
- `include_once()` : helps to not redefine variables
- `require_once()` : 

####Modifying Headers####

- Headers are sent before page
- Changes must be made before any HTML output
-- before a single spaces or line return
-- before whitespace in included files
-- can come after whitespace inside php tags

####Page Redirection####

- 302 Redirect
-- HTTP 1.1/302 Found
-- location: path
- `header("Location: login.php");`

Here's a good function to use for redirection:
`
function redirect_to($new_location) {
header("Location: " . $new_location);
exit;
`
can be used with:
`
$logged_in = $_GET['logged_in'];
if ($logged_in == "1") {
redirect_to("basic.html");
} else {
redirect_to("http://www.lynda.com");
}
`

####Output Buffering####

- `ob_start()`
- `ob_end_flush()` : you have to end this so it will flush out everything.

Or set up in the php.ini file. If you're doing this sitewide, make sure to use `include()` so that you don't forget it on any page.


##Working with Forms and Form Data##
All forms are going to use the $_POST function

$_POST data doesn't need to be encoded.

####Single-Page Form Processing####

- All logic is in one file
- Redisplay the form on errors
-- Return error messages
-- Populate fields


####Common Validations####

- Presence
- String length
- Type
- Inclusion in a set
- Uniqueness
- Format

####Using Custom Validation Functions####

create a php file with validations functions and include that in the necessary pages.

`
// * presence
function has_presence($value) {
return isset($value) && $value !== "";
}
// * string length
// max length
function has_max_length($value, $max) {
return strlen($value) <= $max;
}
// * inclusion in a set
function has_inclusion_in($value, $set) {
return in_array($value, $set);
}
`


##Working with Cookies and Sessions##

$_COOKIE
Cookies are set in the header, and they can only be active when the headers are being sent or received. 

`setcookie($name, $value, $expire);`
`
$name = "test";
$value = "hello";
$expire = time() + (60*60*24*7); // add seconds
setcookie($name, $value, $expire);
`

####Unset Cookies####

The wrong way:

`- unset($_COOKIE["user_id"]);`

The right ways:

- `setcookie($name);`
- `setcookie($name, null);`
- `setcookie($name, $value, time() - 3600 );`


####Working With Sessions####

Pros and Cons with Sessions. 

use: `session_start();` , this should go in the header, since it deals with cookies.
`
$_SESSION["first_name"] = "Kevin";
$name = $_SESSION["first_name"];
echo $name;
`



##MySQL Basics##

- Databases have one database per application
- Table: set of column and rows, relationships between 
- Columns: type types
- Rows: single record of data 
- Field: intersection of row and column
- Index: increase lookup speed.
- Foreign keys: creating relationship table
- CRUD: Create, Read, Update, Delete. 


Setting up a MySQL DB with Command Line:

`
-DROP DATABASE db_name;
-CREATE DATABASE name_of_database;
-SHOW DATABASES;-
-USE name_of_database;
-GRANT ALL PRIVILEGES ON db_name
--TO 'widget_cms'@'localhost'
--IDENTIFIED BY 'password';
`
####Creating Tables####

`
CREATE TABLE table_name (
-- id INT(11) NOT NULL AUTO_INCREMENT,
-- menu_name VARCHAR(30) NOT NULL,
-- position INT(3) NOT NULL
-- visible TINYINT(1) NOT NULL,
-- PRIMARY KEY (id)
-- );
`

SHOW COLUMNS FROM table_name;
Always add a column for:
-id

####CRUD####

SELECT: Read
SQL INSERT: Create
SQL UPDATE: update
SQL DELETE: Delete

SQL Commands:

- SHOW TABLES db_name;
- SHOW COLUMNS FROM table_name; 
- INSERT INTO table_name (column_name, column_name, column_name) (<-- these should be parameters)
-- VALUES ('Insert a string here', 1, 1); (should add the values you want assigned to each of the parameters)




##Using PHP to Access MySQL##

####Database####

- mysql: procedural 
- mysqli: (both procedural and object oriented)
- PDO - (object oriented)

MySQLi and PDO both support prepared statements
More info on choosing APIs: http://php.net/manual/en/mysqlinfo.api.chooseing.php


####PHP Database Interaction:####

1. Create db connection
2. Perform db query
3. Use returned data
4. Release returned data
5. Close db connection

`
// 1. Create a database connection
$dbhost = "localhost";
$dbuser = "widget_cms";
$dbpass = "secretpassword";
$dbname = "widget_corp";
$connection = mysqli_connect($dbhost, $dbuser, $dbpass, $dbname);
// Test if connection succeeded
if(mysqli_connect_errno()) {
die("Database connection failed: " . 
mysqli_connect_error() . 
" (" . mysqli_connect_errno() . ")"
);
}
`

`
// 2. Perform database query
$query = "SELECT * ";
$query .= "FROM subjects ";
$query .= "WHERE visible = 1 ";
$query .= "ORDER BY position ASC";
$result = mysqli_query($connection, $query);
// Test if there was a query error
if (!$result) {
die("Database query failed.");
}
`

`
// 3. Use returned data (if any)
while($subject = mysqli_fetch_assoc($result)) {
// output data from each row
<li><?php echo $subject["menu_name"] . " (" . $subject["id"] . ")"; ?></li>
}
`
`
// 4. Release returned data
mysqli_free_result($result);
`
`
// 5. Close database connection
mysqli_close($connection);
`

####SQL Injection####

Put the \ in there. E.g., "Today\'s Widget Trivia";
Don't use addslashes($string)
Use mysqli_real_escape_string($connection, $menu_name)


####Introducing Prepared Statements####

- Prepare statement once, reuse many times.
-- Faster
- Separate query from dynamic data
-- Prevents SQL injection




##Building a Content Management System##

####Blueprint the CMS####


####Datamodling####
What types of data will there be?






##Using Site Navigation to Choose Content##

####Adding Pages to the Navigation####

Refactoring: changing the code structure or appearance without changing the functionality.
For example:

- Moving functions to the functions.php file
- Taking out SQL functions from main php pages.




##Application CRUD##

Always remember to guard against SQL injection with `mysql_real_escape_string($param, $param);` or something similar. For example, securing `$subject_id` to $safe_subject_id`. 

In manage_content.php, it's best to make sure that you're just managing content and keep functions in funtions.php as you can.

Sessions are most useful for:

-User authentication
--$logged_in, $user_id

-Holding data during a redirect
--$message, $errors

-Frequently referred to data
--$username, $account_type




##Building in Public Area##






##Regulating Page Access##

