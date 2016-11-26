### Chapter 18: Table-Driven Methods **TO REREAD**
* A table driven method uses a lookup table or array or map rather than logic statements
* Useful when working with more complex logic chains
* Can look up an entry in a table via:
  * Direct access
  * Indexed access
  * Stair-step access
* The table must store data or an action or a reference to a routine associated with a specific lookup value

#### 18.2 Direct Access Tables
* Direct access tables store data in the lookup table directly
* Complex example of how lookup keys make for a much simpler solution in some cases, p 416

#### 18.3 Indexed Access Tables
* When you use indexes, you use the primary data to look up a key in an index table and then you use the value from the index table to look up the main data you’re interested in 
* Index is quite often much cheaper in terms of resources than the main table
* Data encoded in tables is easier to maintain than data embedded in code

#### 18.4 Stair-Step Access Tables
* Access table that is based on bucketing/classifying
* Put the upper end of each range into a table, then write a loop to check the value against the upper end of each range
* When you find the point at which the score first exceeds the top of a range, you know what the lookup value is
* Very flexible approach, and it is useful for tables that include ugly numbers
* Subtleties to consider
  * Watch the endpoints (including top of the uppermost range)
  * Consider using a binary search instead of a sequential search
  * Consider using indexed access instead of the stair step technique
  * Put the stair step table lookup into its own routine
