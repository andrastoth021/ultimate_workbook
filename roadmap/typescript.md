# 10 TS questions and answers

### What is TypeScript and why is it used?
TypeScript is a superset of JavaScript that adds static types to the language, making it easier to catch errors during development and enhancing code documentation. It's particularly useful for large-scale applications.

### Explain the concept of 'any' in TypeScript.
The 'any' type is a special type in TypeScript that allows a variable to hold any type of value. It's useful when the type of a variable is not known at compile time.

### What does the `Omit` type do in TypeScript?
The `Omit` type is used to create a new type by excluding specified properties from an existing type.
For example, `Omit<Person, 'location'>` creates a new type that has all properties of `Person` except for `location`.

### What are decorators in TypeScript and where can they be applied?
Decorators are a special kind of declaration that can be attached to a class declaration, method, accessor, property, or parameter. They can be used to modify the behavior of the target they are attached to.
To use decorators, you define a function (the decorator) that modifies or adds behavior to the target (e.g., class, method). This function is then prefixed with the `@` symbol and placed immediately before the declaration it decorates.

### Explain the use of the `tsconfig.json` file.
The `tsconfig.json` file is used to specify the root files and the compiler options required to compile a TypeScript project. It helps in configuring the TypeScript compiler according to the project's requirements.

### What is meant by contextual typing?
Contextual typing is a feature of TypeScript where the type of a variable is inferred from its usage or the context in which it is used. This reduces the need to explicitly type variables in many cases.
Example: `let x = 3;`
*Here, TypeScript infers that the type of x is number, because it is initialized with a numeric literal.*

### What are the recent advancements in TypeScript?
Recent versions of TypeScript, such as 4.2 and 4.5, have introduced more flexible type annotations, tougher checks, additional configuration choices, and new utility types like `Awaited` for better handling of asynchronous code.

### Explain the concept of optional chaining in TypeScript.
Optional chaining allows you to access deeply nested properties of an object without having to check each level for existence. It uses the `?.` operator to access properties and methods, returning `undefined` if any reference in the chain is `null` or `undefined`.

### What are abstract classes in TypeScript?
Abstract classes are base classes from which other classes may be derived. They may not be instantiated directly. Abstract classes can contain abstract methods, which are methods declared in an abstract class but do not contain an implementation.

### Explain the difference between union and intersection types in TypeScript.
Union types allow you to define a type that can be one of several types, using the `|` operator. Intersection types, on the other hand, combine multiple types into one, allowing you to add together existing types.
