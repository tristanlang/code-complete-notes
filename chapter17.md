### Chapter 17: Unusual Control Structures

#### 17.1 Multiple Returns from a Routine
* Use a return when it enhances readability
* Use guard clauses (early returns or exits) to simplify complex error processing
* Minimize the number of returns in each routine

#### 17.2 Recursion
* Make sure the recursion stops
* Use safety counters to prevent infinite recursion
* Limit recursion to one routine
* Keep an eye on the stack
  * Safety counters can help prevent stack overflow
  * Watch for allocation of local variables in recursive functions, especially memory intensive objects
  * Use `new` to create objects on the heap rather than letting the compiler create `auto` objects on the stack
* Don't use recursion for factorial or Fibonacci numbers

#### 17.3 goto
* goto often leads to the violation of the principle that code should flow from top to bottom
* goto is useful in a routine that allocates resources, performs operations on those resources, and then deallocates the resources
  * Reduces likelihood of forgetting to deallocate when you detect an error
* Can avoid goto with several possible methods:
  * Rewrite with nested if statements (if nesting is not too deep)
  * Rewrite with a status variable
  * Rewrite with try-finally, if available and the functions called within the try all throw exceptions
  * Rewrite by adding new routines
* If you must use goto, document extensively
