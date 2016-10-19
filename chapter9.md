### Chapter 9: The Pseudocode Programming Process

##### 9.1 Summary of Steps in Building Classes and Routines
* Steps in creating a class
  * Create a general design for the class
    * Class's responsibilities
    * Secrets the class hides
    * Define the abstraction the class interface captures
    * Identify key public methods
    * Identify and design any nontrivial data members used by a class
  * Construct each routine within the class
    * May find new routines you need to create
  * Review and test the class as a whole
  * Iterate
* Steps in building a routine
  * Design the routine
  * Check the design
  * Code the routine
  * Check the code
  * Iterate, using Psuedocode Programming Process

##### 9.2 Pseudocode for Pros
* Pseudocode Programming Process defines a specific approach to using pseudocode to streamline the creation of code within routines
* Guidelines for using pseudocode effectively
  * Use English-like statements that precisely describe specific operations
  * Avoid syntactic elements from the target programming language
  * Describe the meaning of the approach rather than how the approach will be implemented in the target language
  * Refine the pseudocode in more and more detail until it seems as if it would be easier to simply write the code
* Once the pseudocode is written, you build the code around it and the pseudocode turns into comments

#### 9.3 Constructing Routines Using the PPP

##### Design the Routine
* Check the prerequisites
  * Well defined purpose
  * Fits cleanly into overall design
  * Is needed by the program's requirements
* Define the problem the routine will solve in enough detail to create the routine
  * Information the routine will hide
  * Inputs/outputs
  * Preconditions that are guaranteed to be true before routine is called
  * Postconditions that are guaranteed after routine finishes
* Name the routine (trouble naming a routine may mean that the routine's purpose is not well defined)
* Decide how to test the routine
* Research functionality available in the standard libraries
* Think about error handling
* Think about efficiency (minority of systems are performance critical)
  * In performance critical systems, design your routine so that it will meet its resource and speed goals
  * In other systems, if you have good encapsulation, you can replace a slow, high-level language implementation with a better algorithm or a low-level language implementation
  * Otherwise, usually a waste of effort to work on efficiency at the level of individual routines
  * Biggest optimizations come from refining high-level design
* Research the algorithms and data types (if functionality is not available in libraries)
* Write the pseudocode
  * Start with the general and work toward something more specific
  * Routine's header comment first
  * You must first know the routine's role in the program (if you do not then something is probably wrong)
  * Then fill in the high-level pseudocode for the routine
  * Express in precise English what the routine will do, step by step
* Think about the data
  * Definitions of key data types are useful to have when you design the logic of a routine
  * Worthwhile to think about the key data pieces before logic, if data manipulation is a prominent part of the routine
* Check the pseudocode
  * Back away from it and think about how you would explain it to someone else
  * Ask for a review of your pseudocode
  * Make sure you really understand it
* Try a few ideas in pseudocode, and keep the best (iterate)
  * Try as many designs as possible in pseudocode
  * Easy to get emotionally invested in code already written
 * **Iterate the routine in pseudocode until the statements become simple enough that you can fill in code below each statement and leave the original pseudocode as documentation**
  * **Keep working with pseudocode until you are sure of how to code something**

##### Code the Routine
* Write the routine declaration as an interface statement
* Turn the pseudocode into high level code comments and wrap with braces
  * At this point it should feel natural and easy to turn the pseudocode into code
  * If not, drill down further with pseudocode
* Fill in the code below each comment
  * Each comment generally expands to 2-10 lines of code
* Check whether code should be further factored, especially if one comment has a large amount of code beneath it
  * Call the function declaration as if it existed, finish initial routine, apply PPP to new routine
  * Apply PPP recursively by breaking out initial pseudocode into more detail and coding below each new comment

##### Check the Code
* Mentally check the routine for errors
  * Trace each path in the routine, either alone or with peers
  * Understand each line of code and why it is needed, otherwise experiment with alternative designs until you do
* Compile the routine
  * Wait until this far into constructing the routine to compile
  * By waiting, you avoid the hasty, error-prone changes associated with thinking that you'll have the routine complete just for the next compile
  * Compiling before you're sure your program works is often a symptom of hacked together code
  * Understand each warning you get from the compiler
* Step through each line of code in the debugger, making sure it does what you expect it to
* Test the code using test code and test cases
* Remove errors from the routine
  * If you find a bug, squash it immediately
  * If the routine is unusually buggy, rewrite it

##### Clean Up Leftovers
* Check that all input and output data is accounted for and that all parameters are used
* Routine should do one thing and do it well
* Check for inaccurate variable names, unused objects, undeclared variables
* Check the routine's statements and logic for infinite loops, off by one errors, improper nesting, resource leaks
* Check the routine's layout
* Check the routine's documentation, making sure the pseudocode comments are still accurate
* Remove redundant comments

##### Repeat Steps as Needed
* If the quality of the routine is poor, back up to the pseudocode

#### 9.4 Alternatives to the PPP
* Test driven development
* Refactoring (Fowler book)
* Design by contract
