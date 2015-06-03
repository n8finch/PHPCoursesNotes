#Object-Oriented Programming with PHP#

##Intro to Object Oriented Programming##

What are objects?

- Primitive Data types
-- boolean
-- interger
-- floating point numbers
-- strings

- Objects
-- Complex
-- Multiple data types

Classes are blueprints for the structure of an object.

- Attributes and properties
- Behaviors (methods)
- Instances of a class are the action

OOP

- Organizes projects in well organized fashion and isn't procedural
- Abstraciton, Encaptularity, Modulation, Polymorphism



##Creating Your First Object##

-Classes deinitions always start with class, followed by a name
- Naming rules
-- Must start with letter or underscore
-- Remaining characters must be 
-- UpperCamel
-- Variables in lower case
-- Avoid the word "class"
-- Use {} to enclose properties and methods

e.g.: `class Address {}`



Class Properties

- Structure for storing values
- Unlimited properties per class
- Defined with visibility keyword
-- public, protected, private
-- Omit? Parse error

Declaring a Property

- lowerCamel
- like variables
- optionals

eg.: `class Address {
// Street address.
public $street_address_1;
public $street_address_2;
}`

Class Methods

- Function within a class
- Same naming conventions as functions
-- Same as PHP labels
- Best practice
-- lowerCamel

First Method= HTML Address
always should use htmlspecialchars();
Use the pseudo variable $this to access the object's properties.
`$this->name`
Eg.: Address with city property: "San Diego"
`$this->city` accesses `"San Diego"`


`
class Address {
// Street address.
public $street_address_1;
public $street_address_2;
`
`
// Name of the City.
public $city_name;
`
`
// Name of the subdivison.
public $subdivision_name;
`
`
// Postal code.
public $postal_code;
`
`
// Name of the Country.
public $country_name;
`
`
/**
* Display an address in HTML.
* @return string 
*/
function display() {
$output = '';
`
`
// Street address.
$output .= $this->street_address_1;
if ($this->street_address_2) {
$output .= '<br/>' . $this->street_address_2;
}
`
`
// City, Subdivision Postal.
$output .= '<br/>';
$output .= $this->city_name . ', ' . $this->subdivision_name;
$output .= ' ' . $this->postal_code;
`
`
// Country.
$output .= '<br/>';
$output .= $this->country_name;
`
`
return $output;
}
}
`
`


Creating an instance:
`$instance = new Class;`
`$address = new Address;`

Protecting content with `public, private, protected`
e.g. `public $country_name;`



##Creating Overloading with Magic Methods##

Magic methods are specialized methods built into PHP that execute in response to events. There are about a dozen available.

They start with two underscores and then a string, e.g. `__construct() or __toString()`. 

Trigger custom behavior, access unavailable property, missing methods. Custom object creation allows for defaults to be set which are normally unavailable at run time. Like 

Can slow down and expose variables that are otherwise hidden.

Treating objects like strings: Convenient to assume. Polymorphism: allows you to act on an object without knowing the class, common function names between classes. 



##Accessing Classes without Instantiation##

Why limit instantiation? DB connections, third-party services (slow performance), alternative to global (declaring a class), only one instance in an application.

Static keywords: Access property, method without instantiation. Static properties have values stored at class, not object level, keep track of number of instantiated objects.

`Static public $variable = ... `

`static public $valid_address_types = array(
1 => 'Residence',
2 => 'Business',
3 => 'Park',
);`

Scope Resolution Operator allows access to: static, constant, overridden properties & methods without instantiation.

`::`
`Class::method()`
`Class::$variable`

Constants: like a property that never changes. Should all be in all caps, with const at the beginning. e.g. `const JENNY = "867-5309";` Can't be arrays. 

Static Methods, similar to regular methods in naming convention, visibility scope, returns value. 
Cannot use `$this` to get properties. Instead, use `$self` keyword which refers to the current class. 

Database Class: allow only one connection, provide access throughout the application, minimize corruption, using MySQLi

/**
* MySQLi database; only one connection is allowed. 
*/
class Database {
private $_connection;
// Store the single instance.
private static $_instance;

/**
* Get an instance of the Database.
* @return Database 
*/
public static function getInstance() {
if (!self::$_instance) {
self::$_instance = new self();
}
return self::$_instance;
}

/**
* Constructor.
*/
public function __construct() {
$this->_connection = new mysqli('localhost', 'sandbox', 'sandbox', 'sandbox');
// Error handling.
if (mysqli_connect_error()) {
trigger_error('Failed to connect to MySQL: ' . mysqli_connect_error(), E_USER_ERROR);
}
}

/**
* Empty clone magic method to prevent duplication. 
*/
private function __clone() {}

/**
* Get the mysqli connection. 
*/
public function getConnection() {
return $this->_connection;
}
}



##Class Relationships and Interactions##

Autoload Functions: automatically called `__autoload()`
`function __autoload($class_name) {
include 'class.' . $class_name . '.inc';
}`

Restict access with abstract class.

Use `final` to make sure child classes don't reload declarations. 

Overriding

Referencing is an alias, variables do not contain the object, but only the internal object identifier.



##Built in PHP Objects##

Exception Handling: a problem without crashing. `try` can be used, but `throw` might be better, e.g. `throw new exception...`

If using `try`, follow with `catch (Exception $e)`, you can also define error codes like 404, 1000, etc., otherwise, they are only throwing errors that are intergers, 0, 1, 2, etc...




##Design Patterns##

- Singleton Pattern
- Factory Method Pattern
- Strategy Pattern


##Conclusion##

- Namespace on php.net
- Books:
-- Design Patterns: Elements of Reusable OO Software
-- Code Complete (2nd ed. , MS Press)




