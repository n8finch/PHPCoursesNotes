#PHP For Web Designers#


##Introduction##

Variables use camelCase. No number at the beginning.

Use ' ' unless it's necessary to use " " for strings.

Putting () around the variable is options, e.g. `echo $title;` and `echo ($title);` is the same thing.

To concatenate, use the "." operator, and can also wrap the variables in double quotes, e.g. `"$description $answer"` will put a space between the two variables. 

echo and print are basically the same.

Commenting in PHP: 

- `//` for single line comment
- `#` single line comment
- `/*  */` for multiple lines




##Using Server-Side Includes for Common Page Elements##

Server-side includes?: files you call in your php files.

- `include` : script continues
- `require` : script stops working
- `include_once`
- `require_once`

PHP looks for includes:

- Strict set of rules
- Use a path relative to the current document
- If the include file is in the same folder, begin with ./
- Paths relative to the site root will not work.

Moving common elements to includes files.

- header
- nav
- footer

If the header and nav are used together, they can go into the same place. 

Variables can be used to change the $siteroot for development to production.


##Using Conditions to Change Page Output##

PHP works very similarly to Javascript and booleans.

if, if/else, if/elseif/else, while, case, 

Conditional operators, ==, !=, etc.

PHP stops checking when it encounters a true condition.

Date function: http://www.php.net/manual/en/function.date.php

Use these variables:
`$day = date('l');
$time = date('H:i');
$hour = date('H');`
[code]
</php if ($hour > 5 && $hour < 12) { >
<p>Good Morning</p>
</php } else if .... 
[/code]


Always use the isset() variable to check if a variable is set. If it's not, it will return false.


##Working with Multiple Values in Arrays and Loops##

Arrays can be made in two ways:

- $flowers = array('tulips', 'roses', etc...);
- (5.4 or later) $flowers = ['tulips', 'roses', etc...]; (this is like javascript)
- $flowers[] = 'irises';  adds to the end of the array

To display the value of an array: `echo $flowers[3];`

Wrapping arrays in a {$flowers['spring']}  keeps it from throwing errors.

foreach loops, good to use the temporary variable as the singular of the variable, e.g. `foreach ($features AS $feature)` or `foreach ($features AS $key => $value)`.

The `in_array($whatyouarelookingfor, $thearraytosearch)` funciton. Can be used in an an if/else statement to see if something is in stock, for example. `in_array($needle, $haystack)`

















