# JAVA

## JVM, JRE, JDK

### JVM

#### What is JVM?
> JVM (Java Virtual Machine) is an abstract machine. It is a specification that provides runtime environment in which java bytecode can be executed.

The JVM is **responsible for** interpreting and executing Java bytecode, which is a compiled version of the Java source code. It also provides features like memory management, security, and platform independence.

One of the **key advantages** of using the JVM is that it allows developers to write code in Java or other JVM-compatible languages and run it on any platform that has a JVM installed, without having to worry about the underlying hardware or operating system
Some popular JVM languages include Java, Kotlin, Scala, and Groovy.

It is:
  1. **A specification** where working of Java Virtual Machine is specified. But implementation provider is independent to choose the algorithm. Its implementation has been provided by Oracle and other companies.
  2. **An implementation:** JVM's implementation is known as JRE (Java Runtime Environment).
  3. **Runtime Instance:** Whenever you write java command on the command prompt to run the java class, an instance of JVM is created.

#### What it does?
The JVM performs the following operations:
  - Loads code
  - Verifies code
  - Executes code
  - Provides runtime environment

#### How does it work? (Compilation Process)
Java Source Code (mycode.java) --> Java Compiler (javac) --> Bytecode --> **JVM** --> Machine code --> OS (Windows for example)


### JRE
> JRE is an acronym for Java Runtime Environment. The Java Runtime Environment is a set of software tools which are used for developing Java applications. It is used to provide the runtime environment. It is the implementation of JVM.

#### What does JRE consist of?
  - Set of libraries (like JDBC)
  - Java Virtual Machine (JVM)


### JDK
> JDK is an acronym for Java Development Kit. The Java Development Kit (JDK) is a software development environment which is used to develop java applications and applets.

#### What does JDK consist of?
  - Development Tools: interpreter/loader (java), a compiler (javac), etc.
  - Java Runtime Environment (JRE)


## Spring Boot

### Inversion of Control
> Inversion of Control (IoC) is a design principle in software engineering that inverts the flow of control in a program. Traditionally, in procedural programming, the custom code of a program calls reusable libraries to handle generic tasks. However, with IoC, the framework or a generic container takes control of the flow, calling the custom code when needed.

*This principle is widely used in application development frameworks, especially in GUI environments and web server application frameworks, to make the framework extensible by the methods defined by the application programmer.*
*IoC is often associated with event-driven programming, where the framework or runtime environment handles the event loop and dispatch of events/messages, allowing the custom code to focus solely on event handling. This pattern is also known as the "Hollywood Principle: Don't call us, we'll call you".*

### Dependency Injection
> Dependency Injection (DI) is a software design pattern that implements the principle of Inversion of Control (IoC) by allowing one object (or static method) to supply the dependencies of another object. This technique is used to decouple objects from their dependencies, making the code more modular, testable, and maintainable.

It involves passing objects (dependencies) to other objects (clients) that require them, rather than having the clients create these dependencies themselves. This can be achieved through various methods, including constructor injection, setter injection, and interface injection.

Example: Playground - Little Girl - Ball
