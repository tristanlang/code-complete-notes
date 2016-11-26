### Chapter 14: Organizing Straight-Line Code

#### 14.1 Statements That Must Be in a Specific Order
* When statements have dependencies that require them to be executed in a certain order, take steps to make them obvious
* Organize code and name routines so that dependencies are obvious
* Use routine parameters to make dependencies obvious 
* Document unclear dependencies with comments
* Can use assertions and error handling to ensure dependencies are met

#### 14.2 Statements Whose Order Doesn't Matter
* Principle of Proximity: keep related actions together
* After writing a set of statements, try to put an imaginary block around related statements, there should be no overlap, ideally
* Make the program read from top to bottom
