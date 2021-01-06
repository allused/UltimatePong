# OOP questions

## Software design

### Error handling

#### What does 'fail fast' mean in terms of exception handling? Why is it a good practice?

## Computer Science

### Data structures

#### How to find the middle element of singly linked list in O(n)?


#### Given an array of integers going from 1 to 100 (both inclusive) there is a duplicated entry. How to find it?
-Create a HashSet
-Add array elements to HashSet
 -before add new element check if it contains
  -if yes return the value

	Set<Integer>hashSet=new HashSet<>();
	for(int i:array){
		if (hashSet.contains(i)) return i;
		hashSet.add(i);	
	}

#### What is a linked list? How to find if a linked list has a loop?
We could add the Nodes next to a Set and before we add it, we check if the Set contains the Node, if yes it has a loop.

#### What is the Big O time complexity of the common operations in an ArrayList, LinkedList, HashMap? And of a bubble sort, quicksort, finding items in a Binary Search tree?

	!! TODO !!

#### How does HashMap work?

	HashMap implements Map.

	It takes K key V values pairs, and store them as nodes in a Map.

	Each node has these attributes: key,hashedKey,value,nextNode<K,V>

	How put works:

		First it takes the given key and hash it /with hashCode()/.

		Then it takes a result hash code and makes a bitwise calculation to give the node an index, 
		where it will be stored.

		If there is already a node on the give index, then it connects the two as  LinkedList, so the previous node nextNode
		will point to the new node.

	How get works:
		
		It takes the give key, hash it, make the bitwise calculation from the result hash.

		Then it goes to the result index, and start with the first node, compare the result hash with the node hash code.

		If it matches it compare the given key with the node key, if it matches too it returns the node value.

#### Why is it important for keys in a map to have an immutable type? (Consider String for example.)
	-TODO

	Because even the smallest change could lead to a different calculated bitwise index, and we will never find out stored value. 

### Other

#### What is a garbage collector, in a nutshell?
	
	In a nutshell it disengage a lot of memory by destroying unreachable objects.

## Programming paradigms

### Procedural

#### What is casting? What is the difference between up vs downcasting?

	Basicly casting is when we take one type of Object and turn it into another type of Object.
	
	Downcasting:
		
		Downcasting is when we cast an Object to a more specific type of Object.
			example: 
				Object text = "plain text";
				String plainText = (String) text;
	Upcasting:
		Upcasting is when we cast a specified type Object to a more generic type of Object.
			example:
				String plainText = "plain text";
				Object  text = (Object) plainText;


#### Which order should we catch the exceptions? Why?

	When we catch exceptions we should always catch the more specific exceptions and then the more generic ones,
	so it's the best to catch the children exceptions first then the parent exceptions.

	This practice allow us to get more specified Error messages, so we get a better picture about what caused the error.

### Object-oriented

#### What is a class?

	A Class is like an object constructor, or a "blueprint" for creating objects.
 	A class is the blueprint from which individual objects are created.
	

#### What is an object?

	In Java, an object is created from a class. If we create a class which has contstructor,  we can use this to create objects.
	An object have methods, and fields.

#### What is a constructor?

	A constructor is the part of the class which set the fields for the instance what created from the class.

#### Do we require parameter for constructors?

	It depends, we can give existing values for the constructor, or get the values from a method, or we can pass the 	values to the constructors as parameters.

#### What is an interface?

	In the most common form, interface is a group of related methods, with empty body.

	Implementing an interface allows a class to become more formal about the behaviour it promises to provide.

	If your class claims to implement an interface, all methods defined by that interface must appear in its source 	code, vefore the class will successfully compile

#### What are access modifiers?

	There are two type of modifiers in Java access modifiers and non-acces modifiers.
		
		The access modifiers in Java specifies the accessability or scope of a field, method, constructor or class.
		We can change the access level of the above by applying the access modifier on it.
		
		Java also provides non-access modifiers to achieve more functionality. 
		
		Access modifiers:
			
			-Private: It means you can not access it outside of the class.

			-Default: It means you can not access it outside of the package, if you don't set access modifier,
					it will be default.

			-Protected: It means you can not acccess it outside of the package only with child class, if you 						don't make a child class, you can not access it from outside of the package.

			-Public: Basically you can access it from everywhere.


		Non-access modifiers:
			
			-Static: This keyword used to create variables, methodss that will exist independently.

			-Final: The final modifier is for finalizing the implementation of classes, methods and variables.
				If a class is declared final it means other class can not inherit any feature from it.

			-Abstract: An abstract class can never be instantiated. If a class is declared as abstract then 					the purpose of the class is to be extended.

					The abstract mehod is a method declared without any implementation, the methods
					implementation is provided by the sub class.

			-Synchronized: The synchronized keyword used to indicate that a method can be accessed by only one 						thread at a time.
		

#### What is data hiding?

	The main purpose of data hiding or Encapsulation is to hide those fields which are not neccessary for being seen 		from outside of the package, or atleat modify. To reach encapsulation you have to declare every field private 		inside of a class and if you would like to know their values or modify, you make getter, setter methods. 

#### Can a static method use non-static members?

	A static method can access non-static methods and fields of any instance it knows of. However, it cannot access 	anything non-static if it doesn't know which instance to operate on. So it can use  non-static member if it knows 		the instance, if it doesn't it can not use, even if it's declared in the same class.

#### What is the difference between hiding a static method and overriding an instance method?

	Overriding is for non-static methods, it supports late binding, therefore it's decided at run time which method
	will be called.

	Hiding is for all other members (static methods, instance members, static members).
	It is based on early binding, the method or member to be called or used is decided during compile.

#### Define the following terms: Instantiation, Attribute, Method

	Instantiation: Is a term for creating new instance of object.

	Attribute:  An attribute with another term is a field, typically a public constatnt or a public variable, that can 				be accessed directly.

	Method: Method is a block of code, which only runs when it's called. 

#### Could we access a static variable (or method) from a non-static method? Why?

	Yes we can, because they can be reached independently even without that class instance, and they are also private, 		which means you can reach them everywhere.

#### Could we access a non-static variable (or method) from a static method? Why?

	We could, if the static method knows the non-static variable or method instance, without it it can not access it.
	Because for example:

		Public class Test{
		private int num = 42;

		public static shout(){

			System.out.println(num)
                      }
				}
	In the case above it will cause an error, the method is in the class, but it can not use the variable, because
	it doesn't know exactly to which object variable we would like use. The static method is independent from the current class.


#### How many instances you have of a static variable of a given class?

	Only one, when you declare a static variable in java, and set it to a value, every instances static variable will refer to that value.

#### Why is it not a good practice to write a lot of static methods?

	Because java oop would be less oop, the strength of oop that everything is an object and that we create instances from an object
	and then we can use its methods. Static methods doesn't realy fit into inheritance, also they can not be overriden.

#### What are the features of static attributes and static methods of a class? What are the benefits, when to use them?

	Features of static fields: You can reach them without instancing the actual class, they are not hiden, so you don't need a getter to 						reach them.

		Benefits of static attributes: You can save space by making a cons static, so all your sub class cons will refer to one memory 							address, you don't have to instantiation to reach it.

	Features of static methods: The same with the fields, you don't need to create an instance from the class where it is to use the 						actual method, you can use it independently.

		Benefits of static methods: You can use the methods independently, without making an instance from the class, mostly used in 							Utils classes.

#### What is the ‘this’ reference?

	"this" is a reference variable, it refers to the current object.

#### What are base class, subclass and superclass?

	Base class: It is a class from which other classes are derived.It facilitates the creation of other classes that 				can reuse the code implicitly inherited from the base class (except constructors,destructors).

	Subclass: It is class what extends another class a Superclass, it inherits all it's methods,variables and nested 				classes.

	Superclass: It a class which is extended by other classes.It can be used to when other classes would have the same 				fields or methods, and instead of every one of them implementing it, they just extend the super 			class, saving a lot of code.

#### Draw an object oriented family (as entities, with relations) on the whiteboard.



#### Difference between overloading and overriding?
	
	When we overloading a method we just create that method again with different parameters, it is used to use the same method with more 			parameters or with different type of parameters, when we overriding a method we are about to override it just once and use it 			instead of the existing method with a different implementation.

#### What are the Object Oriented Principles? Explain the concepts with realistic examples!

	Inheritance: 

	Polymorphism:

	Abstraction:

	Encapsulation: 

#### What is method overloading?

	Overloading: We use overloading when we create the same methods, but with different parameters, like Java Lists have add() method, 
		     But when you type add(), there is a lot of add() method to choose from, depends what type of variable you would like
		     to pass to the method.

#### What is method overriding?

	Overriding: Overriding a method is useful when there is already a method with the same name, but we want to make sure, when we use
		    that object we want to use our implementation of that method. A great example is the toString() method.

#### Explain how object oriented languages attempt to simplify memory management for Programmers.

				TODO

#### Explain the “Single Responsibility” principle!

	It states that each class should have one single responsibility or purpose.
	By this we escape object which has unreleated behaciour.

#### What is an object oriented program? Explain, show.

		TODO

#### How do you make a class immutable? What do you need to watch out for?
	
	-Declare every field private, don't create setter methods for them.

	-Declare the class final, so it can't be extended.

	-Make the mutable fields final, so they can't be changed after they are set.

	-Initialize all fields in the constructor performing deep copy.

	-Perform cloning in the getters, so you return a copy rather than a reference

		Look out for: Use deep copy in the constructor instead of shallow copy, because for example if you are using HashMap its 			values can change if you are using shallowcopy.

#### How many instances can be created for an abstract class?

	Z E R O - abstract means that it can not be instantiated, abstract marks that the class is for extending. 

## Programming languages

### Java

#### What is autoboxing and unboxing?

	Autoboxing is when Java automatically convert a primitive type to generics.
	Unboxing is when Java automatically convert generics type to a primitive type.

#### If you have a variable, that shall store a positive whole number between 0 and 200, what primitive type would you use to store it?

	I would choose short, because only byte under short, and byte can store only between -127 and 127, short can store 		between  -32.768 and 32.768, and takes less memory than the other primitive types which can store even bigger number.	

#### What is the "golden rule" of variable scoping in Java? What is the lifetime of variables?

	There is four scope in Java: 
		
		Class scope: Every variables is declared inside of a class brackets, with private access modifier but outside 			of any method has class scope, these variables can be used everywhere inside of a class but not outside of it.
		
		Metthod scope: When a variable is declared inside of a method, it has a method scope, it can't be used outside 			of the method.

		Loop scope: When we declarea variable inside of a loop, it can be reached only inside of the loop.

		Bracket scope: We can also declare additional brackets, and if we declare variables inside of that bracket
		that variable can be used only inside of that bracket.  

#### What is the purpose of the ‘equals()’ method?

	The purpose of equals() is to compare objects.

#### What is the difference between '==' and 'equals()'?

	The difference is : "==" is an operator and "equals()" is a method.
			    "==" is comparing the object reference and "equals()" compare the object content

#### What does the ‘static’ keyword mean?

	Static keyword is a non-access modifier which can be used to reach a variable or a method independently, also has been used to achieve better memory management since it gets memory only once, when the class is loading and from that point other instances will point to that memory address.

#### Why is the main() method declared as static? Explain.

	Main is static so you can reach it from anywhere, and it has to be static so the program can call it on startup without instantiation .

#### What is the default access modifier in a class?

	By default java set package private or default access modifiert, so it can be reached from inside of the package.

#### What is the JVM?

	JVM is Java Virtual Machine, it is a specification that provides runtime enviroment. It translates the compiled bytecode into machine code in the ram, it calls the class loader then the byte code verifier then the execute engine which turn the byte code into machine code /just in time compiling/ thats why java slow

#### What is the difference between the JRE and the JDK?

	JDK: Java Development Kit is a software development environment used for developing Java applicatons and applets.
	     It includes JRE, an interpreter/loader (Java), a compiler (javac) an archiver(jar), a documentation generator(javadoc) and othertools neededin java development.


	JRE: Java Runtime Environment provides the minimum requirments for executing a java application, it consist of JVM, core classes and supporting files.

#### What is the difference between long and Long?

	The difference is,that long is primitive type(only contains a number) and Long is generics, means long is wrapped with a wrapper class, which provide wider usage by it's methods.

#### Can a long store bigger numbers than a Long?

	No.

#### What kind of packages do you know under java.util.* ? Bring at least 3 examples.

	List,HashSet,Set,Date,ArrayList

#### What are the access modifiers in Java? Which one could we use for class?

	The four access modifiers in java: Private,Default,Protected,Public
	For a "normal class" you can use default(by not using any, so it will be default by default) and public.

		For inner classes you may use private and protected too.

#### Can an “enum” contain methods in Java? Explain.

	Yes it can, because for example if you pair values to the enums you need a method like value() to return the given enum 	value.

#### When would you use a private/protected/public attribute? What is the difference?

	Private - I would use private when other classes shouldn't directly be able to access a field or an inner class, or when I would like to break up a public method to smaller parts, and make a private method for it, so others won't use it, because they don't see it, so I can change the public method if I want even without that private method without worrying about it would affect others.

	Protected - Mostly I would use for fields, it's great because basicly others can't see it from outside of the package, but It can be seen when the class instantiated outside of the package

	Public - Basicly for classes, and methods inside of classes, so other classes can use the methods, and see the class from anywhere.

#### How do you prevent developers from subclassing a class?

	You can use the "final" keyword when making a class, it means it's not extendable.

#### How do you prevent developers from overriding a method in a subclass?

	By using the "final" keyword you make a method unoverrideable.

#### How do you prevent developers from changing the value of a variable?

	Using the "final" keyword, so by this after declaration you can't change it's value.

#### Think about money ;) How would you store a currency value, that shall support decimal parts? Think it through again, and try to think outside of the box!

	TODO	

#### What happens if you try to call something, that you have no access to, because of data hiding?

	Nothing, probably IntellIj will show that can not find the method or the given variable, so you have to declare it to use it/ "Can not resolve method/symbol"/

#### What happens if you try to delete/drop an item from an array, while you are iterating over it?

	You can't just simply drop or delete an element from an array while iterating over it, because simple arrays doesn't have methods, so you can't delete or drop an element from it, if you want to add or remove from the array, you have to create a new array and fill that with the previous one and add more or add less elements to it.

#### What happens if you try to delete/drop/add an item from a List, while you are iterating over it?

	You can add or remove element from a List while iterating over it without getting any exceptions, but if you would like to remove or drop the item which actually is the iterator it will cause IndexOutOfBounds exceptions, because the indexing will change while 

#### What happens if you try to add an item to the end of an array, while you are iterating over it?

	TODO

#### If you need to access the iterator variable after a for loop, how would you do it?

	I would create a variable outside of the loop and save the actual iterator by making it equal with the iterator.

#### Which interfaces extend the Collection interface in Java. Which classes?

	Directly List,Set and Queue extends the Collection interface.

#### What is the connection between equals() and hashCode()? How are they used in HashMap?

	The connection:  If we use equals(Object o) and it returns true, then calling hashCode() on those two objects should return the same number.
	
	Usage in Hashmap: As I mentioned before hashCode() is used to hash the given key, equals() is used when you want to use get() method of HashMap, first it checks if the both key hash is the same, if it is it uses the equals() method to compare the two object, and if that's true, then return the object.

#### What is the difference between checked exceptions and unchecked exceptions? Could you bring example for each?

	Checked exceptions - Checked exceptions are the type of exceptions which are checked compile time, if a method contain a checked exception the method must use a try catch block or throw an exception, show in the method signature with "throws".
		-IOException

	Unchecked exceptions - Unchecked exceptions are not checked compile time, so you can run your code without handle or specify the given exception, Error and RuntimeException classes belongs to unchecked exceptions.
		-IndexOutOfBoundsException 

#### What is Error in Java and how does it relate to Exception?

	Error indicates a serious problem while the application running what the program should not try to catch.
	They are both sub-classes of java.lang.
	Errors can not recovered by any handling technic and surely cause the termination of the program abnormally.
		Examples:Out of memory error, Cache error

#### When does 'finally' block run? What it is used for? Could you give an example from your projects when you would use 'finally'?

	Finally block always run after the try block, regardless of what happe in the try block.
	You can use for example clean up codes, so if you open a Writer or handling files, finally block is the best place to close them and prevent memory leaks, beause as I mentioned above, it will get executed regardless what happens in the try block.

#### What is the largest number you can work with in Java?

	Double.POSITIVE_INFINITY is the biggest number compared to other primitives.

#### When you use method overriding, can you change the access level of the method, from protected to public? Why?When you use method overriding, can you change the access level of the method, from public to protected? Why?

	TODO

#### Can the main method be overridden? Explain your answer!

	You can override static methods, but since there is no polymorphism at runtime, so you can't reach polymorphism and since the main method have to be static, you can not override it and reach polymorphism.

#### When you use method overriding, can you throw fewer exceptions in the subclass than in the parent class? Why?

	no, because you

#### When you use method overriding, can you throw more exceptions in the subclass than in the parent class? Why?

	no, because you can not throw more exceptions than 

#### What does "final" mean in case of a variable, method or a class?

	Variable: After it's declared and initialized with value, it can not be changed.
	
	Method: If you decalare a method final it means you can not override it in the subclasses.

	Class: If a class is final it means it can not be extended.

#### What is the super keyword?

	Super keyword is a reference to the immediate parent class object.
		
		- super can be used to refer immediate parent class instance variable
		- super can be used to invoke immediate parent class method
		- super() can be used to invoke immmediate parent class constructor

#### What are “generics”? When to use? Show examples.

	List<T> is a generics type, so it mea

#### What is the benefit of having “generic” containers?

	So we have much more built in methods for them, so we can save a lot of code by using the methods, declared in the genereics  class.

#### Given two Java programs on two different machines. How can you communicate between the two? What are the possible ways?

	TODO

#### What is an annotation? What can be annotated and how? Show examples.

	TODO

### C&#35;

#### Explain the purpose of IL and how does it relate to CLR?

	IL: Intermediate Language 
		IL code is a CPU independent partially compiled code,
		partially compiled because we do not know in what kind of env. .NET will run
		on runtime. IL code will compile to machine code using the env. properties(CPU,OS,machine configuration, etc.)

	CLR: Common Language Runtime
		CLR manages the execution of code and provides different services
		like:Garbage collection, Code Access Security, Code Verification, IL to Native code translation
	
	CLR translates the IL code to native code with the metadata IL provides. 


#### What does “managed code” mean?

	Managed code is the code whose execution is managed by a runtime.
	In our case it's CLR. It's called managed because CLR provide services like automatic memory management,
	security boundaries, type safety etc.
	So we do not have to "take care" about these like in compare with C/C++ where you would run unmanaged code,
	where you have to manage all of these things by yourself.

#### What is an assembly?

	Assemblies form the fundamental units of deployment, version control, reuse, activation scoping,
	and security permissions for .NET-based applications. 

#### What is the difference between an EXE and a DLL?

	EXE: Executable
		-Can run on it's own
		-Can be shared with other applications
		-Application contains ONE exe
		-There is an entry point
		-It has main 

	DLL: Dynamic link library
		-Can not run on it's own, it's linked or refecenced to an exe at run time
		-Can be shared with other applications
		-Application may contain as many dll as many needed
		-There is no entry point
		-It doesn't has main

#### What is strong-typing versus weak-typing? Which is preferred? Why?

	A strongly typed language has stricter typing rules at compile time, so errors and exceptions are more likely
	to happen during compilation.

	A weakly typed language has looser typing rules and may produce undpredictable results or may perform implicit type conversion at runtime.

	It is easier and may be a little quicker to write code in a weakly typed language( like Python) because you do not have to take care about
	return types, but because this it can cause confusion if you are looking at someones code (it may be unclear what type a method will reuturn for example).
	
	 

#### What is a namespace?

	A is used to organize larger project, also preventing name conflicts.

#### Explain sealed class in C#?

	Applying "sealed" modifier to a class, prevent it from inheriting. 

#### What is explicit vs. implicit conversion? Give examples of both of them.

	Implicit conversion: There is no special syntax required because the conversion always 
			     succeeds. For example smaller to larger integral types.(int to long)
	
	Explicitin conversion: It requires a cast expression (type)variable.Casting is required
				when information might be lost in the conversion or when the 
				conversion might not succeed for other reasons.(decimal to int)
	

#### Is a struct stored on the heap or stack?

	It depends, it could be stored on the stack and also the heap, structs mostly allocated on the stack
	because value types are allocated on the stack, but in several cases they can be allocated on the heap
	like if they are a variable in a class or elements of an array, so it depends on where they were declared.
	For example a variable 'int i=3' is declared in a function it will be stored in the stack and after the 
	function returned it's value it will gone, but if it's declared as a class variable it will be allocated in
	the heap, because it may need later and till it got a pointer refering to it, it will stay there.

#### Can a struct have methods?

	Yes it can contain related methods.

#### Can DateTimes be null?

	Since it's valu type, no it can not be null, only reference types are nullable.

#### List out the differences between Array and ArrayList in C#?

	Array:
		-do not have methods
		-fixed length (decided on declaration)
		-doesn not implement ICollection, IList, ICloneable
		

	ArrayList:
		-have methods
		-not fixed length, you can add or delete elements by Add(), Remove() methods
		-implement ICollection, IList, ICloneable

#### How is the using() pattern useful? What is IDisposable? How does it support deterministic finalization?

	Using statement becomes useful when we are working with unmanaged resources Streams for example.
	Using using() :) will close our resources without we have to worry about them, preventing memory leak etc.
	IDisposeable provide us a Dispose method which makes the clean ups for us.

#### How can you make sure that objects using dedicated resources (database connection, files, hardware, OS handle, etc.) are released as early as possible?

	T O D O !!!!!!!!!

#### Why to use keyword “const” in C#? Give an example.

	When you would like to use a constant, a variable which will not change in the future.
	A "const" may save you memory space, because only one copy of the variables is created 
	and shared among all objects.

#### What is the difference between “const” and “readonly” variables in C#?

	const: 
		-you must initialize upon declaration
		-initialized at compile time

	readonly:
		-you can initialize upon declaration or at the constructor 
		-initialized at compile time or runtime

#### What is a property in C#?

	Properties are a special methods, called "accessors".
	
	They behave like a private field even when they are public, they make the data 
	accessibility realy easy by the methods they provide.

	You can choose if you would like a setter or getter or both for these fields
	and after this you do not have to worry about setter/getter like in Java.
	

#### List out two different types of errors in C#?

	Syntax errors: They occurr when you make type mistake in code.

	Runtime errors: They occurr during execution of the program, they are also called exceptions.

#### What is the difference between “out” and “ref” parameters in C#?

	out:
		-do not have to initialize the parameter before passing to out
		-have to initialize the value of a parameter before returning to calling method
		-when it's used the data may pass in bi-directional

	ref:
		-have to initialize parameter before passing to ref
		-do not have to initialize the value of the parametor before returning to the calling method
		-when it's used the data only passed in unidirectional

#### Can we override private virtual method in C#?

	You should not using private virtual methods in the first place.
	But you can not override them.

#### What's the difference between IEquatable and just overriding Object.Equals()?

	There is no real difference, only in performance, because the Generic (IE) version
	do not use boxing/unboxing so it brings you better performance.

#### Explain the differences between public, protected, private and internal. Explain access modifier – “protected internal” in C#!

	public: you can access it from any class
	protected: you can access it only from the same class or the class what inherited from the super class
	private: you can access it only from the given class
	internal: you can access it only from the same assembly

	protected internal member is accessible from the current assembly or from types that are derived from the containing class.

#### What’s the difference between using `override` and `new` keywords when defining method in child class?

	Override: overriding indicates when you run that class method you want to use the last implementation of the method.

	New: new keyword is used, when you want to use the child class implementation of a method.	

#### Explain StringBuilder class in C#!

	StringBuilder class is for building a string ! You can create a stringbuilder instance and you can add or remove from it
	or even join string at a selected index.

#### How we can sort the array elements in descending order in C#?

	Array.Sort(array)
	Array.Reverse(array)

#### Can you use a value type as a generic type argument in C#? For example when implementing an interface like (IEquatable).
#### What are Nullable Types in C#?

	Reference types are nullable types, it means they can be null.

#### Conceptually, what is the difference between early-binding and late-binding?

	Binding means when an object is assigned to an object variable, early bindig refers
	to compile time binding, late binding refers to runtime binding.

#### What is delegate, event, callback, multicast delegate?

	T O D O !!!!!!!

#### What is enum in C#?

	Enum is a special class in which you basically store constans, which you 
	will have to use in multiple classes.

#### What is null-conditional operator?

	It's an operator which let's you perform a member or element access operation
	only if an operand is non-null

#### What is null-coalescing operator?

	It's a logical operator which return it's right side operand when it's left hand side
	operand is null or undefined, otherwise it returns it's left side operand.

#### What is serialization?

	Serialization is when you turn an object in memory to a stream of bytes, so you can
	store it on disk or send through network etc.

#### What is the difference between Finalize() and Dispose() methods?

	Dispose: 
		-called by user
		-belongs to IDsiposeable interface
		-no performance cost

	Finalize:	
		-called by Garbage Collector
		-belongs to Object class
		-there is performance cost because it does not clean the memory immediatly 
		 and called by GC

#### How do you inherit a class from another class in C#?

	public Class : fromClassName
	{
		//code
	}
	
	You have to type a double dot and after it the class name.

#### What is difference between “is” and “as” operators in C#?

	is: 
	   -boolean type
	   -can not be used for nullable conversions
	   -can be used for unboxing conversions
	   -used to check if the runtime type of an object is compatible with the given type
	   
	as:
	  -not boolean type
	  -can be used for nullable conversions
	  -can not be used for unboxing conversions
	  -used to perform conversion between compareable reference types or nullable types
	 

#### What are indexers in C# .NET?

	Indexers enable objects to be indexed in a similar way as arrays.

#### What is the difference between returning IQueryable<T> vs. IEnumerable<T>?

	IQueryable:
			-allows LINQ to SQL
			-the whole query will execute in database and then return the result
			-Where() accepts functions

	IEnumerable:
			-allows LINQ to Object
			-first the query matching all the object loaded into memory, then there
			 will does the rest like filtering etc.
			-Where() accepts expressions

#### What is LINQ? Explain the idea of extension methods.

	Extension method: Extension method enable to "add" a method to an existing type, without recompiling or otherwise modifying the orignal type.
			  Extension methods are static methods, but they are being called as instance methods on the extended type.
			  

	LINQ: Language Integrated Query is a way to use familiar queries like an sql query
		but these are performed on c# collections. It's integrated in c# and the query
		expressions are written in a declarative query syntax.LINQ is an extension method
		because it capable to add functionality to the existing IEnumerable and IEnumerable<T> types.


#### What are the advantages and disadvantages of lazy loading?

	Advantage: It could save us memory because we do not have to initialize unnecessary objects in the constructor
			but only when they are being accessed for the first time.

	Disadvantage: It may cause unnecessarry complexity in our code, if we use it in too much it may cause user latency,
			because the the later initializations.

#### How to use of “yield” keyword? Mention at least one practical scenario where it can be used?

	It helps to do custom stateful iteration over a collection.

	for example: yield return value

	If I were reading elements from a collection or database I could use "yield return value" and by this using this in an iteration it "remembers"
	where it stopped in an iteration, so when it returns the value it will not start again iterating through again because it remembers from where did it returned the last value,
	and it will continue from that point.


#### What are attributes in C#? Give some examples of usage of them.

	Attributes adds metadata to your program, and by this they can be querried by a techniq
	called reflection.

	One example of usage in .NET when creating a class to handle API requests, in that class we use it in three different way.
	1: [route(path)] - by this tell that that this is the basic route these requests will listen for.
	2: [ApiController] - by this we indicate to our program that this class is an API Controller 
	3: [POST/GET etc.] - by these we indicate that the method below this attribe will listen to that specfied hhtp request.
 
	Another example when we are making Tests, at the top of our test class we write [Test] and by this we indicate that this class is for testing.

	
#### By what mechanism does NUnit know what methods to test?

	Basically it doesn't know what method to test, we have call the desired method and check if the given result by it match our desired result.

#### What is the GAC? What problem does it solve?

	GAC - Global Assembly Cache, it is used to share assemblies between the several applications on the computer.
	When there is an assembly what we would like to use in different application, we can install it to GAC and use it in any application we want
	With GAC you can use more versions of the same assembly and by this you do not have to reference for an exact version, your application may get 
	the version it needs from GAC. Older version applications get the older version of the assembly and the newer versions get the newer version of the 
	assembly, because by gac you can have multiple versions of the same assambly.

#### What is the largest number you can work with in C#?

	2,147,483,647

### Database

#### How can you connect your application to a database server? What are the possible ways?
#### What do you know about database normalization?
