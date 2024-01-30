# Ultimate workbook

## WEB Basics

### DOM
> The **Document Object Model** (DOM) is a programming interface built for HTML and XML documents.
It represents the page that allows programs and scripts to dynamically update the document structure, content, and style. With DOM, we can easily access and manipulate tags, IDs, classes, attributes, etc.

DOM is a tree-like structure that represents the HTML code of the page (a bit like a family tree).
The browser turns each HTML element into something called, a DOM node.
DOM nodes have properties and methods that allow us to manipulate them using JavaScript.



### REpresentational State Transfer (REST)
> REST is an architectural style for providing standards between computer systems on the web, making it easier for systems to communicate with each other.

REST is a set of architectural constraints (set of guidelines), not a protocol or a standard.

In the REST architectural style, **the implementation of the client and the implementation of the server can be done independently without each knowing about the other**. This means that the code on the client side can be changed at any time without affecting the operation of the server, and the code on the server side can be changed without affecting the operation of the client.

**As long as each side knows what format of messages to send to the other, they can be kept modular and separate.**
Separating the user interface concerns from the data storage concerns, we **improve the flexibility** of the interface across platforms and **improve scalability** by simplifying the server components.

**Headers** and parameters are also important in the HTTP methods of a RESTful API HTTP request, as they contain important identifier information as to the request's **metadata, authorization, uniform resource identifier (URI), caching, cookies, etc**. There are request headers and response headers, each with their own HTTP connection information and status codes.

> By using a REST interface, different clients hit the same REST endpoints, perform the same actions, and receive the same responses.


### Application Programming Interface (API)
> An API is a set of definitions and protocols for building and integrating application software. It’s sometimes referred to as a contract between an information provider and an information user—establishing the content required from the consumer (the **call**/**request**) and the content required by the producer (the **response**).

If you want to interact with a computer or system to retrieve information or perform a function, an API helps you communicate what you want to that system so it can understand and fulfill the request.

Think of an API as a mediator between the users or clients and the resources or web services they want to get. It’s also a way for an organization to share resources and information while maintaining security, control, and authentication—determining who gets access to what. 

Advantage of an API is that you don’t have to know the specifics of caching—how your resource is retrieved or where it comes from.


### RESTful API (extra)
> In contrast, REST is a set of guidelines that can be implemented as needed, making REST APIs faster and more lightweight, with increased scalablity—perfect for Internet of Things (IoT) and mobile app development.

In order for an API to be considered RESTful, it has to conform to these criteria:

1. A client-server architecture made up of clients, servers, and resources, with requests managed through HTTP.
2. Stateless client-server communication, meaning no client information is stored between get requests and each request is separate and unconnected.
3. Cacheable data that streamlines client-server interactions.
4. A uniform interface between components so that information is transferred in a standard form. This requires that:
  - resources requested are identifiable and separate from the representations sent to the client.
  - resources can be manipulated by the client via the representation they receive because the representation contains enough information to do so.
  - self-descriptive messages returned to the client have enough information to describe how the client should process it.
  - hypertext/hypermedia is available, meaning that after accessing a resource the client should be able to use hyperlinks to find all other currently available actions they can take.
5. A layered system that organizes each type of server (those responsible for security, load-balancing, etc.) involved the retrieval of requested information into hierarchies, invisible to the client.
6. Code-on-demand (optional): the ability to send executable code from the server to the client when requested, extending client functionality.


### Node.js & npm
> **Node.js is an open-source and cross-platform JavaScript runtime environment.**

Developers use Node. js to create server-side web applications, and it is perfect for data-intensive applications since it uses an asynchronous, event-driven model.
A Node.js app runs in a single process, without creating a new thread for every request.

- Why?
Node.js is a cross-platform runtime, perfect for a wide range of use cases. Its huge community makes it easy to get started. It uses the V8 engine to compile JavaScript and runs at lightning-fast speeds. Node.js applications are very scalable and maintainable.

> **npm is the standard package manager for Node.js.**

It is two things: first and foremost, it is an online repository for the publishing of open-source Node.js projects; second, it is a command-line utility for interacting with said repository that aids in package installation, version management, and dependency management.


### Fetch
> The Fetch API provides a JavaScript interface for accessing and manipulating parts of the protocol, such as requests and responses. It also provides a global `fetch()` method that provides an **easy**, **logical** way to fetch resources **asynchronously** across the network.

> The `Promise` object represents the eventual completion (or failure) of an asynchronous operation and its resulting value.

Important about Promise:
  - then
  - catch
  - finally: The `finally()` method of `Promise` instances schedules a function to be called when **the promise is settled (either fulfilled or rejected)**

Unlike XMLHttpRequest that is a callback-based API, Fetch is promise-based and provides a better alternative that can be easily used in service workers. Fetch also integrates advanced HTTP concepts such as **CORS** and other extensions to HTTP.


### React
> React is the most popular **front-end JavaScript library** for building user interfaces. React can also render on the server using Node and power mobile apps using React Native.


### React hooks
> Hooks let us use React’s features-like managing your component’s state and or performing an after effect when certain changes occur in state(s) without writing a class. (were introduced in React 16.8)

A few important React Hooks:
  - useState: lets you add a state variable to your component.
  - useEffect: lets you synchronize a component with an external system.
  - useCallback: lets you cache a function definition between re-renders.
  - useRef: lets you reference a value that’s not needed for rendering.
  - useContext: lets you read and subscribe to context from your component.

> **Context** lets the parent component make some information available to any component in the tree below it—no matter how deep—without passing it explicitly through props.

> Building **Custom Hooks** (your own Hooks) lets you extract component logic into reusable functions.


### React Lifecycles
Each component in React has a lifecycle which you can monitor and manipulate during its three main phases.
The three phases are: **Mounting**, **Updating**, and **Unmounting**.
Mounting: means putting elements into the DOM.
Updating: A component is updated whenever there is a change in the component's state or props.
Unmounting: The next phase in the lifecycle is when a component is removed from the DOM, or unmounting as React likes to call it.


## Java & Object Oriented Programming (OOP)

### Java Memory Management (Stack Memory & Heap Space)
> **Stack Memory** in Java is used for static memory allocation and the execution of a thread. It contains primitive values that are specific to a method and references to objects referred from the method that are in a heap.

Access to this memory is in Last-In-First-Out (LIFO) order. Whenever we call a new method, a new block is created on top of the stack which contains values specific to that method, like primitive variables and references to objects.

When the method finishes execution, its corresponding stack frame is flushed, the flow goes back to the calling method, and space becomes available for the next method.

Key features of Stack Memory:
  - Variables inside the stack exist only as long as the method that created them is running.
  - Access to this memory is fast when compared to heap memory.
  - This memory is threadsafe, as each thread operates in its own stack.

> **Heap Space** is used for the dynamic memory allocation of Java objects and JRE classes at runtime. New objects are always created in heap space, and the references to these objects are stored in stack memory.

These objects have global access and we can access them from anywhere in the application.



### Heap
> The Java heap is the area of memory used to store objects instantiated by applications running on the JVM. When the JVM is started, heap memory is created and any objects in the heap can be shared between threads as long as the application is running.
The Java heap lives in RAM.


### Stack
> **In computer science**, a **stack** is an abstract data type that serves as a collection of elements with two main operations: Push, which adds an element to the collection, and. Pop, which removes the most recently added element.


### Stack vs Heap
- Heap memory is used by all the parts of the application whereas stack memory is used only by one thread of execution.
- The stack is generally smaller in size than the heap because it is used for storing small, temporary variables and data, while the heap is used for storing larger objects.


### JVM
> The **Java Virtual Machine** is a program whose purpose is to execute other programs. JVMs are available for many hardware and software platforms (i.e. JVM is platform dependent). JVM is the one that actually calls the main method present in a java code. JVM is a part of JRE(Java Runtime Environment)


### JRE & JDK
> **Java Runtime Environment** (JRE) is the implementation of the Java Virtual Machine (JVM) and is designed to provide an environment to execute Java programs.
It consists of the JVM, Java binaries, and other classes needed for the smooth execution of a program.
Importantly, JRE does not contain any development tools such as a compiler or debugger. If you simply want to execute a Java program, you can install only JRE without needing JDK.

> **Java Development Kit** (JDK) is used for developing Java applications.
It includes everything that JRE has, plus additional development tools like compilers, debuggers, and others.
Therefore, JDK is used when you want to create and compile new Java programs.

In short, de difference between the two:
  - JRE is used for running Java programs
  - JDK is used for developing Java programs


### JUnit
> JUnit is a testing framework for Java.


### JDBC
> JDBC stands for **Java Database Connectivity**. It provides a set of Java API for accessing the relational databases from Java program. These Java APIs enables Java programs to execute SQL statements and interact with any SQL compliant database.

Pros:
  - Clean and simple SQL processing
  - Good performance with large data
  - Very good for small applications
  - Simple and easy to learn syntax

Cons:
  - Complex if it's used in large projects
  - Large programming overhead (too much time and energy basically)
  - No encapsulation
  - Hard to implement MVC concept


### Maven



### Java Collections (https://www.javatpoint.com/collections-in-java)
> The **Collection** in Java is a framework that provides an architecture to store and manipulate the group of objects. **A Collection represents a single unit of objects, i.e., a group.**

Java Collections can achieve all the operations that you perform on a data such as searching, sorting, insertion, manipulation, and deletion.

What is a framework in Java:
  - It provides readymade architecture.
  - It represents a set of classes and interfaces.
  - It is optional.

The **Iterable** interface is the root interface for all the collection classes. In other words the **Collection** interface extends the Iterable interface.
Collection useful/important/popular subinterfaces: Set, List, Queue.

Main Collections that are good to know:
1. ArrayList
2. HashMap
The advantage of using a HashMap over a simple list is that it provides an average **time complexity** of **O(1)** for the put and get operations, making it highly efficient for large datasets.
If you try to insert a duplicate key in HashMap, it will replace the element of the corresponding key 1.
HashMap is known for its ability to quickly locate and store values based on their keys.

3. Stack (LIFO - pencake/verem)
4. PriorityQueue


### Primitive & Reference types
Types in Java are divided into two categories—primitive types and reference types.

**Primitive Types**:
1. `int`: used to store whole numbers (e.g., 5, -10)
2. `double`: used to store decimal numbers (e.g., 3.14, -0.5)
3. `boolean`: used to store true or false values
4. `char`: used to store single characters (e.g., 'a', 'B')
5. `byte`: used to store small integer values (from -128 to 127)
6. `short`: used to store small integer values (from -32,768 to 32,767)
7. `long`: used to store large integer values (from -9223372036854775808 to 9223372036854775807)
8. `float`: used to store decimal numbers with less precision than `double`
All other types are reference types, so classes, which specify the types of objects, are reference types.


### Equals & Hashcode
The `equals()` and `hashCode()` methods are fundamental methods in Java that are used to determine whether two objects are equal and to generate a hash code for an object, respectively. They are inherited from the Object class and can be overridden in your own classes to provide custom behavior.

If you override the equals() method in your class, you should also override the hashCode() method to ensure that equal objects have the same hash code.

hashCode()
Objects that are equal (according to their equals()) must return the same hash code.
Different objects do not need to return different hash codes.


### OOP principles
The four fundamental principles of object-oriented programming are the following:

  1. **Abstraction**: Representing the problem domain with a simplified model.
  Abstraction is a way of creating a simplified, good enough conceptual model of an otherwise complex mechanism or a system.
  Example:
  Cell phones are complex. But using them is simple.
  You interact with your phone by using only a few buttons. What’s going on under the hood? You don’t have to know — implementation details are hidden. You only need to know a short set of actions.

  2. **Encapsulation**: Hiding the inner workings of a component by only allowing access to it through a public set of functions.
  Encapsulation is achieved when each object keeps its state private, inside a class. Other objects don’t have direct access to this state. Instead, they can only call a list of public functions — called methods.
  
  Examle:
  There is a class called **Cat**. Fields: mood, hungry, energy. Methods: sleep(), play(), feed(), meow().
  What they can do is defined in the public methods sleep(), play() and feed(). Each of them modifies the internal state somehow and may invoke meow(). Thus, the binding between the private state and public methods is made.
  This is encapsulation.
  
  3. **Inheritance**: Ability to create new abstractions based on existing abstractions.
  Objects are often very similar. They share common logic. But they’re not entirely the same.
  So how do we reuse the common logic and extract the unique logic into a separate class? One way to achieve this is inheritance.
  It means that you create a (child) class by deriving from another (parent) class. This way, we form a hierarchy.

  The child class reuses all fields and methods of the parent class (common part) and can implement its own (unique part).

  Example:
  Main class: Person
  Lower classes: Teacher, Student.

  4. **Polymorphism**: Ability to implement inherited properties or methods in different ways across multiple abstractions.
  Simply put, polymorphism gives a way to use a class exactly like its parent so there’s no confusion with mixing types. But each child class keeps its own methods as they are.

  This typically happens by defining a (parent) interface to be reused. It outlines a bunch of common methods. Then, each child class implements its own version of these methods.

  Example:
  There is an interface called Figure with calculateSurface() and calculatePerimeter() methods declared.
  Triangle, Circle and Rectangle inherit the Figure interface (or abstract class).
  They implement their own versions of these 2 methods.
  **Triangle, Circle, and Rectangle now can be used in the same collection.**

All these features - if used properly - contribute to writing more testable, flexible, and maintainable code.


### SOLID principles
These **five** software development principles are guidelines to follow when building software so that it is easier to scale and maintain. They were made popular by a software engineer, **Robert C. Martin**.

1. **Single Responsibility**: A class should have a single responsibility
If a Class has many responsibilities, it increases the possibility of bugs because making changes to one of its responsibilities, could affect the other ones without you knowing.

Goal: This principle aims to separate behaviours so that if bugs arise as a result of your change, it won’t affect other unrelated behaviours.

2. **Open-Closed**: Classes should be open for extension, but closed for modification
Instead of modifying existing code, new functionality should be added through inheritance, composition, or other means of extension.

Goal: This principle aims to extend a Class’s behaviour without changing the existing behaviour of that Class. This is to avoid causing bugs wherever the Class is being used.

3. **Liskov Substitution**: It states that objects of a superclass should be replaceable with objects of their subclasses without affecting the correctness of the program.
The child Class should be able to process the same requests and deliver the same result as the parent Class or it could deliver a result that is of the same type.
Goal: This principle aims to enforce consistency so that the parent Class or its child Class can be used in the same way without any errors.

4. **Interface Segregation**: Clients should not be forced to depend on methods that they do not use.
The goal of this principle is to reduce the side effects of using larger interfaces by breaking application interfaces into smaller ones. It’s similar to the Single Responsibility Principle, where each class or interface serves a single purpose.
Goal: This principle aims at splitting a set of actions into smaller sets so that a Class executes ONLY the set of actions it requires.

5. **Dependency Inversion**
- High-level modules should not depend on low-level modules. Both should depend on the abstraction.
- Abstractions should not depend on details. Details should depend on abstractions.
High-level Module(or Class): Class that executes an action with a tool.
Low-level Module (or Class): The tool that is needed to execute the action
Abstraction: Represents an interface that connects the two Classes.
Goal: This principle aims at reducing the dependency of a high-level Class on the low-level Class by introducing an interface.


### YAGNI, SLAP, KISS principles
1. YAGNI: You Ain't Gonna Need It.
2. SLAP: Single Level of Abstraction Principle.
3. KISS: Keep It Simple, Stupid.


### Design Patterns


## Advanced
TODO: Annotations for every topics that needs it.

### Algorythms (time complexity & others)


### MVC
> The Model View Controller (MVC) design pattern specifies that an application consists of a data model, presentation information, and control information. The pattern requires that each of these be separated into different objects.

Model-View-Controller:
  - The **Model** contains the pure application data and pure logic describing how to present the data to a user.
  - The **View** presents the model’s data to the user. The view knows how to access the model’s data, but it does not know what this data means or what the user can do to manipulate it.
  - The **Controller** exists between the view and the model. It listens to events triggered by the view (or another external source) and executes the appropriate reaction to these events.

MVC mostly relates to the UI / interaction layer of an application. You’re still going to need a business logic layer, maybe some service layer, and a data access layer. 


### DAO
> DAO stands for **Data Access Object**. DAO Design Pattern is used to separate the data persistence logic in a separate layer. This way, the service remains completely in dark about how the low-level operations to access the database is done. This is known as the principle of Separation of Logic.


### DTO
> A **Data Transfer Object** (DTO) is an object that carries data between processes. You can use this technique to facilitate communication between two systems (like an API and your server) without potentially exposing sensitive information.


### Spring & Spring Boot
> **Spring** is an open-source framework that provides a comprehensive programming and configuration model for modern Java-based enterprise applications. The core module of Spring, also known as the “Spring Core” module, is at the heart of the framework and provides the fundamental functionality for **dependency injection (DI)** and **inversion of control (IoC)**.

> **Spring Boot** is an open source, microservice-based Java web framework. The Spring Boot framework creates a fully **production-ready environment** that is completely configurable using its prebuilt code within its codebase. The microservice architecture provides developers with a fully enclosed application, including embedded application servers.


### Bean
> In Spring, the objects that form the backbone of your application and that are managed by the Spring IoC container are called beans. A bean is an object that is instantiated, assembled, and managed by a Spring IoC container.
There are 3 ways to create a bean:
1. Using `@Component` Annotation: You can create a bean by annotating a class with `@Component`. The Spring framework automatically detects these classes and registers them as beans in the application context.
2. Defining Beans in XML Configuration File: You can also define a bean in an XML configuration file.
3. Using `@Bean` Annotation: You can define a bean in a configuration class using the @Bean annotation. The method annotated with `@Bean` returns an object that should be registered as a bean in the Spring application context.


### IoC
> **Inversion of Control** (IoC) is a design pattern that is often used in conjunction with the Dependency Injection (DI) pattern.
The basic idea behind IoC is to invert the flow of control in a program, so that instead of the program controlling the flow of logic and the creation of objects, the objects themselves control the flow of logic and the creation of other objects.

The Spring IoC container is responsible for managing the creation and configuration of objects in a Spring-based application.

The Spring IoC container creates objects, wires them together, configures them, and manages their complete lifecycle from creation till destruction. This removes the burden of instantiating and configuring objects from the application code, and allows the application code to focus on the business logic rather than on infrastructure concerns.


### Entity Relationships
> **Hibernate** is a Java framework that provides an object-relational mapping to an object-oriented model to the relational database. It means hibernate provides from Java classes to database tables and also provides data querying and retrieval facility.

You can tag JPA Entities with the `@Entity` annotation.

Using hibernate, if we want to have relationship between two entities, there must exist a foreign key relationship between the tables, we call it as Referential integrity.
The main advantage of having relationship between objects is, we can do operation on one object, and the same operation can transfer onto the other object in the database.

Here are the **4 types of relationships** we can have between objects in Hibernate:
  - One-To-One
  - Many-To-One
  - Many-To-Many
  - One-To-Many


### ORM (Object-Relational Mapping)
> **ORM** is a programming method to map objects in Java to relational entities in a database. In other words, converting data between relational databases and object-oriented programming languages.

Popular ORM tools/frameworks in Java are:
  - Spring Data JPA
  - Hibernate
  - Ebean

Advantages:
  - Let's business code access objects rather than DB tables.
  - Hide details of SQL queries (from OO logic)
  - It's based on JDBC 'under the hood'.
  - No need to deal with database implementation.
  - Entities based on business concepts rather than database structure.
  - Transaction management and automatic key generation.
  - Fast development of application.


### JPA
> The **Jakarta Persistence API** provides Java developers with an object/relational mapping facility for managing relational data in Java applications. JPA is not a tool nor a framework, but a set of interfaces for accessing, persisting, and managing data between Java objects and (a) relational database.

Because it is a set of interfaces, it will require an implementation to work with and persist Java objects. This will be ORM. 
Here are the main features of JPA:
  - Cleaner, easier, standardized ORM.
  - Supports inheritance, polymorphism, and polymorphic queries.
  - Supports metadata annotations/XML descriptors to define the mapping (between objects and relational database).
  - Supports a rich, SQL-like query language for static and dynamic queries.
  - Pluggable persistence providers like Hibernate, MyBatis, etc.
  - Caching: JPA supports 2 kinds of cache - first and second levels - to support performance tuning.


### Spring Data JPA
> **Spring Data JPA**, part of the larger Spring Data (framework extension) family, makes it easy to easily implement JPA-based (Java Persistence API) repositories. It makes it easier to build Spring-powered applications that use data access technologies.

Implementing a data access layer for an application can be quite cumbersome. Too much boilerplate code has to be written to execute the simplest queries. Add things like pagination, auditing, and other often-needed options, and you end up lost.

Spring Data JPA aims to significantly improve the implementation of data access layers by reducing the effort to the amount that’s actually needed. As a developer you write your repository interfaces using any number of techniques, and Spring will wire it up for you automatically. You can even use custom finders or query by example and Spring will write the query for you!


### Hibernate ORM
> Hibernate is an implementation of the Java Persistence API (JPA) specification. As such, it can be easily used in any environment supporting JPA including Java SE applications, Java EE application servers, Enterprise OSGi containers, etc.
> It is a powerful, high performance Object-Relational Persistence and Query service for any Java Application.

Hibernate maps Java classes to database tables and from Java data types to SQL data types and relieves the developer from 95% of common data persistence related programming tasks.

Hibernate sits between traditional Java objects and database server to handle all the works in persisting those objects based on the appropriate O/R mechanisms and patterns.


### Authentication
> The API authentication process validates the identity of the client attempting to make a connection by using an authentication protocol. The protocol sends the credentials from the remote client requesting the connection to the remote access server in either plain text or encrypted form. The server then knows whether it can grant access to that remote client or not.

Here is the list of common ways of authentication:
  - JWT Authentication
  - Token based Authentication
  - Session based Authentication
  - Basic Authentication
  - OAuth - Open Authorization
  - Cookie-Based Authentication


### JWT
> JWT stands for **JSON Web Token** is a token-based encryption open standard/methodology that is used to transfer information securely as a JSON object.

Clients and Servers use JWT to securely share information, with the JWT containing encoded JSON objects and claims. JWT tokens are designed to be compact and safe to use within URLs.


### Token based Authentication
> Token-based authentication is a protocol which allows users to verify their identity, and in return receive a unique access token.

Auth tokens work like a stamped ticket. The user retains access as long as the token remains valid. Once the user logs out or quits an app, the token is invalidated.

Token-based authentication is different from traditional password-based or server-based authentication techniques. Tokens offer a second layer of security, and administrators have detailed control over each action and transaction.


### Session based Authentication
> User is assigned some unique identifier and this identifier is stored on the server in memory. Client sends this session id in all the requests and server uses it to identify the user.

Step by step of how it works:
Server keeps track of the logged in users in memory or in storage.
1. Client sends the login request.
2. Server validates the credentials, create a session (some random unique identifier to identify the user) and stores it in memory assigned to current user and returns back the generated session id.
3. Client recieves the session id and stores it in a cookie if cookies are enabled by client or somewhere else (e.g. in local/session storage) if cookies are not enabled.
4. Client sends next requests with session id. Server checks: if there exists a user with the current session id in its storage?
Yes: 200 OK
No: Invalid Session ID --> 401 Unauthorized
5. When the user logs out, the session is destroyed (cookie removed + session removed from the server) and same Session ID cannot be reused.


### Basic Authentication


### OAuth - Open Authorization


### Cookie-Based Authentication
> Cookies are pieces of data used to identify the user and their preferences. The browser returns the cookie to the server every time the page is requested. Specific cookies like HTTP cookies are used to perform cookie-based authentication to maintain the session for each user.


### Authorization


### Spring Security


### Security Filter Chain


