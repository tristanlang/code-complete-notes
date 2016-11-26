### Chapter 24: Refactoring **Read Martin Fowler's _Refactoring_**
* The Cardinal Rule of Software Evolution = evolution should improve the internal quality of the program
* Refactoring improves the internal quality of the program with no effect on the program function

#### 24.2 Introduction to Refactoring
* Refactor for the following reasons:
  * Code that is duplicated
  * Routine too long
  * Loop too long or too deeply nested
  * Class has poor cohesion
  * Class interface does not provide a consistent level of abstraction
  * Changes within a class tend to be compartmentalized (could be 2+ different classes)
  * Changes require parallel modifications to multiple classes (could have inheritance structure or combine into a single class)
  * Inheritance hierarchies that have to be modified in parallel (combine into single class?)
  * case statements have to be modified in parallel (use inheritance or embedding or put into single case statement)
  * Related data items that are used together but are not organized into classes
  * A routine uses more features of another class than of its own class
  * A primitive data type is overloaded (using ints or floats for Money)
  * A class doesn't do much
  * A chain of routines passes tramp data
  * A middleman object isn't doing anything
  * One class is overly intimate with another
  * A routine has a poor name
  * Data members are public
  * A subclass uses only a small percentage of its parents' routines
  * Comments are used to explain difficult code
  * Global variables are used
  * A program contains code that seems like it might be needed some day (but is not used today)

#### 24.3 Specific Refactorings
* Data-Level Refactorings
  * Replace a magic number with a named constant
  * Rename a variable with a clearer or more informative name
  * Replace an expression with a routine
  * Introduce an intermediate variable
  * Use a local variable for local purposes rather than as a parameter
  * Convert a data primitive to a class
  * Change an array to an object
  * Encapsulate a collection
* Statement-Level Refactorings
  * Decompose a boolean expression
  * Move a complex boolean expression into a well-named boolean function
  * Consolidate fragments that are duplicated within different parts of a conditional
  * Use break or return instead of updating a loop control variable
  * Return as soon as you know the answer instead of assigning a return value within nested if statements
  * Replace conditionals (especially repeated _case_ statements) with polymorphism
  * Create and use null objects instead of testing for null values
* Routine-Level Refactorings
  * Extract a routine
  * Convert a long routine into a class
  * Substitute a simple algorithm for a complex algorithm
  * Add/remove a parameter
  * Separate query operations from modification operations
  * Combine similar routines by parameterizing them
  * Separate routines whose behavior depends on parameters passed in
  * Pass a whole object rather than specific fields (or vice versa)
* Class Implementation Refactorings
  * Change value objects to reference objects (or vice versa)
  * Change member routine or data placement
  * Extract specialized code into a subclass
  * Combine similar code into a superclass
* Class Interface Refactorings
  * Convert one class into two
  * Replace inheritance with delegation (and vice versa)
  * Introduce an extension class
  * Encapsulate an exposed member variable
  * Remove `Set()` routines for fields that cannot be changed
  * Hide routines that are not intended to be used outside the class
  * Encapsulate unused routines
* System-Level Refactorings
  * Provide a factory routine rather than simple constructor

#### 24.4 Refactoring Safely
* Save the code you start with (new branches)
* **Keep refactorings small**
* **Do one refactoring at a time**
* **Make a list of steps you intend to take**
* Make a parking lot for ideas you'd like to try out at some point
* Make frequent checkpoints
* Retest
* **Add test cases**
* **Review the changes**
