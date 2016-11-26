### Chapter 22: Developer Testing
* Unit, component, integration testing
* Regression and system testing
* Black box testing: tester does not know the inner workings of what is being tested
* White/glass box testing: tester knows the inner workings

#### 22.1 Role of Developer Testing in Software Quality
* Developer testing may not catch all error cases
* It requires testers to think about breaking code, which runs counter to the way in which code is normally written
* Test code should comprise 8-25% of total time on a project
* Advantageous to treat a class as a white box when testing (should test more than just the interface)

#### 22.2 Recommended Approach to Developer Testing
* Test for each relevant requirement to ensure it is implemented 
  * Ideally test cases are planned during requirements gathering phase
* Test each relevant design concern to make sure it had been implemented 
  * Plan test cases at design stage
* Add basis tests and data flow tests
* Add additional tests to ensure every line of code is tested
* Write test cases before code to minimize time until defects are found
* Limitations of developer tests
  * Developer tests tend to be clean tests (good tests should try to break the code...key is to have a lot of dirty tests)
  * Developer testing tends to skip more sophisticated kinds of test coverage (better to test every possible branch)

#### 22.3 Bag of Testing Tricks
* The art of testing is that if picking the test cases most likely to find errors
* When planning tests, eliminate those that do not test anything new - those that have inputs similar to those that were already tested
* Structured basis testing
  * Test each statement at least once
  * Start with one test for the straight path through the routine 
  * Add one test for each of the following keywords: if, while, repeat, for, and, or
  * Add one test for each case in a case statement 
  * Ensures that all code is tested but does not account for variations in data (tests control flow)
* Data flow testing
  * Data can exist as defined, used, or killed
  * Data relative to the control flow
    * Entered: data that begins to exist only immediately after entering a control
    * Exited: data that is assigned immediately prior to exiting a control
  * Anomalous data flow type combinations (should not exist)
    * Defined-Defined
    * Defined-Killed
    * Defined-Exited
      * maybe ok if routine or global variable
      * does not make sense to define a variable and exit without using it
    * Entered-Used
      * only ok if it is a routine or global variable that is defined elsewhere before being used
    * Entered-Killed
      * only ok if it is a routine or global variable that is defined elsewhere before being killed
    * Killed-Killed
    * Killed-Used
    * Used-Defined
  * After checking all anomalous cases, the key to writing data-flow test cases is to exercise all possible defined-used paths    * Test every combination of defining a variable in one place and using it in another    * Use the smallest number of test cases possible to cover all defined-used combinations
* Equivalence Partitioning: if two test cases flush out the same errors, you only need one of them
* Error Guessing: creating test cases based upon guesses about where the program might have errors 
* Boundary Analysis
  * Write test cases that exercise boundary conditions and catch off by one errors
* Classes of Bad Data
  * Too much data
  * Too little data
  * Invalid data
  * Uninitialized data
  * Wrong size of data
* Classes of Good Data
  * Must test nominal cases to ensure expected data inputs produce expected outputs
  * Test min/max normal values
  * Test compatibility with old data

#### 22.4 Typical Errors
* Most errors tend to be concentrated in a few highly defective routines
* Maintenance activities should focus on identifying, redesigning, and rewriting from scratch those routines that have been identified as error prone
* Most errors are limited to a single routine
* Misunderstanding design is a common cause of errors
* It's cheaper to build high quality software than it is to build and fix low quality software
* Errors are often found in the test code itself

#### 22.5 Test-Support Tools
* Build scaffolding to test individual classes
* Scaffolding is dummy/mock/stub classes or routines that do specifically what you need to set up tests
* Test harness is a fake routine that calls the real routine which is being tested
