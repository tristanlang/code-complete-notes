### Chapter 13: Unusual Data Types

#### 13.1 Structures
* Use structures to clarify data relationships
* Use structures to simplify operations on blocks of data
* Use structures to simplify parameter lists
* Reduce maintenance 

#### 13.2 Pointers
* Pointer usage is one of the most error prone areas of modern computing
* Every pointer consists of a location in memory and a knowledge of how to interpret the contents of that location (contents stored as bits)
  * Location in memory is a hexadecimal address
  * Knowledge of how to interpret comes from the base type of the pointer
  * There is no inherent interpretation of those bits, only a specific type of pointer can interpret appropriately
* Pointer errors tend to be the result of memory corruption: pointing to an area of memory they shouldn't
* Isolate pointer operations in routines or classes
  * Use access functions instead of using pointer operations liberally
* Declare and define pointers at the same time
* Delete pointers at the same scoping level as they were allocated
* Check pointers before using them (check that the memory locations are within an expected range)
* Check the variable referenced by the pointer before using it
* Use dog-tag fields to check for corrupted memory
  * A dog-tag field is a field in a structure that should remain unchanged
  * When you use the structure or delete the memory, if the field does not have the expected value, it has been corrupted
  * Usually at the beginning or end of a memory allocation
* Add explicit redundancies
  * Use certain fields twice, check that the data matches, otherwise memory is corrupt
  * An alternative to tag fields
* Use extra pointer variables for clarity (don't try to be pythonic..)
* Simplify complicated pointer expressions (such as with a well named variable)
* Draw a picture
* Delete pointer in linked lists in the right order (need access to the following elements before deleting the current one)
* Allocate a reserve parachute if memory, the amount needed to clean up and shut down cleanly
* Shred your garbage, set contents to garbage before deleting pointers
* Set pointers to bulk after deleting or freeing them
* Check for bad pointers before deleting a variable, make sure a pointer is not null before setting it to garbage
* Keep track of pointer allocations, such as in a list
* Write cover routines to centralize your strategy to avoiding pointer problems
  * SAFE_NEW
  * SAFE_DELETE
* Use a non-pointer technique
* C++ pointer pointers
  * Understand the difference between pointers (*) and references (&)
    * Reference must always refer to an object but pointer can be null
    * What a reference refers to can't be changed after the reference is initialized
  * Use pointers for "pass by reference" parameters and use const references for "pass by value" parameters
  * Use auto_ptrs (deletes memory automatically when auto_ptr goes out of scope)
* C pointer pointers
  * Use explicit pointer types rather than the default type (char and void pointers can be used for any type..)
  * Avoid type casting, squeezing a variable of one type into space for a variable of another type
  * Follow the asterisk rule for parameter passing
    * You can pass an argument back from a routine in C only if you have an asterisk in front of the argument in the assignment statement
  * Such as: `*parameter = value`
  * Use sizeof() to determine the size of a variable in a memory allocation

#### 13.3 Global Data

##### Problems with Global Data
* Inadvertent changes to global data
* Multiple threads writing to global variables concurrently
* Code reuse hindered by global data
* Uncertain initialization order of global variables in different files when files are loaded
* Modularity and intellectual manageability damaged by global variables

##### Reasons to Use Global Data
* Some values really do need to be global
* Emulation of named constants or enumerated types
* Streamlining use of extremely common data

##### Use Global Data Only as a Last Resort
* Make every variable local and move to global as necessary
* Differentiate between global and class variables
* Use access routines

##### How to Use Access Routines
* GlobalVar.Get/Set
* Require all code to go through the access routines for the data
* Don't just throw all your global data into the same barrel
* Use locking to control access to global variables
* Build a level of abstraction into your access routines, at the level of the problem domain instead of the level of implementation details
* Use the same level of abstraction consistently

##### How to Reduce the Risks of Using Global Data
* Create a well-annotated list of all your global variables
* Don't use global variables to contain intermediate results
* Don't pretend you're not using global data by putting all your data into a monster object and passing it everywhere
