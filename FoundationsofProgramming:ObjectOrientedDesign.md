#Foundations of Programming: Object Oriented Design#

Each Object has data and logic. This can allow them to be more modular and non-linear. 

##What is an object?##
These all have:

- identity
- attributes
- behavior

Object

##What is a class
Class describes what an object will be, but is not an object. It is a blueprint.
You must have a class first. Some classes already come with the framework. 

Methods are blocks of code that belong to classes.

- name
- attributes
- behavior

Each object is an instance of a class

###APIE###

- Abstraction: the idea of the thing.  Focus on essentials
- Polymorphism: think about the “+” sign. Addition, concatenation. 
- Inheritance: creating a new class that relies on other classes. Superclass->Subclass, Parent->Child. Single and multiple inheritance are both possible.
- Encapsulation: an object should not be accessible to the rest of the program. Reducing dependencies in another part of the application. 


##Steps##

1. Gather Requirements
2. Describe the app
3. Identify the main objects
4. Describe the interaction
5. Create a Class Diagram

##FURPS/FURPS+##

- **Functional** requirements
- **Usability** requirements
- **Reliability** requirements
- **Performance** requirements
- **Supportability** requirements

+ **Design, Implementation, Interface, Physical** requirements


##UML: Unified Modeling Language##

The diagraming language. Use paper/whiteboard to do these. 

Switch from Feature to User focus. Write this out.

###Use Cases###

- Title: e.g. "register new member"
- Actor:  e.g. User, customer, member...
- Scenario: write out what it is. numbered list. 
-- Can add extentions, preconditions, stakeholders, etc. 

Don't let the details kill your progress!

Some distinctions in identifying actors:

- External Systems/Organizations
- Roles/Security
- Job Title/Departments

Some distinctions with scenarios

- Log in
- Add to cart
- Purchase
- Sign up

Use simple, active and non-technical language. Use stick figures, lines, circles and boxes. This might not be sequential.


###User Stories###
Simpler and shorter than a Use Case. One or two sentences. 

Format:

- As a... (type of user, e.g. writer)
- I want... (goal, prompted to save)
- So that... (reason, so I don't lose work)


##Domain Modeling (Modeling the App##

1. **Identifying Objects**. Go through Use Cases and User Stories, take out the nouns and those are probably your objects. Takeout anything that is superfluous.
2. **Create a diagram** of the objects. Draw boxes, lines, etc. 
3. **Identify responsibilities** and behaviors. Go through UCs and USs and pick out the verbs. Always remember responsibilities should remain in Classes. E.g.: the "Order" Class responsibilities might include: Process order, Confirm order, Get order, Get status, Create order confirmation email. 


##CRC (Class, Responsibilitiy, Collaborators) Cards##
Cards include:

- Title: Class
- Two-thirds left: Responsibility
- One-third right: Collaboroators

##Creating Classes##

Name: Capitalized and Singular (not plural)
Datatypes: camelCase
Operations: camelCase()

##Instantiation##

**Constructors**: any variables belonging to an object are set at an initial state (values, e.g. new object of Spaceship "excelsior" is created with "shields" at 100% and "ammo" at "full".

**Destructors**: something to be called when an object is destroyed.

**Static variables**: One copy across all classes. Creating static methods are possible too, but can only access static variables. 

##Inheritance and Composition##

Inheritance has an "is a/an" relationship. "A poodle is a dog." 

You're always inheriting from a very basic Object Class.

Calling a method in the Super/Parent Class is possible with "super", probably. 

Abstract and Concrete classes available.

##Design Patters##

- Creational 
- Structural
- Behavioral

See Lynda Course on PHP Design Patterns

##DRY Development##
DRY and YAGNI (Ya Ain't Gonna Need It)
Code Smell: something just doesn't smell right, e.g. long methods, short variable or identifiers, pointless comments, the "god" object, feature envy.
There should only be one place that 

##Object Oriented Principles##

###SOLID###
- **Single**: An object should have one reason to exist, one reason to change - on primary responsibility
-**Open/Close**: open for extension, closed to modification.
- **Liskov Substitution Principle**: Derived classes must be substitutable for their base classes.
- **Interface Segregation Principle**: Multiple specific interfaces are better than one general purpose interface.
- **Dependency Inversion Principle**: Depend on abstractions, not on concretions. 

###GRASP###

General Responsibility Assignment Software Patterns

- **Expert/Information Expert**: Assign the responsibility to the class that has the information needed to fulfill it
- **Creator**: Who is responsible for creating an object?
- **Low Coupling/High Cohesion**: Reduce the number of dependencies between objects. Low coupling, high cohesion.
- **Pure Fabrication**: invent new classes that need the functionality. Reduces coupling.
- **Protected variations**: Protect the system from changes and variations.

