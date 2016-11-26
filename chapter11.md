### Chapter 11: The Power of Variable Names

#### 11.1 Considerations in Choosing Good Names
* A good name is readable, memorable, and appropriate
* MUST fully and accurately describe the entity the variable represents
* State in words what the variable represents
* Favor names that refer to the problem being solved by the variable
* Check that variable names are as short as they need to be or if you can be more descriptive by adding to them
* Ideal variable length is roughly 10-16 characters
* Longer names tend to be better for rarely used variables
* Shorter names tend to be better for local and loop variables
* Use qualifiers on names that are in the global namespace/package
* Put computed value qualifiers (total, sum, count, average, etc.) at the end of variable names (revenueTotal, etc)

#### 11.2 Naming Specific Types of Data
* Naming Boolean variables
  * Keep typical Boolean names in mind (done, error, ok, success, found)
  * Give Boolean variables names that imply true or false
  * Use positive Boolean variable names
* Naming enumerated types
  * Use the enum type itself as a prefix to the enum members
  * If the language treats enums in a manner similar to classes, no need to add the enum type as a prefix
* Name constants for what they represent rather than the number they take as a value

#### 11.3 The Power of Naming Conventions
* Useful when multiple programmers are working on a project
* Useful when program is so large that all of it cannot be maintained in your mind at once
* To standardize terms and abbreviations
* Useful when a program will be developed or used over a long period of time

#### 11.4 Informal Naming Conventions
* Identify global variables (such as with "g_" prefix)
* Identify member variables (such as with "m_" prefix)
* Identify type definitions (such as with "t_" or ALLCAPS)
* Identify named constants (such as with "c_" or ALLCAPS)
* Identify elements of enumerated types (such as with "e_" or "E_" for the type itself and the type as a prefix for members)
* Identify input only parameters in languages that don't enforce them (such as a "const" _prefix_)
* Format names to enhance readability

#### 11.5 Standardized Prefixes
* User-Defined Type Abbreviations
  * UDTs are described with short codes that you create for a specific program and then standardize on for use in that program
  * Such as crm for consensus raft manager
* Semantic Prefixes
  * Semantic prefixes go a step beyond the UDT and describe how the variable or object is used
  * semantic prefixes are somewhat standard across projects
  * min, max, p, lim, first, last, c (count), i (index)
  * iPa = index of a paragraph in an array

#### 11.6 Creating Short Names that are Meaningful
* General guidelines for using abbreviations
  * Use the standard abbreviations found in a dictionary
  * Use the first or first few letters of each word
  * Remove non-leading vowels
  * Truncate consistently after the first, second, or third letter of each word
  * Keep the most noticeable sound in each variable
  * Do not change the meaning of the variable
  * Iterate until a good variable name is found
* If you can’t read your code to some- one over the phone, rename your variables to be more distinctive 
* Use a thesaurus to resolve naming collisions in abbreviations
* Document extremely short names with a translation table in the code
* Document all abbreviations in a project level Standard Abbreviations document
* Remember that names matter more to the reader of the code than the writer

#### 11.7 Kinds of Names to Avoid
* Avoid names with misleading abbreviations
* Avoid names with similar meanings
* Avoid variables with similar names but different meanings
* Avoid names that sound similar
* Avoid numerals in names (use an array instead)
* Don't differentiate variable names solely by capitalization
