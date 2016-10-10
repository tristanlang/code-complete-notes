### Chapter 7: High Quality Routines
* Routine = individual method or procedure invocable for a single purpose

#### 7.1 Valid Reasons to Create a Routine
* Reduce complexity
* Introduce an intermediate, understandable abstraction
* Avoid duplicate code
* Support subclassing
* Hide sequences of events present in the implementation
* Hide pointer operations (which can be complex or confusing)
* Improve portability
* Simplify complicated Boolean tests
* Improve performance (one centralized place to optimize)
* Small routines improve readability

#### 7.2 Design at the Routine Level
* cohesion is how closely the operations in a routine are related
* Acceptable types of cohesion
  * **Functional cohesion - when a routine does one and only one operation (best type of cohesion)**
  * Sequential cohesion - when a routine must perform operations in a certain order, share data from step to step, and do not make a complete function when performed together
  * Communicational cohesion - operations in a routine make use of the same data but are not related in any other way (to make into functional cohesion, separate the operations into their own routines)
  * Temporal cohesion - operations are combined into a routine because they occur at the same time (best to have the temporally cohesive routine call other routines, rather than performing operations itself)
* unacceptable types of cohesion, result in code that is poorly organized, hard to debug, hard to modify (better to just rewrite if you see this occurring):
  * Procedural cohesion - operations in a routine are done in a specified order (and operations do not need to be combined for any other reason)
  * Logical cohesion - several operations are stuffed into the same routine and one of the operations is selected by a control flag that’s passed in
  * Coincidental cohesion - operations in a routine have no discernible relationship to each other

#### 7.3 Good Routine Names
* Describe everything the routine does
  * Avoid long and silly names
  * Instead, do not make routines with side effects to allow yourself to have simple names
* Avoid meaningless, vague, or wishy-washy verbs (e.g., HandleData, DealWithOutput)
  * Sometimes this is due to good routines with bad names
  * Other times it is because the routines have no focus - must be refactored
* Make names of routines as long as necessary, but as clear as possible
* **To name a function, use a description of the return value (IsReady, CurrentColor)**
* **To name a procedure, use a strong verb followed by an object (PrintDocument, CalcRevenues)**
  * In object oriented languages, the object may be implied
* Use opposites precisely
* Establish conventions for common operations

#### 7.4 How Long Can a Routine Be?
* Theoretical ideal is one page or 1-2 pages of program listing: 50-100 lines
* In OOP many routines will be accessors and thus very short
* A complex algorithm may result in a routine that grows organically up to a maximum of 100-200 lines of code (noncomment, nonwhitespace)
* Let issues such as cohesion, depth of nesting, number of variables, number of decision points, number of comments, etc dictate the length of the routine
* Beyond 200 lines of code, error rates increase

#### 7.5 How to Use Routine Parameters
* Interfaces between routines are some of the most error prone areas of a program
* Put parameters in input-modify-output order
* Consider creating your own "in" and "out" keywords (via preprocessor)
* If several routines use similar parameters, put the similar parameters in a consistent order
* Use all the parameters
* Put status or error variables last
* Don't use routine parameters as working variables
* Document interface assumptions about parameters (use assertions to put them into code)
  * Ranges of expected values
  * Units of numeric parameters
  * Specific values that should never appear
  * Input only, modified, output only
* Limit the number of a routine's parameters to ~7
* Consider an input, modify, output naming convention for parameters
* Pass the variables or objects that the routine needs to maintain its interface abstraction
  * If parameters are passed and returned and only those are used, just pass the values you need
  * If the routine is often modified and it uses variables from the same object each time, pass the object
* Use named parameters (like passing parameters in Python `name='Tristan'`
* Make sure actual parameters match formal parameters
  * Actual parameters = the variables passed when a function is called
  * Formal parameters = the parameters defined when a routine is defined

#### 7.6 Special Considerations in the Use of Functions
* A function is a routine that returns a value
* A procedure is a routine that does not
* Use a function if the primary purpose of the routine is to return the value indicated by the function name, otherwise use a procedure

#### 7.7 Macro Routines and Inline Routines
* Preprocessor macros
* Fully parenthesize macro expressions because macros and their expressions are expanded into code
* Surround multiple-statement macros with curly braces
* Name macros that expand to code like routines so that they can be replaced by routines if necessary
* Inline routines are converted to inline code at compile time, which can make more efficient code by avoiding routine call overhead
* Best to profile the code and measure whether inline routines are necessary to improve performance
