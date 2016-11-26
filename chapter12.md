### Chapter 12: Fundamental Data Types

#### 12.1 Numbers in General
* Avoid magic numbers
* Use hard coded 0s and 1s for loop variables or array access if necessary
* Avoid mixed-type comparisons

#### 12.2 Integers
* Check for integer overflow when multiplying or adding integers
* Check for overflow in intermediate results

#### 12.3 Floating-Point Numbers
* Avoid addition and subtraction on numbers that differ greatly in magnitude (if necessary, start with the small and work toward the large)
* Avoid equality comparisons (use acceptable deltas if necessary)
* Anticipate rounding errors
  * Change to a type that has greater precision
  * Change to binary coded decimal (BCD) values
  * Change to using integers instead of floating point values
  * Check for library support for specific data types

#### 12.4 Characters and Strings
* Avoid magic characters and strings
* Watch for off-by-one errors with substring indexes
* Know how your language and environment support Unicode natively (if not, decide where and when to use Unicode strings)
* If you need to support multiple languages, use Unicode
* If you will only use one language, consider using ISO 8859 character set (ASCII?)
* Declare C-style strings to have length CONSTANT+1 (to include null terminator at the end of the string, byte set to 0)
* Initialize strings to null to avoid endless strings in C
* Use strncopy() instead of strcopy() to avoid endless strings in C (the “strn” version stops after a maximum length, rather than at a null terminator)

#### 12.5 Boolean Variables
* Use boolean variables to document your program
* Use boolean variables to simplify complicated tests

#### 12.6 Enumerated Types
* Enumerated types are generally used when you know all the possible values of a variable and want to express them in words
* Enumerated types improve readability, reliability, and modifiability
* Use enumerated types as an alternative to boolean variables, to be more expressive
* Can include enumerated first and last values for loop iteration (Country_First = 0; Country_USA = 0; Country_Last = 1; Country_Japan = 1)
* Reserve the first entry in the enumerated type (which has value 0) as invalid because invalid values are more likely to be 0 than any other value

#### 12.7 Named Constants
* Use constants instead of literals, even the "safe" ones
* Use named constants consistently instead of not using it in some places but using the constant in others

 #### 12.8 Arrays
* Consider using containers (sets, queues, stacks) instead of arrays, or think of arrays as sequential structures
  * Some of the brightest people in computer science have suggested that arrays never be accessed randomly, but only sequentially
  * Better to just use sets, stacks, queues, whose elements are accessed sequentially instead
* Check that your code correctly accesses the first, last, and a middle element of an array

#### 12.9 Creating Your Own Types (Type Aliasing)
* Useful for information hiding
* Makes modifications easier
* Create types with functionally oriented names (use real world names)
* Avoid predefined types
* Don't redefine a predefined type
* Consider creating a class instead of a typedef
