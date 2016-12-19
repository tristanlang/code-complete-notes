### Chapter 26: Code-Tuning Techniques
* No code tuning technique is guaranteed to work
* Must measure improvements
* If an optimization isn’t important enough to haul out the profiling machinery, it isn’t important enough to degrade readability, maintainability, and other code characteristics

#### 26.1 Logic
* Stop when you know the answer
* Order tests by frequency (if & case)
* Compare performance of similar logic structures (if vs case)
* Substitute table lookups for complicated expressions
* Use lazy evaluation and caching

#### 26.2 Loops
* Unswitching - move conditionals outside of loops if they don't change inside the loop
* Jamming - combining loops that operate on the same set of elements
* Unrolling
  * Put loop further into straight line code by incrementing by 2 more more instead of by 1
  * Must perform operations on militiamen elements in each loop iteration
* Minimizing work inside loops (any function calls or db queries that do not change vale with each iteration)
* Sentinel values
  * Used in search loops to determine whether the sentinel value is found
  * Can use a Boolean value that is checked with each iteration
  * Can also use an extra element at the end of an array that is set to the sentinel value, loop through the array, if the sentinel value is found break, check the loop control variable value after the loop to see if it is the array's length or if it is less (less means the sentinel value exists in the array)
* Putting the busiest loop on the inside
* Strength reduction
  * Replacing an expensive operation such as multiplication with a cheaper operation such as addition
  * Use variables to store running sums when necessary
  * Calculate multiplied values before the loop instead of with each iteration

#### 26.3 Data Transformations
* Use integers rather than floating point numbers
* Use the fewest array dimensions possible (use vectors not matrices)
* Minimize array references (such as accessing data from the same array index with each iteration of an inner loop)
* Use supplementary indexes
  * String length
  * Using a parallel data structure that stores indexes to the actual data structure
* Use caching

#### 26.4 Expressions
* Exploit algebraic identities (have as few operations as possible)
* Strength reduction
  * Replace multiplication with addition
  * Replace exponentiation with multiplication
  * Replace trigonometric routines with their trigonometric identities
  * Replace floating point numbers with fixed point numbers or integers
  * Replace integer multiplication/division by 2 with shift operations
* Initialize at compile time (rather than calculating the value of constants, use literals)
* Be wary of system routines
* Use the correct types for constants (to avoid unnecessary type casts)
* Precommits results (lookup table or caching, save to file or store in memory)
* Eliminate common subexpressions (duplicated code)

#### 26.5 Routines
* Rewrite routines in line

#### 26.6 Recoding in a Low-Level Language (relative to the original language in question)
1. Write 100% of a program in a high level language
2. Test and verify that it is correct
3. Identify hot spots
4. Recode the hot spot areas in a low level language
