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
Inserting comments `// or /*  */`


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
- Exponential:  pow(2,8); 
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
 $mixed[] = "horse";  Will append to the end of the array

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
- compare  < > <= >=
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



















