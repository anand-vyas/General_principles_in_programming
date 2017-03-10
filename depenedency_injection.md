Depenedency Injection
This is a general design principle in programming. 

Source(s): 
https://www.youtube.com/watch?v=IKD2-MAkXyQ

As the name suggests, dependency injection means to 'inject' a dependency. 
It is used for de-coupling the construction of a class from the contruction of its dependencies. 


Say there is a class A. A uses objects of a class Database. 
Dependency Injection says that 'do not' instantiate an object of the class database in class A using the 'new' keyword.
Instead, we inject this object into A. 

Dependency Inversion Principle
We create an interface that implements all the dependencies required by class A.  
And the class A, that uses all these dependencies, will now only depend on the interface. 

Now, we need to figure out how to instantiate the class A. Before that we need to figure out how to instantiate its dependencies. 

Solution: Dependency Injection Container (DIC)

Structure [Describe which class has what dependencies]:
class1 -> array("Dependency 1", "Dependency 2")
class2 -> array("Dependency 2")

getDependency() -> <Find Dependency> 
Map will figure out which dependencies are required. 

Say we are instantiating class1, DIC will check if its dependencies are loaded? If they are, they are simply returned as is, else, they are instantiated, stored and then returned. 

Now, when you create an object of a class, say class1, the DIC will resolve the dependencies, contruct the object for class1 and then return it you. Its does this transparently. 

