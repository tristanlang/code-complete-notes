### Chapter 29: Integration
* “Integration” refers to the software-development activity in which you combine several software components into a single system
* The order in which you build classes or components affects the order in which you integrate them

#### 29.1 Importance of the Integration Approach
* Careful integration of components saves time and prevents defects

#### 29.2 Integration Frequency - Phased or Incremental?
* Phased
  * Unit Development - design, code, test, and debug each class
  * System Integration - combine the classes into one whopping-big system
  * Test and debug the whole system
  * This approach is problematic because many errors surface all at once from the unknown/unintended behavior of classes with one another
* Incremental
  * Develop a small, functional part of the system. Thoroughly test and debug it. It will be the skeleton of the system.
  * Design, code, test, and debug a class
  * Integrate the new class with the skeleton. Test and debug the combination. Make sure the combination works before adding any new classes. Repeat step 2 if necessary. 
* Benefits of incremental integration
  * Errors are easy to locate
  * The system succeeds early in the project
  * You get improved progress monitoring
  * You'll improve customer relations
  * The units of the system are tested more fully
  * You can build the system with a shorter development schedule (by doing work in parallel)

#### 29.3 Incremental Integration Strategies
* Integration order affects construction order so both must be planned
* Top down integration
  * Component or class at the top of the hierarchy is written and integrated first
  * Stubs are written for subcomponents
  * Replace stubs are classes are integrated
  * Interfaces between classes must be carefully specified
  * Use vertical slice integration as an alternative to pure top down integration (do one component at the second level all the way to the finest level of detail before the next)
* Bottom up integration (low level classes first)
  * Allows you to work on individual classes early on
  * Requires completion of the design of the whole system before you start integration
  * Can use vertical slice approach here too
* Sandwich integration
  * Start with high and low level components
  * Work on middle classes later
  * Minimizing scaffolding needed
* Risk-Oriented Integration
  * Hard part first integration
  * Implement most challenging components first
* Feature-Oriented Integration
  * Requires an initial skeleton to hang other components off of
  * Eliminates scaffolding for almost everything
  * Each newly integrated feature brings about an incremental addition in functionality
  * Works well with OO design
* T-Shaped Integration
  * One specific vertical slice is selected for early development and integration

#### 29.4 Daily Build and Smoke Test
* Compile and test a system daily to make sure it never deteriorates
* Forces developers to get in sync on a regular basis
* Smoke test exercises the system from end to end to expose major problems (not necessarily exhaustive)
* Smoke test should evolve as the system evolves
* Automate the daily build and smoke test
* Don't wait too long to add a set of revisions to the system or you may not know what changes caused some issues
* Require developers to smoke test their code before adding it to the system
* Release new builds in the morning
