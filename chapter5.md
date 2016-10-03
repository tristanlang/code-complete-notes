### Chapter 5: Design in Construction
* Software design is the scheme of turning computer software into operational software
* Design links requirements to coding and debugging

#### 5.1 Key Design Concepts

##### Software's Primary Technical Imperative: Managing Complexity
* Try to organize programs so as to minimize the amount of a program that you need to think about at a time
* Use objects, packages, short routines
* To address complexity:
  * Minimize the amount of essential complexity (which arises out of designing software to address problems in and interface with the real world) that anyone's Brain has to deal with at any one time
  * Keep accidental complexity from needlessly proliferating

##### Desirable Characteristics of a Design
* Minimize complexity - if your design doesn't let you safely ignore most other parts of the program when you're immersed in one specific part, the design isn't doing its job 
* Ease of maintenance - design for the maintenance programmer
* Loose coupling - modules/classes should have as few interconnections as possible
* Extensibility - modular design
* Reusability
* High fan-in - classes should be used by other classes often
* Low-to-medium fan-out - classes should require fewer than ~7 other classes
* Portability - portable to new environments
* Leanness - as few components as possible
* Stratification - design the system so you can view it at one level without dipping into other levels
* Standard techniques - use standardized, common approaches

##### Levels of Design
1. Software system
2. Division into subsystems or packages
  * Identify major subsystems (database, business rules, user interface, etc)
  * To achieve this, must identify how to partition the system and how subsystems will interact
1. Division into classes within packages
  * Making sure that each subsystem has been decomposed to a level of detail fine enough that you can implement their parts as individual classes
  * Also how each class interacts with other classes (their interfaces)
1. Division into data and routines within classes
2. Internal routine design
  * Includes writing pseudocode, looking up algorithms, deciding how to organize the paragraphs of code in a routine, and writing the code

#### 5.2 Design Building Blocks: Heuristics
* Ways to think about design to help produce insight
* Heuristics are the trials in "trial and error"
1. Design objects as real world objects
  * Identify objects and their attributes (methods and data)
  * Determine what can be done to each object (methods?)
  * Determine what each object is allowed to do to other objects
    * Containment - objects containing other objects as fields & scope of what they can modify
    * Inheritance
  * Determine the public and private components of each object
  * Determine each objects public interface
2. Form consistent abstractions
3. Encapsulation - only provide as much access to details of each class as necessary
4. Inherit, when inheritance simplifies the design
  * Inheritance is the use of generalized operations on an object when the object is a specific, non-generalized instance
  * Polymorphism is the ability to use a generalized function without needing to know what specific type of object is calling the function
5. Information hiding
  * **Ask yourself: what about this object or variable should be hidden?**
  * Hide design and implementation decisions from other parts of the program
  * One key task in designing a class is visibility: deciding which features should be known outside the class and which should remain secret
  * The interface to a class should reveal as little as possible about its inner workings
  * Secrets in information hiding fall into two general camps:
    * Hiding complexity so that your brain doesn't have to deal with it unless you're specifically concerned with it
    * Hiding sources of change so that when change occurs, the effects are localized
  * Barriers to information hiding
    * Excessive distribution of information
      * Use access routines instead of global variables
      * This way only the access routines will know the implementation details
    * Perceived performance penalties
      * The concern is that accessing data items indirectly incurs run time performance penalties for additional levels of object instantiations, routine calls, and so on
      * Until you can measure the system's performance and pinpoint bottlenecks, the best way to prepare for code level performance work is to create a highly modular design
6. Identify areas likely to change
  * The goal is to isolate unstable areas so that the effect of a change will be limited to one routine, class, or package
    1. Identify items that seem likely to change
    2. Separate items that are likely to change
      * Compartmentalize each volatile component from #1 into its own class or into a class with other volatile components likely to change at the same time
    3. Isolate items that seem likely to change
      * Design the interclass interfaces to be insensitive to the potential changes
      * Design the interfaces so that changes are limited to the inside of the class and the outside remains unaffected
7. Keep coupling loose
  * Coupling is how tightly a class or routine is related to other classes or routines
  * The goal is to create classes and routines with small, direct, visible, and flexible relations to other classes and routines
  * The more easily other modules can call a module, the more loosely coupled it is = more flexible and maintainable
  * Coupling criteria
    * Size - the number of connections between modules should be as few as possible (small interfaces, few parameters to routines)
    * Vsibility - prominence of the connection between two modules (parameter lists vs changing global variables)
    * Flexibility - how easily you can change the connections between modules
  * Semantic coupling - examples of coupling to avoid
    * Passing a control flag from one module to another - probably ok but still requires module1 to know some of the inner workings of module2
    * Module2 uses global data after it has been modified by module1
    * Initializing partial objects that get passed between modules
    * Casting parameters from generic types to specific types - just use specific type as parameter
  * If using a module requires you to focus on more than one thing at once (knowledge of inner workings, modification to global data, uncertain functionality) the abstract or power is lost and the module's ability to help manage complexity is reduced or eliminated
8. Look for common design patterns
9. Aim for strong cohesion
  * All routines in a class or all code in a routine should support a central purpose
  * The module should be very focused
10. Design for test

#### 5.3 Design Practices
* Steps you can take that often produce good results
* Iterate
* Divide and conquer
    * Divide into different areas of concern and iterate on each area
    * Incremental refinement: understand the problem, devise a plan, carry out the plan, and then look back to see how you did 
* Top down design
    * Continue decomposing until it seems as if it would be easier to code the next level than to decompose it
    * Work until you become somewhat impatient at how obvious and easy the design seems
* Bottom up design
    * Ask yourself what you know the system needs to do
    * Identify concrete objects and responsibilities from that question
    * Identify common objects, and group them using subsystem organization, packages, composition within objects, or inheritance, whichever is appropriate
    * Continue with the next level up, or go back to the top and try again to work down
* Experimental prototyping
    * Some software problems are "wicked" - solutions can only be designed for them by solving them
    * Write the absolute minimum amount of code needed to answer a question
    * This code should be treated as throwaway code that only helps define the problem
    * Write in non-production language or prefix with "prototype" to prevent the throwaway code from going into production
* When is design done?
  * Depends on the project but generally it is better to err on the side of more detailed design rather than starting to code with less design
  * Capture design discussions and decisions on a wiki
