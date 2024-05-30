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

## What is the difference between final, finally, and finalize in Java?
`final` is a keyword used to make a variable, method, or class immutable. `finally` is a block of code that is executed after try and catch blocks, regardless of whether an exception is thrown. `finalize` is a method that is called by the garbage collector before an object is destroyed.

## What is the difference between checked and unchecked exceptions in Java?
Checked exceptions are exceptions that are checked at compile time, and the compiler requires that they be caught or declared in the method's `throws` clause. Unchecked exceptions are exceptions that are not checked at compile time, such as `NullPointerException` and `ArrayIndexOutOfBoundsException`.

## What is a ClassLoader in Java?
A ClassLoader in Java is part of the **JVM** that loads bytecode for classes. It is responsible for finding and loading class files at runtime. You can also write your own ClassLoader to customize the way classes are loaded.
It operates based on three principles: Delegation, Visibility, and Uniqueness.

## What are the Delegation, Visibility, and Uniqueness principles?
  - **Delegation Principle**: The ClassLoader forwards the request for class loading to its parent ClassLoader. It only attempts to load a class if the parent ClassLoader cannot find or load it. This ensures that classes are loaded by the most appropriate ClassLoader, maintaining a hierarchical structure of ClassLoaders.
  - **Visibility Principle**: A child ClassLoader can see all the classes loaded by its parent ClassLoader, but the parent cannot see classes loaded by the child. This principle ensures that classes loaded by different ClassLoaders remain isolated, preventing conflicts and ensuring that each ClassLoader can manage its own set of classes.
  - **Uniqueness Principle**: This principle ensures that a class is loaded only once, even if multiple requests to load the class are made. It is achieved through the delegation principle, where a child ClassLoader does not attempt to reload a class that has already been loaded by its parent.

## Spring Boot

### Inversion of Control
> Inversion of Control (IoC) is a design principle in software engineering that inverts the flow of control in a program. Traditionally, in procedural programming, the custom code of a program calls reusable libraries to handle generic tasks. However, with IoC, the framework or a generic container takes control of the flow, calling the custom code when needed.

*This principle is widely used in application development frameworks, especially in GUI environments and web server application frameworks, to make the framework extensible by the methods defined by the application programmer.*
*IoC is often associated with event-driven programming, where the framework or runtime environment handles the event loop and dispatch of events/messages, allowing the custom code to focus solely on event handling. This pattern is also known as the "Hollywood Principle: Don't call us, we'll call you".*

### Dependency Injection
> Dependency Injection (DI) is a software design pattern that implements the principle of Inversion of Control (IoC) by allowing one object (or static method) to supply the dependencies of another object. This technique is used to decouple objects from their dependencies, making the code more modular, testable, and maintainable.

It involves passing objects (dependencies) to other objects (clients) that require them, rather than having the clients create these dependencies themselves. This can be achieved through various methods, including constructor injection, setter injection, and interface injection.

Example: Playground - Little Girl - Football

### How do you handle exceptions in a Spring Boot application?
Handling exceptions in a Spring Boot application can be effectively managed through several strategies, including the use of `@ControllerAdvice`, custom exceptions, and Aspect-Oriented Programming (AOP). Here's a comprehensive approach to exception handling in Spring Boot:

  1. Use @ControllerAdvice for Global Exception Handling
  The @ControllerAdvice annotation allows you to handle exceptions globally across all controllers. This is particularly useful for centralizing error handling logic, ensuring consistency in error responses, and reducing code duplication.

  ```
  @ControllerAdvice
  public class GlobalExceptionHandler {
      @ExceptionHandler(Exception.class)
      public ResponseEntity<Object> handleException(Exception ex) {
          Map<String, Object> body = new HashMap<>();
          body.put("message", "An error occurred");
          return new ResponseEntity<>(body, HttpStatus.INTERNAL_SERVER_ERROR);
      }
  }
  ```

  2. Implement Custom Exceptions
  Defining custom exceptions can provide more specific error messages and handle unique situations that may not be covered by built-in Spring Boot exceptions.

  ```
  public class InvalidRequestException extends RuntimeException {
      public InvalidRequestException(String message) {
          super(message);
      }
  }
  ```

  3. Use @ExceptionHandler for Controller-Specific Exception Handling
  The @ExceptionHandler annotation allows you to handle exceptions thrown by specific controller methods. This is useful for providing customized error responses for specific exceptions.

  ```
  @ExceptionHandler(ResourceNotFoundException.class)
  public ResponseEntity<Object> handleResourceNotFoundException(ResourceNotFoundException ex) {
      Map<String, Object> body = new HashMap<>();
      body.put("message", ex.getMessage());
      return new ResponseEntity<>(body, HttpStatus.NOT_FOUND);
  }
  ```

