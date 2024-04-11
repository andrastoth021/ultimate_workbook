# 10 TS questions and answers

## What is TypeScript and how does it differ from JavaScript?
	TypeScript is a **superset** of JavaScript that compiles to plain JavaScript. TypeScript is an **object-oriented** and **statically typed** language, similar to Java and C#, whereas JavaScript is a scripting language closer to Python. The object-oriented nature of TypeScript is complete with features such as classes and interfaces, and its static typing allows for better tooling with type inference at your disposal.
	From a code perspective, TypeScript is written in a file with a `.ts` extension whereas JavaScript is written with a `.js` extension. Unlike JavaScript, TypeScript code is not understandable by the browsers and can’t be executed directly in the browser or any other platform. The `.ts` files need to be transpiled using TypeScript’s `tsc` transpiler to plain JavaScript first, which then gets executed by the target platform.

## What are the benefits of using TypeScript?
	An immediate advantage of using TypeScript is its tooling. TypeScript’s strict checks catch your errors early, greatly reducing the chances of typos and other human errors from making their way to production.
	A long-run advantage of using TypeScript is its scalability and maintainability. The ability to describe the shape of objects and functions directly in your code makes your codebase easier to understand and more predictable. When used correctly, TypeScript provides a more standardized language resulting in better readability which could save time and effort down the road as the codebase grows.

## What are interfaces in TypeScript?
	Interfaces in TypeScript are a powerful feature that allows developers to define the shape of objects, functions, and classes.
	Interfaces act as a syntactical contract that entities should conform to, defining properties, methods, and events that any entity must adhere to. They are used to provide a standard structure and to ensure that objects have the correct shape and properties.

## How do you create a new type using a subset of an interface?
	TypeScript has a utility type called `omit` that lets you construct a new type by passing a current type/interface and selecting the keys to be excluded from the new type.
	**Example**:
```ts
interface User {
	name: string;
	description: string;
	age: number;
	email: string;
}

// removes the `email` property from the User interface
type UserPreview = Omit<User, "email">;

const userPreview: UserPreview = {
	name: "Bob",
	description: "Awesome guy",
	age: 20
};
```

## How do “enums” work in TypeScript?
	Enums in TypeScript are commonly used to represent a set number of options for a given value using a set of key/value pairs.
	Under the hood, TypeScript translates enums into plain JavaScript objects after compilation. This makes the use of enums more favorable compared to using multiple independent `const` variables. The grouping that enums offer makes your code type-safe and more readable.
	**Example**:
```ts
enum UserType {
  Guest = "G",
  Verified = "V",
  Admin = "A",
}

const userType: UserType = UserType.Verified;
```

## What access modifiers are supported by TypeScript?
	TypeScript uses access modifiers to set the visibility of a class’s contents. Because TypeScript gets compiled to JavaScript, logic related to access modifiers is applied during compile time, not at run time.
	There are three types of access modifiers in TypeScript: `public`, `private`, and `protected`.
	- **public**: All properties and methods are public by default. Public members of a class are visible and accessible from any location.
	- **protected**: Protected properties are accessible from within the same class and its subclass. For example, a variable or method with the `protected` keyword will be accessible from anywhere within its class and within a different class that extends the class containing the variable or method.
	- **private**: Private properties are only accessible from within the class the property or method is defined.
	asdq

## What are generics and how to use them in TypeScript?
	Good software engineering practice often encourages **reusability** and **flexibility**. The use of **generics** provides reusability and flexibility by allowing a component to work over a variety of types rather than a single one while preserving its precision (unlike the use of `any`).
	To call a generic function, you can either pass in the type explicitly within angle brackets or via _type argument inference_, letting TypeScript infer the type based on the type of the argument passed in.
	**Example**:
```ts
function updateUser<Type>(arg: Type): Type {
	return arg;
}

// explicitly specifying the type
let user = updateUser<string>("Bob");

// type argument inference
let user = updateUser("Bob");
```

## What is the difference between `any` and `unknown`?
	`unknown` is a special type that is similar to `any`. Like `any`, a common use case of the `unknown` type is when you don’t know the exact type upfront. `unknown` variables accept any value.
	However, when trying to operate on an `unknown` variable, TypeScript requires a type check or a type assertion.
	**Examples**:
```ts
// any example
invokeCallback(callback: any): void {
	callback();
}

// unknown example
invokeCallback(callback: unknown): void {
	if (typeof callback === 'function') {
		callback();
	}
}
```

## What are conditional types in TypeScript?
	Conditional types in TypeScript are similar to ternary operators. As the name suggests, it assigns a type to the variable based on a condition.
	**Example**: `A extends B ? X : Y`
	Type `X` in the snippet above is applied if the variable fulfills the condition whereas type `Y` is applied if the variable doesn’t.

## What is the difference between union and intersection types?
	Unions (`|` keyword) and intersection(`&` keyword) types let you compose and combine existing types instead of creating them from scratch. Both union and intersection come with their unique characteristics which make them ideal for different use cases.
	
	```ts
interface B {
  name: string,
  email: string
}

interface C {
  name: string,
  age: number
}
	```
	
	A **union** type is described as a type that can be one of several types.
	Example:
	```ts
	type A = B | C;
	```
	*`A` in the snippet above can either be of type `B` or `C`. Based on `B` and `C`s interfaces, `A` can either contain `name` and `email` (`B`) or `name` and `age` (`C`), but not `email` and `age`.*
	
	**Intersection** on the other hand, is described as a type that combines multiple types into one – combining all the properties of each type to create a new type.
	Example:
	```ts
	type A = B & C;
	```
	*`A` in the snippet above will contain all the properties from both `B` and `C` (`name`, `email`, and `age`).*

