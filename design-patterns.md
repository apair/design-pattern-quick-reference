# Design Patterns 
* Design patterns tend to favor composition over inheritance. 
* You use composition when your object contains other objects instead of inheriting from them.

## The Mediator Pattern
* When you use a mediator, you’re encapsulating the interaction between objects.
* When you use a mediator, you’re encapsulating the interaction between objects.
* You can use a mediator here to encapsulate all the navigation code out of the
separate pages and place it into a mediator object instead. From then on,
each page just has to report any change of state to the mediator, and the
mediator knows what page to send the user to.
* The Mediator object should inject to each object.

Mediator

***Without***

* Client1: Hey Taxi1, take me somewhere.
* Client2: Hey Taxi1, take me somewhere.
* Client1: Hey Taxi2, take me somewhere.
* Client2: Hey Taxi2, take me somewhere.

***With***

* Client1: Hey TaxiCenter, please take me a Taxi.
* Client2: Hey TaxiCenter, please take me a Taxi.

* [Event Dispatcher example](http://phpbeginnertoadvanced.blogspot.com/2016/05/explaining-mediator-pattern-to-myself.html)

## The Adapter Pattern
* names -> firstName,lastName
* Adapter acts as a wrapper between two objects, It catches calls for one object and transforms them to format and interface recognizable by the second object.[(Mail, Slack, SlackNotification)](https://refactoring.guru/design-patterns/adapter/php/example)
* This design pattern is particularly good when you’re working with legacy code that can’t be changed
* You can inherit from target class or in betterway create new class and implement target interface.( you should favor composition over inheritance.)

## The Facades Pattern
* To Print : turn of printer,call warm up method,call check ink method, call  check paper method...
* The Adapter pattern adapts code to work with other code. But the Facade pattern
gives you a wrapper that makes the original code easier to deal with.
* Often, you use the Facade pattern when you’re dealing with poorly encapsulated code. 

## The Proxy Pattern

* The most common applications of the Proxy pattern are lazy loading, caching, controlling the access, logging, etc. 
* A Proxy object can perform one of those things and then, depending on the result, pass the execution to the same method in a linked RealSubject object.
* So client calls the proxy object as call the real subject object.

## The Observer Pattern
* The Pattern should “Define a one-to-many dependency between objects so that when one object changes state, all its dependents are notified and updated automatically.”
* The Observer pattern provides a way to subscribe and unsubscribe to and from these events for any object that implements a subscriber interface.
*  PHP has several built-in interfaces (SplSubject, SplObserver) that can be used to make your implementations of the Observer pattern compatible with the rest of the PHP code.

***Without***

* Client1: Hey Subject, when do you change?
* Client2: When did you change Subject? I have not noticed!
* Client3: I know that Subject has changed.

***With***

* Clients are silent.
* Sometime later ...
* Subject: Dear clients, I have changed!

## Strategy Pattern
* This design principle comes into play when it makes sense to extract code that handles specific tasks from your app.
* Creating a family of algorithms lets you choose your strategy by choosing consciously which algorithm(s) you want to work with. 
* This design pattern is often used as an alternative to inheritance, where you can end up spreading out the way you handle one specific task over many class files
* Consider using the Strategy design pattern if you have one of the following situations:
   * You have volatile code that you can separate out of your application for easy maintenance
   * You want to avoid muddling how you handle a task by having to split implementation code over several inherited classes.
   * You want to change the algorithm you use for a task at runtime.

## The Decorator pattern
* Burger -> Burger with Cheese -> Burger With Cheese and Onion ...
* It’s all about extending the functionality of a given class
* After you’ve
written a class, you can add decorators (additional classes) to extend that class; doing so means that you won’t have to keep modifying the original class’s code over and over again.
*  Instead of using external algorithms(Like the Strategy pattern), this design pattern is all about using wrapper code to extend your core code.
*  When you use wrapper code to extend your core functionality and you don’t need to modify that core functionality, you are essentially decorating the code.
* The decorator class and base class implement the same interface,(Computer and Computer Decorator). Other classes (Disk, CD, Monitor,...) extend decorator class with injecting (wrapping) interface.

## The Factory Method Pattern
* Oracle -> SQL server -> Mysql -> Secure Connection
* The idea is simply that you have an object that creates other objects. 
* You should derive all the objects your factory creates from the same base class or interface so that code that uses the objects it creates doesn’t have to be modified for each new object type.
*  The GoF way of doing things means that you define how factory methods should work and leave it up to subclasses to implement the actual factory.It means no longer does a single concrete factory object instantiate your objects — a set of subclasses does the work.
* You set the factory specification by creating an abstract class or interface that subclasses have to use, and they build the actual concrete factory that can create objects.

## The Chain of Responsibility Pattern
* JS Event bubbling -> which layer can handle it?
* This pattern is all about connecting objects in a chain of notification; as a notification travels down the chain, it’s handled by the first object that is set up to deal with the particular notification.
* one of the most famous examples of using this pattern in PHP is [HTTP Request Middleware](https://www.php-fig.org/psr/psr-15/) described in PSR-15.

## The Singleton Pattern
* You use the Singleton design pattern when you want to either restrict resource use (instead of creating numbers of large objects without limit) or when you have a sensitive object whose data shouldn’t be accessed by multiple instances (such as a registry).
* It implemented by restricting access to a class’s constructor(Make it *private*) and allowing objects to be created only with a utility method( like getInstance()), you’ve implemented the Singleton pattern.
* The is an alternative to Singletons that simply making all the methods and variables in a class static.

## The Flyweight Pattern
* Students -> average -> name
* It is all about restricting object creation, but this time it gives the rest of your code the feeling of multiple objects.
* Whenever you’ve got a large number of massive objects that are putting a strain on your application, the Flyweight pattern should pop into your mind.
* Instead of a set of full objects, you need only one configurable object.(It config in *for loop*)
* Drawbacks:
  * The main issue is that it can take some time to configure a flyweight object
  * you’re adding another layer of programming, which can make maintenance and extension harder.

##  The Template Method Pattern
* AutomotiveRobot & CookieRobot
* It lets subclasses redefine the steps involved in creating an object by overriding method.
* You use the Template Method design pattern when you’ve got an algorithm of several steps and you want to allow customization by subclasses.
*  Implement the steps in that algorithm as an overridable method calls in an abstract class, and let the subclasses override those steps as required.

## The Builder Pattern
* It add more flexibility with the creation process by separating the construction process out into its own object.
* Use the Builder design pattern when you want client code to have control over the construction process but want to be able to end up with different kinds of objects (each of which is built by a different type of builder).
* This pattern is similar to the Factory pattern, also one of the GoF patterns, but the Factory pattern can be more involved, and it centers on a single-step creation process, not a configurable sequence of steps, as here.
* Query Builder of Laravel is a good example of this pattern.

## The Iterator Pattern
* The Iterator pattern gives you a way of accessing the elements inside an object without having to know the internal details of that object.
* The PHP has a built-in [Iterator interface](http://php.net/manual/en/language.oop5.iterations.php) that can be used for building custom iterators compatible with the rest of the PHP code.
* In Java iterators follow the lead of the interface that defines three methods:next,hasNext,remove

## The Composite Pattern
* This is all about creating tree-like structures where the leaves in a structure can be treated in the same way as the branches.(which are substructures that can contain multiple leaves, as well as other branches)
* It fits in with the Iterator pattern.
* The simplest example would be applying the pattern to elements of the DOM tree.
* To implement the Composite pattern, the GoF suggests that you use an abstract class as the basis for both the leaves and branches in the tree. 

## The State Pattern
* tenant -> Fill application form ->if approve -> dispense key
* An object keeps track of its internal state and can change its behavior based on that state
* You use *Switch/Case* on each state on each method.
* A better way is to define each state as an object and put all methods on this object.
* State object change the status of an injected main object(that has these statuses)

## The Command Pattern
* It lets you package complex commands into a single object and supports undoable operations.
* The idea here is encapsulation. You’re encapsulating a set of complex actions, targeted at a particular target.(shutDownAsia,rebootAsia,...)
* There are two interfaces: Reciever(Asia, Euro, USA) and Command(execute,undo) and one Invoker class that run sets of commands.
* If there is only one execute method on Invoker you can ignore Invoker object.

## The Abstract Factory Pattern
* Sometimes, you might need more than one factory to create objects of a similar nature and this pattern become a handy.
* It describes a factory of factories, or,more properly thought of, an abstract specification for an actual object factory. 

## The Prototype Pattern
* page -> draft page
* The Prototype pattern says that when it takes a lot of resources, or a lot of code, to create an object, you should consider simply copying an existing object and customizing it instead.
*  PHP has built-in cloning support.

## The Bridge Pattern
* The inspiration here is that when you have an abstraction that can vary(remote), and that’s tied to an implementation that can also vary(car), you should decouple the two. 
* Decouple an abstraction from its implementation so that the two can vary independently.

## The Interpreter Pattern
* It’s all about putting together your own programming language, or handling an existing one, by creating an interpreter for that language.

## The Memento Pattern
* It allows making snapshots of an object’s state and restoring it in future.

## Visitor Pattern
* With the Visitor design pattern, you can add a new operation to a structure of objects, like a Composite structure, without changing the objects in the structure.

# [Portland Pattern Repository](http://c2.com) (Not GOF Pattern)

## The Circular(Ring) Buffer Pattern
* It’s perfect when one part of your code stores data and another part reads that data asynchronously. Makes very efficient use of memory.

## The Double Buffer Pattern
* The idea is that you use createImage to create an Image object compatible with a particular visual component in your application and draw in that Image object. When you want to flash the completed image onscreen, you can use a Graphics object’s drawImage method.

## The Recycle Bin Pattern
* The idea is that when you’re done with an object, you toss it into the recycle bin, and when you need an object of the same kind again, you can grab it out of the recycle bin.

## MVC Pattern
* Model: The model doesn’t know anything about the view or the controller — you just pass it data and it goes from there, returning its results.
* View: Implements the presentation layer that interacts with the user.
* Controller: Acts as the boss of the application and is responsible for routing data to the right model and view components.
* A triad of three modules linked by the ObserverPattern.Controller observe model and view.

# Create Your Own Pattern
## The Rules Of Three
* A pattern has to be used in at least three real-world applications before it can be considered for true pattern hood. 

## Pattern Catalog Style
* The best way to start anything is with a guide of some kind, and for design patterns, that guide is the pattern catalog style. 
* All 23 GOF Patterns use this styles to intruduced patterns.
1. Intent (Short description)
2. Motivation (long description)
3. Applicability (General Scenario)
4. Structure (Diagram)
5. Participants (List of Interface and Objects)
6. Collaborations (Objects Relations)
7. Consequences (Usage Cons,Drawbacks)
8. Implementation/Sample Code
9. Known Uses (Realword Example)
10. Related Patterns 


