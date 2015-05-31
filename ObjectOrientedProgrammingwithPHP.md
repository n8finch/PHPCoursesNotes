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



##Accessing Classes without Instantiation##



##Class Relationships and Interactions##



##Built in PHP Objects##



##Design Patterns##


