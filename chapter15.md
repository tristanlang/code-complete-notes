### Chapter 15: Using Conditionals

#### 15.1 if Statements
* Write the normal path through the code first, then write the unusual cases
* Make sure that you branch correctly on equality (e.g. > vs >=)
* Put the normal case after the if rather than after the else
* Follow the if clause with a meaningful statement (comment or code?)
* Consider the else clause (possibly include with a comment and nothing more for completeness)
* Test the else clauses for correctness
* Check for reversal of the if and else clauses
* Chains of if-elseif-else statements
  * Simplify complicated tests with Boolean function calls to make them more readable
  * Put the most common cases first
  * Make sure all cases are covered
  * Replace if-elseif-else chains with case statements if possible

#### 15.2 case Statements
* Keep the actions of each case simple
  * Write a routine and call the routine if the actions are complex
* **Don't make up phony variables to be able to use the case statement**
  * case statement is for simple data that is easily categorized
  * Otherwise use if else statements instead
  * **Phony variable is indicated by not checking the real life cases you want to check, but rather forcing a variable to fit into the case statement**
* Use the default clause only to detect legitimate defaults
* Use the default clause to detect and log errors
* In C++ clearly and unmistakably identify flow-throughs at the end of a case statement (but generally AVOID)
