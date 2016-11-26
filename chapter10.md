### Chapter 10: General Issues in Using Variables

#### 10.3 Guidelines for Initializing Variables
* Explicitly declare variables even when the language does not require you to in order to avoid errors with implicit declarations
* Initialize each variable as it is declared
* Initialize each variable close to where it is first used
* Principle of Proximity: keep related actions together
* Ideally, declare and define each variable close to where it is first used
* Use final or const when possible
* Pay special attention to counters and accumulators, be sure to reset them
* Initialize a class's member data in its constructor
* Check the need for reinitialization
* Initialize named constants once; initialize variables with executable code
* Use the compiler setting that automatically initializes all variables
* Take advantage of your compiler's warning messages regarding uninitialized variables
* Check input parameters for validity
* Use a memory-access checker to check for bad pointers
* Initialize working memory at the beginning of your program to a known value (0xCC or 0xDEADBEEF)

#### 10.4 Scope
* Scope is the extent to which variables are known and can be referenced throughout a program
* Localize references to variables, keep variables contained to a small section of code to improve readability
* Keep variables "live" for as short a time as possible (small delta between when variable is first used and last used)
* General guidelines for minimizing scope
  * Initialize variables used in a loop immediately before the loop
  * Don't assign a value to a variable until just before the value is used
  * Group related statements
  * Break groups of related statements into separate routines
  * Begin with most restricted visibility, and expand scope only if necessary

#### 10.5 Persistence
* Persistence is the life span of a piece of data (code block, lifetime of a program if a static variable, until deleted or garbage collected, forever in a db)
* Avoid bad persistence by:
  * Setting variables to unreasonable values when you are done with them
  * Use assertions and error checking to verify that critical variables are in reasonable ranges
  * Write code that assumes that data is not persistent
  * Develop the habit of declaring and initializing variables just before they are consumed

#### 10.5 Binding Time
* Binding time is the time at which the variable and its value are bound together
* The later you make binding time, the more flexibility you have
* Hard coding is the earliest binding time of code writing time
* Named constants bind at compile time
* Routine return values bind at run time
* Just in time means that binding time occurs when a program is run and each time a routine is called

#### 10.7 Relationship Between Data Types and Control Structures
* Sequential data translates to sequential statements in a program
* Selective data translates to if and case statements in a program
* Iterative data translates to for, repeat, and while looking structures in a program

#### 10.8 Using Each Variable for Exactly One Purpose
* Use each variable for one purpose only (avoid reusing temp variables especially)
* Avoid variables with hidden meanings
  * This includes hybrid coupling, such as allowing variables to take on unreasonable values (word count = -1) during normal operation
  * Better to use a custom data type or multiple variables for this
* Make sure that all declared variables are used
