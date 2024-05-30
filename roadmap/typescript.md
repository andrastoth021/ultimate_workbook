# [TypeScript Roadmap](https://roadmap.sh/typescript)
(3 - 1 sor különbségek)



## Tartalomjegyzék (Table of contents)
  1. [Introduction](##Introduction)
    - [TypeScript vs JavaScript](###TypeScript-vs-JavaScript)
    - TS and JS Interoperability
    - Installation and Configuration
      - tsconfig.json
      - Compiler Options
    - Running TypeScript
      - tsc
      - ts-node
      - TS Playground
  2. [TypeScript Types](##TypeScript-Types)
    - [Assertions](###Assertions)
    - [Primitive Types](###Primitive-Types)
    - [Object Types](###Object-Types)
    - [Other Types](###Other-Types)
  3. [Type Inference](##Type-Inference)
  4. [Type Compatibility](##Type-Compatibility)
  5. [Combining Types](##Combining-Types)
    - [Union Types](###Union-Types)
    - [Intersection Types](###Intersection-Types)
    - [Type Aliases](###Type-Aliases)
    - [keyof operator](###keyof-operator)
  6. Type Guards / Narrowing
    - instanceof
    - typeof
    - Equality
    - Truthiness
    - Type Predicates
  7. TypeScript Interfaces
    - Types vs Interfaces
    - Extending Interfaces
    - Interface declaration
    - Hybrid Types
  8. Classes
  9. Generics
    - Generic Types
    - Generic Constraints
  10. Decorators
  11. Utility Types
  12. Advanced Types
    - Mapped Types
    - Conditional Types
    - Literal Types
    - Template Literal Types
    - Recursive Types
  13. TypeScript Modules
  14. Ecosystem
    - Useful Packages


## Introduction
> TypeScript is a statically-typed programming language that is a superset of JavaScript. It was developed and is maintained by Microsoft. TypeScript was created to address the challenges of building large-scale JavaScript applications and adds optional type annotations, classes, interfaces, and other features to the language.

The main benefits of using TypeScript include:
  - Type Safety
  - Improved Tooling
  - Improved Maintainability
  - Backwards Compatibility

### TypeScript vs JavaScript
> JavaScript is a dynamically-typed language that is primarily used for client-side web development and can also be used for server-side development.

Here are a few key differences between TypeScript and JavaScript:
  - **Types**: TypeScript has optional type annotations while JavaScript is dynamically-typed. This means that in TypeScript, you can specify the data type of variables, parameters, and return values, which can help catch type-related errors at compile-time.
  - **Syntax**: TypeScript extends JavaScript syntax with features like interfaces, classes, and namespaces. This provides a more robust and organized structure for large-scale projects.
  - **Tooling**: TypeScript has better tooling support, such as better editor integration, type checking, and code refactoring.
  - **Backwards Compatibility**: TypeScript is fully compatible with existing JavaScript code, which means you can use TypeScript in any JavaScript environment.


## TypeScript Types
### Assertions
> Type assertions in TypeScript are a way to tell the compiler to treat a value as a specific type, regardless of its inferred type.

There are two syntaxes for type assertions in TypeScript:
- The “angle-bracket” syntax: `<T>value`
- The “as” syntax: `value as T`

1. `as const` is a type assertion in TypeScript that allows you to assert that an expression has a specific type, and that its value should be treated as a read-only value.
Example: `const colors = ['red', 'green', 'blue'] as const;`

2. `as [type]`: In TypeScript, the `as` keyword is used for type assertions, allowing you to explicitly inform the compiler about the type of a value when it cannot be inferred automatically. Type assertions are a way to override the default static type-checking behavior and tell the compiler that you know more about the type of a particular expression than it does.

Here’s a simple example:
```Typescript
let someValue: any = "Hello, TypeScript!";
let strLength: number = (someValue as string).length;

console.log(strLength); // Outputs: 18
```

3. `any` is a special type in TypeScript that represents a value of any type. When a value is declared with the any type, the compiler will not perform any type checks or type inference on that value.

Example: `let anyValue: any = 42;`

### Primitive Types
- boolean
- number
- string
- void
- undefined
- null

### Object Types
- Interface: TypeScript allows you to specifically type an object using an interface that can be reused by multiple objects.
- Class: In TypeScript, a class is a blueprint for creating objects with specific properties and methods.
- Enum:  It allows a developer to define a set of named constants. Using enums can make it easier to document intent, or create a set of distinct cases.
- Arrays
- Tuples: A tuple type is another sort of Array type that knows exactly how many elements it contains, and exactly which types it contains at specific positions.

### Other Types
- any: You can use it whenever you don’t want a particular value to cause typechecking errors.
- object: To define an object type, we simply list its properties and their types.
- unknown: It is the type-safe counterpart of any. Anything is assignable to unknown, but unknown isn’t assignable to anything but itself and any without a type assertion or a control flow based narrowing.
- never: The never type represents the type of values that never occur. For instance, never is the return type for a function expression or an arrow function expression that always throws an exception or one that never returns.

## Type Inference
Type inference in TypeScript refers to the process of automatically determining the type of a variable based on the value assigned to it. This allows you to write code that is more concise and easier to understand, as the TypeScript compiler can deduce the types of variables without you having to explicitly specify them.

Example: `let name = 'John Doe';`

## Type Compatibility
TypeScript uses structural typing to determine type compatibility. This means that two types are considered compatible if they have the same structure, regardless of their names.

Example:
```TypeScript
interface Point {
  x: number;
  y: number;
}

let p1: Point = { x: 10, y: 20 };
let p2: { x: number; y: number } = p1;

console.log(p2.x); // Output: 10
```
In this example, `p1` has the type `Point`, while `p2` has the type `{ x: number; y: number }`. Despite the fact that the two types have different names, they are considered compatible because they have the same structure. This means that you can assign a value of type `Point` to a variable of type `{ x: number; y: number }`, as we do with `p1` and `p2` in this example.

## Combining Types
### Union Types
> Union Types in TypeScript allow you to specify multiple possible types for a single variable or parameter. A union type is written as a vertical bar | separated list of types.

Example:
```TypeScript
function combine(input1: string | number, input2: string | number) {
  return input1 + input2;
}
```

### Intersection Types
> An intersection type creates a new type by combining multiple existing types. The new type has all features of the existing types.

To combine types, you use the `&` operator as follows:
```TypeScript
type typeAB = typeA & typeB;
```

The `typeAB` will have all properties from both typeA and typeB.
Note that the union type uses the `|` operator that defines a variable which can hold a value of either `typeA` or `typeB`.

### Type Aliases
> A Type Alias in TypeScript allows you to create a new name for a type.

Example:
```TypeScript
type Name = string;
type Age = number;
type User = { name: Name; age: Age };

const user: User = { name: 'John', age: 30 };
```
In the example above, `Name` and `Age` are type aliases for `string` and `number` respectively. And `User` is a type alias for an object with properties `name` of type `Name` and `age` of type `Age`.

### keyof operator
The `keyof` operator in TypeScript is used to get the union of keys from an object type. Here’s an example of how it can be used:

```TypeScript
interface User {
  name: string;
  age: number;
  location: string;
}

type UserKeys = keyof User; // "name" | "age" | "location"
const key: UserKeys = 'name';
```

In this example, `UserKeys` is a type that represents the union of keys from the `User` interface, which is `"name"` | `"age"` | `"location"`. And a constant named `key` with the type `UserKeys` is declared with the value `"name"`.

