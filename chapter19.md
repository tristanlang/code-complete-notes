### Chapter 19: General Control Issues

#### 19.1 Boolean Expressions
* Compare Boolean values to true and false implicitly
* Break complicated tests into partial tests with new Boolean variables
* Move complicated expressions into Boolean functions
* Use decision tables to replace complicated conditions
* Better to express conditions as positives rather than negatives because it is easier to understand
* Apply DeMorgan's Theorems to simplify multiple logical expressions into one (a single `not` wrapping and negating the entire condition)
* Use parentheses to simplify logical expressions
* When using numerical comparisons, organize them from smallest to largest (MIN < x && x < MAX)
* Consider putting constants and literals on the left side of comparisons to prevent erroneous assignments (= instead of ==)
* In java, know the difference between `==` and `.equals`

#### 19.2 Compound Statements (Blocks)
* Write braces together
* Use braces to clarify conditionals

#### 19.3 Null Statements
* Null statement is a line with just a semicolon on it
* Call attention to null statements by indenting them as normal and putting them on their own line
* Create a preprocessor DoNothing() macro
* Consider whether the code would be clearer with a non-null loop body

#### 19.4 Taming Dangerously Deep Nesting
* Best to limit nesting/indentation to 3-4 levels deep
* Simplify nested ifs by retesting part of the condition
  * Will involve testing multiple times for some conditions
  * Allows for less indentation by repeating the conditions
* Simplify a nested if by using a breaking block (while loop that only gets executed once and is broken out of if condition fails)
* Convert a nested if to a set of if-else statements
* Convert a nested if to a case statement
* Faster deeply nested code into its own routine
* Use a more object oriented approach
  * Use a base class with subclasses for the actions after each condition
  * Can use a factory method to create the derived classes
* Redesign deeply nested code entirely

#### 19.5 A Programming Foundation: Structured Programming
* Structured programming is using single-entry, single-exit control constructs
* A structured program progresses in an orderly, disciplined, predictable way
* The three components of structured programming
  * Sequence: a set of statements executed in order (assignments and calls to routines)
  * Selection: a control structure that causes a statement to be executed selectively
  * Iteration: a control structure that causes a group of statements to be executed multiple times
* Core thesis of structured programming is that **any control flow (program) can be created from these three constructs of sequence, selection, and iteration**
* Use of any control structure other than the three standard structured programming con- structs—that is, the use of break, continue, return, throw-catch, and so on—should be viewed with a critical eye

#### 19.6 Control Structures and Complexity
* Control structures contribute directly to complexity
* Poor use increases complexity
* Good use decreases complexity
* **Mental juggling or control structures is difficult and is why programming requires more concentration than other activities**
* Control flow is at least one of the largest contributors to complexity, if not the largest 
* Tom McCabe’s cyclomatic complexity metric measures how complex a program is, by counting the number of “decision points” in a routine
  * Start with 1 for the straight line path through the routine
  * Add 1 for each of the keywords: if while for repeat and or
  * Add 1 for each case in a case statement
* Score the routine
  * 0-5: routine is probably fine
  * 6-10: start to think about ways to simplify the routine
  * 10+: break the routine into a second routine and call it from the first
