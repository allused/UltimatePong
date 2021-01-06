# General enterprise questions

## Software engineering

### Architectures

#### What is n-tier (or multi-tier) architecture?

	N-tier architecture is also called multi-tier architecture because the software is engineered to have the
	processing, data management, and presentation functions physically and logically separated.

#### What are microservices? Advantages and disadvantages?

	Microservices help build an application as a suite of small services, each running on it's own process
	and are independently deployable.

	Pros: 
		- Gives the freedom to independently develop/deployservices
		- Doesn't require a big team for developing
		- Code for different services can be writen in different languages
		- Easy to understand and modify for developers
		- Easy to scale, no long term commitment to technology stack
		- Better fault isolation: if one microservice fail the other continue to work

	Cons:
		- Developers have to deal with the complexity of distributed system
		- When number of services increase, intergration and managing whole product become complicated
		- Developers have to put additional effort into implement the communication between the services

#### What is Separation of Concerns?

	It is a design principle for separating a program into different sections addresses to a separate concerns.
	It helps you to focus on smaller parts of the program instead of the program in whole.
	It helps you make it modular and more testable, and makes it easier to maintain by it.

#### What is a layered design and why is it important in enterprise applications?

	Layered architecture pattern (n-tier)
	It is important because the modularity of the program, so the presentation layer should not depend on 
	the data or business layer, it should take care only about representing a given data regardless of the 
	data. It makes easier to implement new features, also makes it easier to maintain because the different 
	layers are separated, and easier to test the different parts. Also separating layers is necessary for security
	reasons, so different layers developers can not change implementation in other layers.

#### What is Dependency Injection?

	Dependency injection purpose is to make the classes independent from each other(avoid cross dependency)
	by "injecting" the needed class via dependency injection, by this you make your code more modular and much
	easier to maintain and test. 
	
	Because for example: 	Instead you declare a dependent class in the other class
				and make it dependent from that class, you remove the instantination from the method
				where you would use, and give in as a parameter.

#### What is the DAO pattern? When and how to implement?

	Data Access Object pattern is used to separate low level data accessing API or operations from high level business
	service.
	When to use : When in a larger project we want to reach a clean separation of concern, when we want to change our 
			current DB

	How to: 1.: Create a DAO interface, where we will define what methods we will need in the given class (for example: add,update,delete)
		2.: Create a DAO implementation class where we use the DAO interface, and implement the given methods.
		3.: When we use the DAO we give the DAO interface as reference and for the objects you give the DAO impl. like: IProdDao products = new ProdDao() 

#### What is SOA? When to use?

### Testing
#### What are unit test, integration test, system test, regression test, acceptance test? What is the major difference between these?
#### What is code coverage? Why is it used? How you can measure?

	Code coverege measurment of how many lines/blocks of your code are executed while the tests runs.
	It is calculated from the gaps where code is not tested.
	To give you a better overall view about how much of percent your code is "covered" with tests.
	/ Although it does not represent how good is your tests /

#### What does mocking mean? How would you do it 'manually' (i. e. without using any fancy framework)?

	Mocking means when we "mock" a given method behaviour and test if we got our predefined desired result.
	Without anything, I would create the method manually what you will give to the tested class as dependency.

#### What is a test case? What is an assertion? Give examples!

	The assertion is a condition, which determines what conditions should the test case meet to fail or pass a test.
	Test cases are the different types of inputs to your code to test your defined logic and produce the output.

#### What is TDD? What are the benefits?

	Test Driven Developemnt is a development approach in which test cases are developed
	to specify and validate what the code will do. Test cases created for each functionality and tested first,
	if the tests fail the new code is written in order to pass the tests.


#### What are the unit testing best practices? (Eg. how many assertion should a test case contain?)

	Use with CI - for example run your tests at every commit, so it doesn't get forgotten.
	Tests are written during development(TDD)
	Use test naming conventions
	Test the public interface
	Test should contain only one assertion
	Group test are coupled into subclasses

#### What is arrange/act/assert pattern?

	It suggests that you should divide your test methods into three sections: arrange, act, assert.
	Each one of them only responsible for the part which they are named after.

### DevOps
#### What is continuous integration? Why is CI important?

	Continuous integration is a software development practice of regularly integrating code changes into a shared code repository.
	Typically this would happesn at least once or several times a day, and encourages atomic commits.
	Each commit triggers a build during which tests are run that help to identify if anything was broken by the changes.

#### Why are tests important in the CI workflow?

	So the developers gets immediate feedbacks after their commits, so they will know which commit caused problem.

#### Name some software that help the CI workflow!

	Jenkins, Travis, Team city

#### What is Continuous Delivery?

	Continuous delivery is the ability to continuously deliver integrated code to prodcution.
	It means that if the commited changes pass the tests, they should be realeased.

#### What is Continuous Deployment?

	CD allows you to automatically deploy live every main branch change that passes the CI

#### What is DevOps?

	DevOps is the practice of operations and development engineers participating together
	in the entire service lifecycle, from design through the development process to production.


### Software Methodologies
#### What kind of software-lifecycle models do you know?

	software development life cycle: Plan -> Design -> implement -> Test -> Deploy -> Maintain

#### What is a UML diagram? What kind of diagram types do you know?

	Unified Modeling Language with the purpose of visually representing a system along with it's main actors,roles
	actions, classes, in order to better understand, alter, maintain or document information about the system.

#### What is a UML class diagram? What are the typical elements?

	Same as UML diagram, but it's used to represent OOP implementation, so you will work with oo elements.
	typical elements: class, methods, variables, interfaces, enums, connections between these(and what type of connection), package

#### What kind of design patterns do you know? Bring at least 3 examples.
		
	Creational pattern:
	Singleton: This design pattern means when you instantiate a class just once, and use that object from that point.
	
	Factory method: In factory pattern we create object without exposing the creation logic to the client and refer
			to newly created object using a common interface.     https://www.tutorialspoint.com/design_pattern/factory_pattern.htm
	Structural:
	Adapter: This is a special object that converts the interface of one object so that another object can understand it.
		https://refactoring.guru/design-patterns/adapter

#### What is the purpose of the Iterator Pattern?

	Iterator pattern is a behavioral pattern that let's you traverse elements of a collection without exposing
	it's underlying representation(list,stack,tree,etc.)
	https://refactoring.guru/design-patterns/iterator

#### What do you know about the SOLID principles?

	Single Responsibility principle: A class should have only a single responsibility, that is only changes one part of the software's specification.

	Open-closed principle: Objects or entities should br open for extension but closed for modification.

	Liskov substitution principle: Objects in a program should be replacable with instances of their subtypes without altering the correctness of that program.

	Interface segregation principle: Many client specific interfaces are better than one general purpose interface.

	Dependency inversion - High level modules should not be dependent of low level modules, both should depend on abstraction
 

#### How would you separate data storage code and business logic code (which uses stored data) in an application?

	If data storage code mean the code what handles the db and connections, You can use packaging or namespace in c#, different classes.

## Computer science

### Data Structures
#### What is the difference between Stack and Queue data structure?

	Stack: 
		- LIFO - last in first out
		- push(), pop() removes the recently added item
		- insertion takes places at the same end
		- only one pointer

	Queue: 
		- FIFO- first in first out
		- The object which added first can only be removed from the queue
    		- Enqueue adds items to the read and dequeue removes items from the front
    		- Two pointers


#### What is a graph? What are simple graphs? What are directed graphs? What are weighted graphs?
#### What are trees? What are binary trees? What are binary search trees?
#### How can you store graphs in programs? What are the advantages/disadvantages per each?
#### What are graph traversal algorithms? What is BFS, how does it work? What is DFS, how does it work?
#### How does dictionary work?
#### Why is it important for keys in a hashmap to have an immutable type? (Consider string for example.)

### Algorithms
#### What is QuickSort? Describe the main logic of this sorting algorithm.

## Software design

### Security

#### What is OAuth2?

	OAuth 2.0 is the industry-standard protocol for authorization.It focuses on client developer
	simplicity while providing specific authorization flows for web allplications, desktop applications,
	mobile phones, and living room devices.

#### What is Basic Authentication?

	In a basic HTTP authentication , a request contains a header field in the form of
	Authorization: Basic <credentials> - where credentials is the Base64 encoding of ID and Password joined
	by a single colon

#### What is CORS, why it’s needed in browsers?

	Cross Origin Resource Sharing: It is a http header based mechanism that allows a server to indicate any other
	origins than it's own from which a browser should permit loading of resources.
	It realies on a mechanism by which browsers make a prefilght request to the server hosting the cross-origin resource, in order
	to check that the server will permit the actual request.

#### How can you initialize a CSRF attack?

	First you have to forge a request as a link to do something you want,
	then you send it to a user from the site you are trying to reach (as a link) who is probably logged in to the site,
	then the visitor clicks the link and if you are lucky and your request is right it will succeed. 
	
#### What is JWT used for? Where to store it on client side?

### Threaded programming

#### When do you need to use threads in an application?
#### What is a daemon thread?
#### What is the difference between concurrent and parallel execution of code?
#### What is the most important problem developers are faced when using threads?
#### In what kind of situations can deadlocks occur?
#### What are possible ways to prevent deadlocks from occurring?
#### What does critical section or critical region mean in the context of concurrent programming?
