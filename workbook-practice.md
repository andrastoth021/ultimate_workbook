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
