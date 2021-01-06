# Web with Python questions

## Software design

### Clean code

#### Point out 5 suggestions, how to format an SQL query!

Keywords should be uppercase.

Write your querry expressions in new line, so it will be easier to read.

If you have a column name which contain more than one word, use _ underline or
camelCasing to name it.

If you feel like your querry a bit complicated, and should be explained write a doc for it instead of using comments after every line.

#### What layers can you name in a simple web application?

The Viewer layer - interaction with the user, UI

Business logic layer - deals with the program logic

Data layer - controls the data retrieval from its sources

### Error handling
#### What error can occur, when an array does not have an element on the requested index?
It wil raise IndexOutOfBounds 

#### What is the “finally” block, and how would you use it?
Finally block will be executed after the try and except blocks regardless of their results.

#### Why should we catch special exception types?

To be able to give a wider feedback about exactly what error occured during the program running.

### Security
#### What is SQL injection? How to protect an application against it?

SQL injection is when an attacker “inject” harmful SQL statement via any type of user input, and by it gain access to sensitive informations/data or drop table/all tables.

Validation: It’s about control what we accept from the user side, like how long text a    field may contain or what type of characters the users may use.

Sanitizing Inputs: - Check that supplied fields like email addresses match a regular expression.
-Ensure that numeric or alphanumeric fields do not contain symbol characters.
-Reject (or strip) out whitespace and new line characters where they are not appropriate.



#### What is XSS? How to protect an application against it?

XSS attacks, in essence, trick an application into sending malicious script through the browser, which believes the script is coming from the trusted website. Each time an end user accesses the affected page, their browser will download and run the malicious script as if it was part of the page.

Escaping: -Escaping data means taking the data an application has received and ensuring it’s secure before rendering it for the end user. By escaping user input, key characters in the data received by a web page will be prevented from being interpreted in any malicious way. In essence, you’re censoring the data your web page receives in a way that will disallow the characters – especially < and > characters – from being rendered, which otherwise could cause harm to the application and/or users.

Validating Input: Validating input is the process of ensuring an application is rendering the correct data and preventing malicious data from doing harm to the site, database, and users. While whitelisting and input validation are more commonly associated with SQL injection, they can also be used as an additional method of prevention for XSS. Whereas blacklisting, or disallowing certain, predetermined characters in user input, disallows only known bad characters, whitelisting only allows known good characters and is a better method for preventing XSS attacks as well as others.

#### How to properly store passwords?
Passwords have to be hashed, then stored, and the database should only contain the hashed version of the passwords, so if someone unauthorized gain access to it, won’t be able to easily use it.

#### What is HTTPS?
HTTPS stands for Hyper Text Transfer Protocol Secure, it is a secure verison of HTTP which is the transfer protocol between the browsers and web servers, HTTPS encrypt the transfered data so it is safe to use even when sending sensitive informations.

#### What is encryption and decryption?
Encryption is to transform information into an unrecognizable form, it is entirely different from the original information, usually done by a key algorithm.

Decryption is to convert the decrypted form to a recognizable and readable form to humans/computers, this  could be done un-encrypting the text manually or using the same key which was used to encrypt the original data.

#### What is hashing?
Hashing is to turn any amount of data into a fixed-length "fingerprint" that cannot be reversed, and also have the property that if the input changes by even a tiny bit, the resulting hash is completely different.

#### What is the difference between encryption and hashing? When would you use which?
Encryption mostly used to secure data while transfering between “two points”.

Hashing is mostly used in digital signatures, storing sensitive data or compare big data, as it is easier to compare it’s hash then the data itself.

#### What encryption methods do you know?

Symmetric encryption: Symmetric encryption uses a single key to encrypt as well as decrypt data. The key needs to be shared with all authorized people.
 
Asymmetric encryption: Also called public key cryptography, asymmetric encryption uses two separate keys—one public (shared with everyone) and one private (known only to the key’s generator). The public key is used to encrypt the data and the private key helps to decrypt it.

#### What hashing methods do you know?
Digit rearrangement method:  This method uses a simple substitution in which a pre-determined part of the original data string is reversed, and taken as the hash value for the string.

The Folding method: For numeric strings, the folding method takes the original digits and divides them into several parts, adds these together, then uses a pre-determined number of the last digits resulting as the key or hash value.

#### How/where would you store sensitive data (like db password, API key, ...) of your application?
I would use my own server to store all these data, and a third party app against hackers.


## Computer science

### Algorithms

#### What is the difference between Stack and Queue data structure?
Stack structure follows the LIFO rule, 
Queue structure follows the FIFO rule

To both list you can insert only linearly, LIFO means Last In Last Out, so when you remove from the list you will remove the last element first, FIFO means First In First Out, so when you remove you start with the first element.
 
#### What is BubbleSort? Describe the main logic of this sorting algorithm.
BubbleSort is one of the most simple sorting algorithms.
Logic -  While the iterations it compares the first two elements of an array if the second one is bigger then it swap the two element if not it goes on to the next two.

#### Explain the process of finding the maximum and minimum value in a list of numbers!
 Declare a variable named “num”. Iterate through the given array.
Check whether the element in the scope is bigger than or smaller than "num", if it is asign that value to our variable.  At the end of the iteration we will have our result


#### Explain the process of calculating the average value in an array of numbers!
Declare a variable named "sum" set it equal to zero,  iterate through the given array.
Add every element from the array to our variable and when every element added divide it by the length of the array.

#### What is Big O complexity? Explain time and space complexity!
- Big O notation describes the performance or the complexity of an algorithm.
- Big O describes the worst case scenario.

Time complexity - It describes the amount of time it takes to run the algorithm is  estimated by counting the number of elementary operations performed by the algorithm.

 Space complexity -  is similar to time complexity, instead of saving time
        we want to save memory.

#### Explain the process of calculating the average value in a linked list of numbers!
Declare a variable named "sum" set it equal to zero. While the list has a next element.
Increment our variable by adding the next element of the list, then divide "sum" with the given lists lenght.
### Procedural
#### How the CASE condition works in SQL?
It works like an if-elseif-else statement, once a condition is true
    it will stop executing and returns an answer. If there wasn't any true condition it runs the ELSE caluse
#### How the switch-case condition works in JavaScript?
The switch statement performs different actions based on different conditions,
    like an if-elseif-else statement.
We have an expression that evaluates and based on that the proper case block runs
If there wasn't any matching case, the default block runs (optional).


#### How to achieve a switch-case-like structure in Python?
Well because we do not have switch in python we could use several if else statements, or we could use a dictionary, like this:
            
            def monday():
                print('monday')
            def tuesday():
                print('tuesday')
            
    use them as switch as a dict:
    
            switch = {
                1: monday,
                2: tuesday
            }

#### Explain variable scoping in Python!

In Python, the LEGB rule is used to decide the order in which the namespaces
    (a container where names are mapped to objects) are searched.

 Local: Definded inside function/class.
Enclosed: Defined inside enclosing functions(Nested function).
Global: Defined at the uppermost level.
Built-in: Reserved names in Python builtin modules.

#### What’s the difference between const and var in JavaScript?
- var:
     declarations are globally scoped or function scoped
    variables can be updated and re-declared within its scope
    not necessarily has to be initailzed at the declaration

- const:
    declarations are block scoped
    variables can neither be updated nor re-declared
    must be initailzed at the declaration

#### How the list comprehension looks like in Python?
list = (element for element in iterable)
#### How the “ternary expression” looks like in Python?
outcome = "true" if (expression) else "false"

#### How the ternary expression looks like in JavaScript?
 outcome = (expression) ? "true" : "false"

#### How to import a function from another module in Python?
from module import function

#### How to import a function from another module in JavaScript?
import {function} from "file.js";

### Functional
#### What is recursion?
The process in which a function calls itself directly or indirectly is called recursion and the corresponding function is called as recursive function. Using recursive algorithm, certain problems can be solved quite easily. Examples of such problems are Towers of Hanoi

#### Write a recursive function which calculates the Fibonacci numbers!

        function fibonacci(n) {
            if (n <= 1)
                return n;
            return fibonacci(n-1) + fibonacci(n-2);
        }

#### How to store a function in a variable in Python?
variable = function_name
call: variable()

#### List the ways of defining a callable logical unit in JavaScript!
- Function:        

        function function_name (arg){
            return arg + 1;
        }
    
- Variable (arrow function):

        let function_name = (arg) => {
            return arg + 1;
        }
        
- Object (anonymus function):
    let object_name = { function_name: function(arg) { return arg + 1;} }
#### What is an event listener? How to attach one?
Event listener is a function that waits for a specified event to occure.
Examples are clicking, pressing a key, hoovering, etc.
    
To attach a listener, first we have to query our selected DOM element, than we could attach a listener by specifying the event type.

#### How to trigger an event in JavaScript?
When an event is specified it can be triggered,like if we specify a “mouseenter” event it can be triggered by drag our mouse to the selected element.

#### What is a callback function? Tell some examples of its usage.
A callback function is a function that has been passed to another function as an argument, then invoked inside of that code (callback).
Callbacks are often used to continue execution after an asynchronus operation completed (".then()" function after a Promise).

#### What is a Python decorator? How does it work? Tell some examples of its usage.
Decorators allow us to extend the functionalty of a function without modifing the function itself.
Example:

function doSomething(name) {
  console.log('Hello, ' + name);
}

function loggingDecorator(wrapped) {
  return function() {
    console.log('Starting');
    const result = wrapped.apply(this, arguments);
    console.log('Finished');
    return result;
  }
}

const wrapped = loggingDecorator(doSomething);


doSomething('Graham');
// Hello, Graham

wrapped('Graham');
// Starting
// Hello, Graham
// Finished




#### What is the difference between synchronous and asynchronous execution?
When you are executing something synchronously, it means you wait for it to finish than move on the execution.
  When you are executing something asynchronously, it means you can move on execution, before this task finishes.

## Programming languages

### SQL

#### How can you connect your application to a database server? What are the possible ways?
You could connect your application to a database server via sockets (TCP, UNIX).
A socket is an endpoint of a two-way communication (client-server).

#### When do you use the DISTINCT keyword in SQL?
The SELECT DISTINCT statement is used to return only distinct (different) values. Inside a table, a column often contains many duplicate values; and sometimes you only want to list the different (distinct) values.

#### What are aggregate functions in SQL? Give 3 examples.
An aggregate function performs a calculation one or more values and returns a single value.
SUM() returns the sum of the records.
AVG() returns the average value of records.
MAX() MIN() returns the biggest,smallest value of the records.

#### What kind of JOIN types do you know in SQL? Could you give examples?
JOIN / FULL JOIN - return all the rows from both table.

INNER JOIN - return the matching rows from both table.

LEFT JOIN - return all row from left table and matching from the right

RIGHT JOIN - return all row from the right table matching from the left

#### What are the constraints in sql?
SQL constraints are used to specify rules for the data in a table.

The following constraints are commonly used in SQL:
NOT NULL
UNIQUE
PRIMARY KEY
FOREIGN KEY
CHECK
DEFAULT
INDEX

#### What is a cursor in SQL? Why would you use one?
A cursor is a database object that is used to retrieve data from the result set one row at a time.Cursors are used to avoid memory leaks, when the result contains a large number of records.

#### What are database indexes? When to use?
Indexes could speed up data retrieval in exchange of memory space and additional writes.

#### What are database transactions? When to use?
- A transaction is a mechanism that allows you to gather a group os operations and execute them, such a way that they are either executed (commit), or the state will be as if they were not executed.

#### What kind of database relations do you know? How to define them?
One-to-One:
    - A row from table "A" has only one one matching row in table "B", vica-versa
    - Can be used to divide large tables and for security purposes

One-to-Many:
    - Most common relations type
    - A row from table "A" can have many matching rows in table "B", but a row in
        table "B" can have only one matching row in table "A"

Many-to-Many:
    - A row from table "A" can have many matching rows in table "B"
    - A ~ relationship could be refered as two One-to-Many relationships, linked by a intermediary table (used to link the other two tables together) "junction table"

#### You have a table with an “address” field which contains data like “3525, Miskolc, Régiposta 9.” (postcode, city, street name and address). How would you query all records related to Miskolc?

SELECT *
    FROM table_name
WHERE address ILIKE '%Miskolc%';

#### How would you keep track of what kind of data has changed after an UPDATE or DELETE operation in a table?
Creating log tables

### HTML & CSS

#### What’s the difference between XML, XHTML and HTML?
HTML :The original language of the WWW, designed to create
    structured documents.
    
XML : Provides rules for creating, structuring and
    encoding documents.
    
XHTML : XML based HTML, it serves the same function as HTML
    and with the same rules as XML documents.


#### How to include a JavaScript file in a webpage?
To include a JS file in your HTML file, use a "script" tag.
        <script src="script.js"></script>

#### How to include a CSS file in a webpage?
To include a CSS file in your HTML file, use a "link" tag.
        <link rel="stylesheet" href="style.css">

#### How to select an element using its id in CSS?
You have to use a hashtag like:  #element { properties  }

#### How to select elements using their class in CSS?
You have to use a dot like:  .element { properties  }

#### How to select elements which have the ‘alpha’ and ‘beta’ classes in CSS?
.alpha.beta { properties }

#### How to select all list items in all ordered lists on the page in CSS?
ol li { properties }
ol > li { properties }

#### How to select elements using their attributes in CSS?
element[attribute] { properties }

#### What are UX and UI?
UI : The user interface is the graphical layout of an application. It consists of the buttons users click on, the text they read, the images, sliders, text entry fields, and all the rest of the items the user interacts with. 

UX:A user’s experience of the app is determined by how they interact with it. Is the experience smooth and intuitive or clunky and confusing? Does navigating the app feel logical or does it feel arbitrary? User experience is determined by how easy or difficult it is to interact with the user interface elements that the UI designers have created.

#### Please list some points that an application should fulfill to have good UX.
Useful: Content should be original and fulfill a need
Usable: Easy to use
Findable: Content are easily navigable
Accessible: For people with disabilities

#### What is XML, XSLT, DTD?
XML (Extensible Markup Language):
    - Used to store and transport data
    - Readable for both human and machine
    - Tags are not predefined
XSLT (eXtensible Stylesheet Language):
    - Styling language for XML
 DTD (Document Type Definition):
    - ~ defines a structure with the legal elements and attributes

#### What is the difference between HTML and XML?
HTML is a predefined markup language, XML is a framework for specifying markup languages.

HTML:
    - case insensitive
    - small errors are ignored
    - presentation of the data
    
XML:
    - case sensitive
    - no coding errors are allowed
    - transfer of the data

### Javascript

#### What is javascript?
JavaScript is a scripting, programming language that allows you to implement
complex features on a web page

#### When to use AJAX? Bring examples of its usage.
When web pages needs asynchronous update by exchanging  data
    with the server behind the scenes.

Example: Updating a table with new data without refreshing the page.

#### What is DOM and how to manipulate it from Javascript?
DOM (Document Object Model) is a programming API for HTML and XML documents.
To manipulate a DOM element, first you need to select it and store a reference to it
    in a variable, then we can manipulate it.

#### What are events and how/why to use them in Javascript?
- Events are actions made on the page, such as click, load, hoover, key press, drag, etc. JavaScript interactions with HTML is handled through events.
Events are used in JavaScript to manipulate the page, change its behavior.

#### What is event bubbling/capturing? How would you use it?
Event bubbling is when an event occurs on an element, it first runs the handlars on it,
then on its parent, all the way up on other ancestors
#### What is JSON and how do we use it?
JSON (JavaScript Object Notation) is lightweight data-interchange format, consists of key-value
    pairs. {“user”{“name:”George”,
             “email”:”george@george.com”
             “id”:1}      }


## Software engineering

### Version control

#### What type of branching strategy would you use?
A master branch where production code would be committed.
A development branch where features gets committed.
Feature branches for logically distributed features, and additional
branches if needed (complex feature).

#### What would you do if you find a bug on the production code (master branch)?
First find the issue, check where it came from ( in which update it was uploaded) 
Understand the problem, then solve it.

#### How can you move changes from one branch to another in GIT?
git merge <branch_name>
or
git cherr-pick <commit>

#### How does a VCS help with code reviews?
VCS helps to recall earlier versions of a code.
In code reviews it helps to see how did the reviewed made the code, and he/she can call out specific problems in that version of the code.

#### What is your favorite git command? Why?
git merge maybe ?
because I know that I finished that I done a good work and finaly it can be used and be part of the working software.

#### What does remote/local mean in Git?
Local is your local working folder, which is not seen by others, remote is your remote repository where you committed and pushed your changes so others can access it too.

### DevOps

#### Why is it good to use a package manager software?
This is a programming language's tool that allows you to easily import external dependencies into your projetcs venv.
It's good because you could add dependencies to your project effortlessly.

#### Why is it good to use a virtual environment for a project?
Virtualenv makes it possible to make an isolated python environment for each
    project.

### Networks

#### What kind of HTTP status codes do you know?
200- Everything OK
404-Not found, resource not found
505-internal server error

#### What is a API?
API (Application Program Interface) allows two application to communicate with each other.
API Example:
    - Stitting at a table in a restaurant with a menu to order from. The kitchen is part of the "system" that will prepare your order. What is missing is a link to communicate your order from your table to the kitchen, thats where the waiter or API comes in. The waiter is a messenger that takes your order (request) and tells the kitchen (the system) what to do. Than the waiter delivers the food (response) back to you.

#### What is REST API?
REST (REpresentational State Transfer) is a way for two computers to communicate over
    HTTP (GET, POST, DELETE, PUT, PATCH) in a similar way to web browsers and servers.


#### What is TCP/IP? What layers does it define, what are they responsible for?
TCP/IP (Transmission Control Protocol / Internet Protocol) is a set of standardized rules that allows
    computers to communicate on a network such as the internet.
    
- ~ contains four layers:

    - Process / Application Layer
        - This layer is the top most layer in the ~ model
        - Responsible for handling hig-level protcols
        - This layer allows the user to interact with the application
        
    - Host-to-Host / Transport Layer
        - Provides connectionless serivce and end-to-end delivery of transmission
        - Unreliable protocol, because it doscovers errors, but not specify them
        
    - Internet Layer / Network Layer
        - Second layer of the ~ model
        - Main responsibility is to send packets from any network
        
    - Network access / Link Layer
        - Lowest layer of the ~ model
        - This layer is the combination of the Physical layer and Data Link
            layer defined in the OSI reference model.
        - Defines how data should be sent through the network
        - Mainly responsible for the transmission of data between two devices on the same
            network

#### What’s the difference between TCP and UDP?
- TCP (Transmission Control Protocol):
    - Most commonly used protocol.
    - When a webpage is loaded, the computer sends a TCP packet to the web server's address, asking for the webpage.
        Then the server responds by sending a bunch of TCP packets, that your web browser stiches together to form the webpage.
    
- UDP (User Datagram Protocol):
    - Datagram is the same thing as packets of information.
    - ~ works similarly to TCP, but without all the error checking.
    - Back-and-Forth communication slows things down, so UDP packets are just
        sent to the recipient.
    - The sender won't wait to make sure the reciever recieved all packets.
    - Because of these things, ~ is faster than TCP, but at the same time less reliable.

#### How does an HTTP Request look like? What are the most relevant HTTP header fields?
HTTP requests are sent by the client to make actions on the server.
A request header is an HTTP header that can be used in an HTTP request, and that doesn't relate to the content of the message. Request headers, like Accept,Accept-* or If-* allow to perform conditional requests; others like Cookie,User agent, or Referer precise the context so that the server can tailor the answer.

EXAMPLE: GET https://webserver.com/index

#### How does an HTTP Response look like? What are the most relevant HTTP header fields?
HTTP Response is sent by the server to the client.

Maybe the most important fields: Access-Control
Connection
Content-Encoding
Content-Type
Keep-Alive
Transfer-Encoding


#### What is DNS? How does it work?
DNS stands for Domain Name System, and it translates the domain names to IP addresses, so it can be accessed. 
Example:it converts a name like “www.gmman.com” to IP like “192.168.1.1”

#### What is a web server?
On the hardware side:
    A web server is a computer that stores web server software and a website's component files.
    It's connected to the internet and supports physical data interchange.

On the software side:
    A web server includes several parts that control how web users access hosted files.
    It can be accessed through the domain names like "mozilla.org" of websites it stores
    
-At the most basic level, whenever a browser needs a file which is hosted on a web server, the browser requests the file via HTTP.

#### Explain the client-server architecture.
Is a computing model in which the server hosts, delivers, manages most of the resources
    (security reasons) and services to be consumed by the client.
Is a network architecture is which each computer or process on the network is either
    a client or a server.
    
- Servers are powerful computers or processes dedicated to managing disk drives or network traffic.
    
- Clients are PCs on which users run applications.
- Client rely on servers for resources, such as files, devices, and processing power.

#### What would you use a session for?
Session is a way to store user-specific data between requests.
A session is used for to know if a user is signed in our server,
and to see how long is he/she signed into.

#### What would you use a cookie for?
Cookies are used for websites to remember user informations such as items added to the shopping cart. It can also be used to remember pieces of information that the user entered into form fields such as usernames, addresses, emails.



## Software Development Methodologies

#### What kind of software development methodologies do you know? What are the main features of these?
Agile development methodology:
Teams use the agile development methodology to minimize risk (such as bugs, cost overruns, and changing requirements) when adding new functionality. In all agile methods, teams develop the software in iterations that contain mini-increments of the new functionality.

DevOps deployment methodology:
DevOps deployment centers on organizational change that enhances collaboration between the departments responsible for different segments of the development life cycle, such as development, quality assurance, and operations.

Waterfall development method:
Many consider the waterfall method to be the most traditional software development method. The waterfall method is a rigid linear model that consists of sequential phases (requirements, design, implementation, verification, maintenance) focusing on distinct goals. Each phase must be 100% complete before the next phase can start. 
#### What are the SCRUM roles?
1. Product Owner
   
    serves as an interface between the team and other involved parties.
    makes business decisions of importance and priorities.
    validates the solutions and verifies whether the quality is acceptable or not
   from the end-users' point of view.

2. SCRUM Master
    leads the team and sets tasks.
    does not interfere decisions in the team, rather is there for the team as
        and advisor.
     only interferes actively when someone does not obey the rules of SCRUM.

3. Development Team
     recives tasks from the project leader.
    decides self dependent, which requrirements or User Stories it can accomplish
         in one sprint.
    constructs tasks and responsible for the permutation of those.

#### What are the SCRUM ceremonies?
Sprint planning
    The goas of ~ is to answer the questions "What are we going to work on, and how
        are we going to do it?"

Sprint review
    Once a Sprint ends, to demonstrate the added functionality, the goal is to get
        feedback from the product owner.

Sprint retrospective
    Retrospectives typically lasts 90 minutes, to help us continiously improve the
        team culture by asking about what went well what doesn’t how we could improve in that
Daily SCRUM
    Once a Sprint begins, typically a 15 stand-up meeting to synchronize
        the work of team members.

#### What are the SCRUM artifacts?
1. Product Vision:
    - Defines the long-term goal of the product.
    
2. Sprint Goal:
    - Helps to focus the Sprint.
    
3. Product Backlog:
    - A list of all the things that are required in the product and changes
        made to it.
        
4. Sprint Backlog:
    - A set of Product Backlog items selected for the Sprint.

5. Definition of Done:
    - Every Product Backlog item has an acceptance criteria that defines if the
        item can be declared done.

6. Increment:
    - Sum of all the Product Backlog items completed.
    
7. The Burndown Chart:
    - Graphs that give an overview of progress over time while completing a
        project.

#### What is the main goal of a retrospective meeting?
To look at the teamwork and finding out what went well and why and what the team could work on, and how could work on those things, by set a few exact goals how we could improve those things.

#### Explain, when would you recommend to use the waterfall methodology?
When requirements are very clear and fixed.
Resources with required expertise are avaiable freely.
Client has high confidence in the organization.

