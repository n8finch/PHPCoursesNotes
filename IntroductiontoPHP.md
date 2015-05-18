#Introduction to PHP#

##The Basics##

All pages must be in the root of the file you want to execute.
`<php ?>`

#####Naming Variables####
Something you don't know that you would want to change.

- Names
- Totals

Variables always begin with $ and cannot begin with a number.

- Choose meaningful names
- Use camelCase or underscores to separate names.

Always finish with a semicolon; 

Can be text or numbers for variables. 

`echo $variable;`

####Comments####

- `//` :single line comment
- `#` :single line comment
- Comments can be added to the end of the line.
- `/*...*/` is for a multiple line comment

PHP ignores white space

PHP can use "" or '' . Or, to not include quotes, use a \ right in front of the the quote, e.g. \' or \". BUT, if you want to include a variable in a string, e.g. $book, you can use double quotes, e.g. `echo "I like to read $book";` or you can do `echo "I like to read " $book;`. Here are some more Escape Characters:




To concatinate: use the `.`, e.g.: 
`$fullName = $firstName . ' ' . $lastName;
echo $fullName;`
Will echo `Nate Finch`
You can use the combine concatination operator `.=` to concatinate as well, e.g.:
`$name = "Nate";
$name .= "Finch";
echo $name;` will echo `Nate Finch`

####Math####
You can increment, decremt with ++ and --

Also, you can use += and -=. 

Finally, modulo division gives you the remainder, e.g. `5%2 = 1`

***NOTE*** you cannot echo an array!
You can print or return arrays. You can echo array elements, e.g. `echo array[2];` will echo the third element in the array.

Associative arrays store as ***key value pairs***:
`$descriptions = array ( 'Earth' => 'mostly harmless', 
'Marvin' => 'the paranoid android');
echo "Earth is described as $descriptions[Earth]";`

##Booleans##

True and False.
False: `fales, null, 0, an empty string ' ' or " "`
True: everything else.

These can be used in Boolean if/else statements:

***NOTE***, make sure o check you're NOT assigning a value with `=` in a comparison.

####Switch Statements####

`switch ($name) {
    case
         echo...
         break;
    case
         echo...
         break;
     default
     echo...
}`

####Ternary Operator####
`$result = ($value == 42) ? 'The answer to the ultimate question of life, everything.' : 'Keep calculating';`
If true, will result the first segment, if false, returns second segment.

####While and Do/While Loops####
`while ($i <=10) {echo "This"; $i++;}` or `do {echo "This";  $i++} while($i <=10);`
These basically do the same thing.

####For Loops####
`for ($i =0; $i < count($array); $i++) {echo '<li>' . $array[$i] . '</li>'}` 
this would echo out a list of an array until the array is finished.

####ForEach Loop####
`foreach ($array as $i) {echo '<li>' . $array[$i] . '</li>';}` 
or for associative arrays:
`foreach ($array as $key => description) {echo "<p>$key is $description</p>;}`

##Functions, Objects, and Errors##
Plenty of functions available:
`strtolower($name);` would make NATE to nate.
`ucfirst(strtolower($name));` would make NATE to Nate.
`strip_tags($input, '<p><a>');` would strip all tags but the p and a tags.
`rsort($var)` will rverse the value of the variable.
See more: http://php.net/manual/en/funcref.php
E.g. http://php.net/manual/en/book.strings.php and http://php.net/manual/en/function.strip-tags.php

####Custom functions####
They can be whatever you like but should follow this format:
`function convertSeconds($seconds){
    $minutes= floor($seconds / 60);
    $seconds = $seconds % 60;
    $seconds = ($seconds <10) ? '0' . $seconds : $seconds;
    return "$minutes:$seconds";
}
echo convertSeconds(547);`

####Including External Files####

- include
- include_once
- require
- require_once

`include './includes/paragraph.php';`

####Classes and Objects####
`$datetimehere = new DateTime();` will create a new instance in that class.


##Emailing the Contents of a Form (GET and POST)##

By default forms are submitted with the GET method. Add the "method" and action attribute. 

`<form name="contact" method="get" action="<?php echo $_SERVER('PHP_SELF'); ?>">` would be the opening form.

Array keys in a form are submitted in name value key pairs, i.e. `[name] => David`

GET method should only be used forms, and if you want to send email, the POST method should be used.

####Arguments Mail expects####

`<?php
$to= 'David Powers <david@david.com>, another@email.com';
$subject = 'Subject of the email';
$body = 'This is the body of the email message.";
$headers = 'From: webmaster@example.com\r\n";
$headers .= 'CC: something@mail.com';

$success = mail($to, $subject, $body, $headers, '-david@david.com');

Validation 

`isset` function checks for a variable. 

####Variable Variable####
Allows you to save a variable in another variable to change it as you need (upcase, lowercase, remove spaces, etc.)

`foreach ($_POST as $key => $value) {
$temp = is_array($value) ? $value : trim($value);
if(empty($temp) && in_array($key, $required)) {
    $missing[] = $key;
    $$key = '';
} else if (in_array($key, $expected)) {
    $$key = $temp;
}
}`
