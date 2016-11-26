### Chapter 23: Debugging

#### 23.1 Overview of Debugging Issues
* An error in your program is an opportunity
  * Learn about the program you're working on
  * Learn about the kinds of mistakes you make
    * Ask yourself how and why you made the mistake
    * How could you have found it more quickly or prevented it?
    * Are there similar mistakes elsewhere in the code?
  * Learn about the quality of your code from the perspective of someone that has to read it; refactor if necessary

#### 23.2 Finding a Defect
1. Stabilize the error (make it reproducible)
2. Locate the source of the error
  * Gather the data that produces the defect
  * Analyze the data and form a hypothesis about the defect
  * Determine how to prove or disprove the hypothesis (set up tests or examine code)
  * Prove or disprove the hypothesis
3. Fix the defect 
4. Test the fix
5. Look for similar errors 
* Tips for finding a defect
  * If you have trouble finding a defect, it may be due to poorly written code
  * Use all of the data available to make your hypothesis
  * If you can’t find the source of an error, try to refine the test cases further than you already have (solution may be in modifying a single parameter)
  * Brainstorm for several possible hypotheses before testing them 
  * Narrow the suspicious region of code via commenting code out
  * Be suspicious of classes and routines that have had defects before
  * Check code that has changed recently
* Brute force debugging
  * Rewrite the entire routine, class, program
  * Limit your time spent before resigning yourself to using brute force debugging

#### 23.2 Fixing the Defect
* Make sure you fully understand the problem and the program (context of the problem)
* Confirm the defect diagnosis by running tests and ruling out other hypotheses
* Relax
* Fix the problem not the symptom 
* Only change code for good reason (you should be confident your fix will work)
* Make only one fix at a time
* Check your fix
* Add test code that exposes the defect
* Look for similar defects
