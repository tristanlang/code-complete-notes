### Chapter 25: Code-Tuning Strategies
* Code tuning is the process of modifying correct code in ways that make it run more efficiently
* Small scale changes (class or routine), not full redesign

#### 25.1 Performance Overview
* To the extent that you're working on code's speed, you're not working on other quality characteristics, so be wary of sacrificing other characteristics to make code faster
* Once you've chosen efficiency as a priority (of speed or size), think about efficiency from each of these viewpoints:
  * Program Requirements
  * Program Design
    * If you know size and speed are important, set specific resource requirements for the system
    * Set goals for individual subsystems, features, and classes
    * You can redesign components that do not need their resource goals
  * Class and Routine Design
    * **This is where data structure and algorithm selection are important**
  * Operating System Interactions
    * File descriptors, dynamic memory, output devices, etc. imply OS interactions
  * Code Compilation
    * Good compiler tuning may be all that is necessary and can provide better results than code tuning
  * Hardware
  * Code Tuning

#### 25.2 Introduction to Code Tuning
* Pareto Principle (80/20)
  * Complete it, then optimize it
  * Places to optimize are usually small
  * 20% of routines take up 80% of the execution time
* When you tune code, you’re implicitly signing up to reprofile each optimization every time you change your compiler brand, compiler version, library version, and so on
  * Any change in the above can cause your previous code tuning to result in worse performance
* Work on performance improvements after the program is functional
  * Won't know where to focus for tuning code if it is not working as a system yet
  * Focusing on optimization during initial development will detract from other program objectives
  * Post hoc performance work typically affects less than five percent of a program’s code
  * Harder to focus on code quality improvements later 
  * If the development time saved by implementing the simplest program is devoted to optimizing the running program, the result will always be a program that runs faster than one developed with indiscriminate optimization efforts
* **When to tune**
  * Use a high-quality design
  * Make the program right
  * Make it modular and easily modifiable so that it’s easy to work on later
  * **When it’s complete and correct, check the performance**
  * **If the program lumbers, make it fast and small**
  * **Don’t optimize until you know you need to**

#### 25.3 Kinds of Fat and Molasses
* Common Sources of Inefficiency
  * Input/output operations (use memory instead of db when possible)
  * Paging (swapping memory pages)
  * System calls
  * Interpreted languages
* Improve speed by replacing expensive operations with cheaper ones

#### 25.4 Measurement
* Need to measure performance to know if code has been properly tuned (or where to tune)
* Use CPU ticks or system time

#### 25.5 Iteration
* Iterate to improve code enough for performance goals

#### 25.6 Summary of the Approach to Code Tuning
1. Develop software that is easy to understand and modify
2. If performance is poor
  * Save working version in a new branch
  * Measure the system to find hot spots
  * Determine whether the weak performance comes from inadequate design, data types, or algorithms and whether code tuning is appropriate. If code tuning isn’t appropriate, go back to the previous step. 
  * Tune the code based on findings
  * Measure each improvement one at a time
  * Revert the code if the improvement does not affect performance
3. Repeat from step 2
