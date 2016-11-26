### Chapter 16: Controlling Loops

#### 16.1 Selecting the Kind of Loop
* Use a while loop when you don't know how many times you want the loop to iterate
* Use a for loop when you need a loop that executes a specified number of times
* Use a foreach loop to perform an operation on each member of an array or other container

#### 16.2 Controlling the Loop
* Minimize the number of factors that affect the loop
* Treat the inside of the loop as if it were a routine
* Explicitly state the conditions under which the loop is to be executed (via comments or self documented code)
* Entering the loop
  * Enter the loop from one location only
  * Put initialization code directly before the loop (principle of proximity)
  * Use while true for infinite loops
  * Prefer for loops when they're appropriate
  * Don't use a for loop when a while loop is more appropriate (such as forcing a for loop's conditions to look like that of a while loop)
* Processing the middle of the loop
  * Use braces to enclose the statements in a loop
  * Avoid empty loops, where the work is done in the loop condition
  * Keep loop housekeeping chores (such as i++) at the beginning of end of the loop
  * **Make each loop perform only one function**
* Exiting the loop
  * Assure yourself that the loop ends, even in exceptional cases
  * Make loop termination conditions obvious by putting the control in one place
    * Avoid return statements in the middle of a loop and use break instead??
    * Avoid using a break statement to exit a for loop because the termination condition is already defined
  * Don't monkey with the loop control variable in a for loop to make the loop terminate
  * Avoid code that depends on the final value of the loop index (assign the value to a variable if necessary)
  * Consider using safety counters to increment and check a counter that ensures that any catastrophic errors due to too many loops could be avoided
* Exiting loops early
  * Consider using break statements instead of Boolean flags in a while loop
  * Be wary of loops with a lot of break statements scattered throughout
  * Use continue for tests at the top of a loop
  * Use a labeled loop/break structure if supported
  * Use break and continue only with caution because they add complexity by adding extra exit conditions (loop will be able to exit in more than one place)
* Check endpoints, first and last elements and other edge cases
* Using loop variables
  * For multidimensional arrays, give meaningful names to the loop variables instead of i,j,k
  * If the loop body has more than a few lines, use meaningful variable names instead of i,j,k
  * Limit the scope of loop index variables to the loop itself
* Properly adjusting loop length
  * Make loops short enough to view on one screen
  * Limit nesting to three levels
  * Move bodies of long loops into routines
  * Make long loops especially clear (try to avoid continue and break statements for longer loops, stick to single entry/exit)

#### 16.3 Creating Loops Easily: Inside Out
1. Start with one case
2. Code that case with literals
3. Indent it, wrap with a loop, and replace literals with loop indexes or computed expressions
4. Put another loop around that if necessary and replace more literals
5. Continue as long as necessary
6. Add all necessary initializations
