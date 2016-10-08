### Chapter 6: Working Classes

#### 6.1 Class Foundations: Abstract Data Types (ADTs)
* ADT = data and a collection of operations to view or change that data
* Treat the ADT as what it represents rather than as a data type
* Class = ADT + Inheritance + Polymorphism

#### 6.2 Good Class Interfaces

##### Good Abstraction
* Class interface should offer a group of routines that clearly belong together
* The evaluation of class abstraction is based on the class's collection of public routines - the interface
* Present a consistent level of abstraction in the class interface
  * to determine what the "level" of abstraction is, determine what each function in the interface is operating on
  * is it an Object?
  * is it a list of Objects?
  * **each class should implement exactly one ADT**
  * **reorganize the class into one or more well defined ADTs if you find that it implements more than one ADT or if you cannot determine what ADT it implements**
* be sure you understand what abstraction the class is implementing
* Provide services in pairs with their opposites (e.g. AddItem/RemoveItem), if necessary
* Move unrelated information to another class
* Make interfaces programmatic rather than semantic when possible
  * programmatic means to leave the work to the interface and compiler - the routines should ensure that they are independent of the order in which they are called
  * semantic means the routines in the interface are dependent on being called in a certain order or that they require certain data to be initialized first
  * semantic requires documentation
* beware of erosion of an interface's abstraction under modification - make sure the abstraction is still properly maintained
* Each time you add a routine to a class interface ask, "Is this routine consistent with the abstraction provided by the existing interface?"

##### Good Encapsulation
* hiding & bundling internal data and implementation details from other modules
* Minimize the accessibility of classes and members
  * err on the side of preserving the abstraction
* don't expose member data in public
* Avoid putting private implementation details into a class's interface
  * when the language forces you to (c++), include the implementation details in a separate class and a reference to those details
* a class should not make assumptions about how its interface will or will not be used (a class shouldn't be aware of its users)
* Avoid friend classes(?)
* Favor read time convenience to write time convenience (code is read many more times than it is written
* Always be sure a routine that gets added to an interface is consistent with its abstraction
* Avoid relying on a class's private implementation whenever possible
* Program to the interface, not the private implementation

#### 6.3 Design and Implementation Details

##### Containment ("has a" relationship)
* class contains a primitive data element or an object
* Be critical of a class that has more than about 7 data members

##### Inheritance ("is a" relationship)
* when you decide to use inheritance you must make several decisions
  * for each member routine, will the routine be visible to derived classes? Will it have a default implementation? Will that implementation be overridable?
  * for each data member, will it be available to derived classes?
* Implement "is a" through public inheritance (specialization)
  * base class sets expectations for and constraints on how the derived class can operate
   * if the derived class is not going to adhere completely to the interface of the base class, inheritance is a bad choice, try containment or making a change up the inheritance hierarchy instead
* Design for and document inheritance or prohibit it (members would be non-virtual in c++, final in java)
* Adhere to the Liskov Substitution Principle (LSP) - derived classes should be able to use the base class interface without a user noticing the difference
* Be sure to inherit only what you want to inherit… think through the inherited routine implementation you want for each routine. Variations on inherited routines:
  * abstract overridable routine - derived class inherits the routine’s interface but not implementation
  * overridable routine - derived class inherits the routine’s interface and default implementation, is allowed to override implementation
  * non-overridable routine - derived class inherits the routine’s interface and default implementation, not allowed to override implementation
* Use containment instead of inheritance if you want to use a class’s implementation but not its interface
* Don’t reuse names of non-overridable base class routines in derived classes
* Move common interfaces, data, and behavior as high as possible in the inheritance tree (as high as abstraction makes sense for it to be)
* Be suspicious of classes of which there is only one instance
* Be suspicious of base classes of which there is only one derived class
  * typically found when “designing ahead”, anticipating future needs without fully understanding what the future needs are
  * best way to prepare for future work is to make current work as clear, straightforward, and simple as possible
* Be suspicious of classes that override a routine and do nothing inside the derived routine
  * indicates a problem in the base class
  * for example, not all Cats scratch, so create a Class class and contain that within the Cats class
* Avoid deep inheritance trees (2-3 levels deep, max)
* Prefer polymorphism to extensive type checking
* Make all data private, not protected

##### Multiple Inheritance
* May be useful but also can significantly increase complexity
* Primarily useful for “mixins” - mixing in of properties from multiple base classes to derived classes
* Java allows multiple inheritance of interfaces but only single-class inheritance, C++ allows multiple inheritance of interface and implementation

##### Inheritance vs Containment
* Classes share common data but not behavior ==> containment
* Classes share common behavior but not data ==> inheritance (base class has common routines)
* Classes share common data and behavior ==> inheritance (base class has common data and routines)
* Inherit when you want the base class to control your interface
* Contain when you want to control your interface

##### Member Functions and Data
* Keep the number of routines in a class as small as possible
* Disallow implicitly generated member functions and operators you don’t want (make them private)
* Minimize the number of different routines called from within a class (want low-fan out)
* Minimize indirect routine class to other classes (Law of Demeter - Object A can call its own routines, if it instantiates Object B it can call B’s routines, but it cannot call routines of objects instantiated by B)
* Minimize the extent to which a class collaborates with other classes
  * minimize number of kinds of objects instantiated
  * minimize number of different direct routine calls on instantiated objects
  * minimize number of routine calls on objects returned by other instantiated objects

##### Constructors
* Initialize all member data in all constructors, if possible
* Enforce the singleton property by using a private constructor
* Prefer deep copies to shallow copies until proven otherwise
  * deep copy - member-wise copy of object’s member data
  * shallow copy - reference copy

#### 6.4 Reasons to Create a Class
* Model real-world objects
* Model abstract objects
* Reduce complexity (fewer data members to keep in mind)
* Isolate complexity (looser coupling)
* Hide implementation details
* Limit effects of changes
* Hide global data
* Streamline parameter passing (use a class instead of passing parameters around to many functions)
* Make central points of control
* Facilitate reusable code
* Plan for a family of programs
* Package related operations
* Accomplish a specific refactoring
