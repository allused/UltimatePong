# Enterprise module (C# branch)

### ASP.NET Core, WCF

#### What Is the difference between .NET Core and .NET Standard? How do them relate to “classic” .NET?

	.NET Core is an implementation of the managed framework, it has it's own set of Base Class Library (BCL)
	which contain exception handlig, base classes and collections.
	Every .NET implementation use BCL.

	.NET Standard is a specification for implementing the BCL.

	So all the .NET implementation like .NET Framework, .NET Core etc. implement .NET Strandard
	 for the BCL in their managed framework.

#### What is ASP.NET MVC?

	MVC - Model View Controller design pattern, it is used to decouple user interface, data model and application logic.

#### Can you explain Model, Controller and View in MVC?

	Model - In the model we declare the model classes which will be used in our web applications, also contains the logic to handle databases, services

	Controller - In the controller we handle the incoming requests, when a request arrives to the server, it decides if it need to get some data
			from the model layer, if it needs it gets the data, makes an instance of it, then it calls the view with the data to represent the 
			data towards user.

	View - In the view there is data independent representation classes, it's job to represent the data to the user.

#### Explain the page lifecycle of MVC.

	Routing
	URL Routing Module intercepts the Request
	MVC Handler Executes
	Controller Executes
	Render View Model called
	

#### What is Razor View Engine?

	Razor is a templating engine and ASP.NET MVChas implemented a view engine which allows us
	to use Razor inside of an MVC applicatoon to produce HTML.

#### What you mean by Routing in MVC?

	Routing enables us to define a URL pattern that maps to the request handler.
	This request handler can be a file or class.

#### What is Layout in MVC?

	A web application may contain specific UI elements which will remain the same throughtout the application.
	For example: header,navbar,footer
	
	The layout contains all these elements so we don't have to write the same code again in every page.

#### What ConfigureServices() method does in Startup.cs?

	In the ConfigureServices method we register the services what we would like to use in our application.
	Also the DI takes places here.

#### What Configure() method does in Startup.cs?

	Here we set the processing pipeline of our application.
	 We can set routing there, decide what files our application should use, add exception pages etc.
	These all are middlewares.

#### What is wwwroot folder in ASP.NET Core?

	wwwroot contains the local files what our application may use, like html,css,js and resources like pictures
	logos and everything our webapp may use.

#### What’s the usage of [InternalsVisibleTo] attribute? What are pros and cons of it?

	It makes a class visible to other specified assemmblies when normaly they could be reached only from the same assembly.
	
	pros: 
		-allows your test libraries to access internal classes and methods for additional testing and coverage 
		-provides greater flexibility for internal refactoring and backwards compatibility
		-reduces the surface area of your public API, keeps your API limited to what youwant to publish

	cons:
		-potential loss of encapsulation
		-two levels of "public" visibility that have to be managed
		-enforces bi-directional depenencies between assemblies		

#### Explain what is WCF?

	Windows Communication Foundation is a framework for building service oriented applications.
	You can send data as asynchronous messages from one service endpoint to another.
		for example:    - secure service to process business transactions
				- chat service that allows people to communicate or exchange data in real time

#### Mention what is the endpoint in WCF and what are the three major points in WCF?

	An endpoint can be a client of service that requests data from a service endpoint.

	Address - specifies the location of the service  like: http://server/service.clients
	Contract - Specifies the interface between client and the server, it's a simple interface with some attribute
	Binding - Specifies how the two paries will communicate in term of transport and encoding and protocols.
	

#### Object Relational Mapping, Entity Framework

	Object Relational Mapping  is a programming technique for converting data between incompatible type systems using object-oriented programming languages.
	It enables you to use the language of your choice and write your querries there, with that oo syntax.

	Entity Framework is an open source cross platform ORM Framework for .NET applications.

#### What is an ORM? What are benefits, when to use?

	Object-relational-mapping is the idea of being able to write queries like the one above, as well as much more complicated ones,
	 using the object-oriented paradigm of your preferred programming language.

	The benefits of this is that you can use your own language syntax to make querries, so you do not have to
	learn new sql language syntax.

	When you are not realy good in sql but you find an orm for the language you are working with, it can be a good choice
	for you to use orm instead of writing querries, because the querries whats in orm probably will be better than yours.


#### What is Entity Framework? What are the advantages, limitations?

	Entity Framework is an object-relational mapper (O/RM) that enables .NET developers to work with a database using .NET objects.
	It eliminates the need for most of the data-access code that developers usually need to write.

	You save a lot of code provided by entity framework

#### What is lazy loading?

	Lazy loading is when we do not inicialize everything in a class in the constructor, when something not essential
	in the running of the program, it can be initialized later, so with lazy loading these variables are being initialized
	when first accessed in the code.

#### What is the difference between code first and DB first approach?

	code first: In coe first approach we will create entity classes with properties defined in it.Entity Framework
			will create the db and tables based on the entitty classes defined. So database is generated from the code.
			You can create your db from your businessobjects, db version controll, good for small applications.

	db first: In this approach DB and tables are created first. Then you create entitty Data model using the created db.
		  Simple to create data model, mapping and creation of keys and relations are easy as you do not have to write any code.
		  Preferred for large applications.	

#### What is a migration script?

	Migration script handle the database connection code when you are using code first approach. (Under handle I mean it generates the code 
	which will make the connection to the bd and creates the db)

#### What is a navigation property?

	It is a way to represent a foreign key relationship in the database or define relationship between the two entities.

#### Name 3 different attributes used in EF Core, what can they do for you?