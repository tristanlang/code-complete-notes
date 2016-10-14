### Chapter 8: Defensive Programming
* Main idea is that if a routine is passed bad data, it won't be hurt, even if the bad data is another routine's fault
* Programs will have problems and modifications, and smart programmers develop code accordingly

#### 8.1 Protecting Your Program from Invalid Inputs
* Check the values of all data from external sources
  * Check that data falls within allowable range
  * Be sure that string size is short enough to handle and that it is valid for its intended purpose
* Check the values of all routine input parameters
* Decide how to handle bad inputs

#### 8.2 Assertions
* Assertions are primarily for use during development and maintenance
* Assertions are normally compiled into the code at development time and compiled out of the code for production
* Can be built into a language if they do not support assertions 
* Use error handling code for conditions that may occur; use assertions for conditions that should never occur
* Avoid putting executable code or function calls into assertions, use status variables instead
* Use assertions to document and verify preconditions and postconditions
  * Preconditions are the client code’s obligations to the code it calls
  * Postconditions are the routine’s or class’s obligations to the code that uses it
* For highly robust code, assert then handle the error anyway

#### 8.3 Error-Handling Techniques
Error handling options, all dependent on the situation:
* Return a harmless/neutral value
* Substitute the next piece of valid data (when streaming or sampling data)
* Return the same answer as the previous time
* Substitute the closest legal value
* Log a warning message to a file
* Return an error code
* Call an error-processing routine or object
* Display an error message wherever it is encountered
* Handle the error in whatever way works best locally
* Shut down

##### Robustness vs Correctness
* Correctness means never returning an incorrect result (good for safety-critical applications)
* Robustness means always doing something that will allow the software to keep operating (good for consumer applications)

#### 8.4 Exceptions
Exceptions can add complexity without taking the following precautions:
* Use exceptions to notify other parts of the program of errors that should not be ignored
* Throw exceptions for conditions that are truly exceptional, so exceptional that they should never occur
* Exceptions weaken encapsulation by requiring the code that calls a routine to know which exceptions might be thrown inside the code that’s called 
* Don't use an exception to pass the buck (handle the error locally if it makes sense to do so)
* Avoid throwing exceptions in constructors or destructors unless you catch them in the same place
* Throw exceptions at the right level of abstraction
  * Exceptions thrown are part of the routine interface, just like specific data types are
  * For example, do not use an EOF exception for a class that interprets data that is read from disk, instead use DataNotAvailable
* Include in the exception message all information that led to the exception
* Avoid empty catch blocks
* Know the exceptions your library code throws
* Consider building a centralized exception reporter - this would result in a simple call to the exception handling routine each time an exception is encountered
* Standardize your project's use of exceptions
  * Standardize what will be thrown (perhaps only objects derived from the Exception base class)
  * Consider creating you project's own exception base class
  * Define the specific circumstances under which code is allowed to use throw- catch syntax to perform error processing locally
  * Define the specific circumstances under which code is allowed to throw an exception that won’t be handled locally
  * Determine whether a centralized exception reporter will be used
  * Define whether exceptions are allowed in constructors and destructors
* Consider alternatives to exceptions
  * You should always consider the full set of error-handling alternatives: handling the error locally, propagating the error by using an error code, logging debug information to a file, shutting down the system, or using some other approach

#### 8.5 Barricade Your Program to Contain the Damage Caused by Errors
* Barricades are a damage containment strategy
* Designate certain interfaces as boundaries to "safe" areas
  * Check days crossing the boundaries for validity
  * Respond sensibly if invalid
* A class's public methods should assume all data passed to it is unsafe
* Private methods can assume data is safe
* Concert data to proper type as soon as it is input
* Use error handling outside the barricade
* Use assertions inside the barricade

#### 8.6 Debugging Aids
* Use offensive programming
  * Exceptional cases should be handled in a way that makes them obvious during development and recoverable during production
  * Make sure that asserts abort the program
  * Completely fill any memory allocated so you can detect memory allocation errors
  * Completely fill any files or streams allocated so you can detect file-format errors
  * Be sure each default or else case aborts the program
  * Fill an object with junk data just before it is deleted
* Plan to remove debugging tools for production
  * Use version control or build tools such as make
  * Use built in preprocessor
  * Build your own preprocessor
  * Use debugging stubs
    * Functions that test that values are what they should be
    * Swap out the functions to do nothing in production

#### 8.7 Determining How Much Defensive Programming to Leave in Production Code
* Leave in code that checks for important errors (leave out those that can error silently)
* Remove code that checks for trivial errors (via version control or separate builds)
* Remove code that results in hard crashes
* Leave code in that helps the program crash gracefully
* Log errors for your technical support personnel (change assertions to logs)
* Make sure the error messages you leave in are friendly
* Be sure the error logs do not give too much information to a potential attacker
