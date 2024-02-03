# Chapter 1: Up and Running Quickly

TypeScript generates JavaScript: Wherever we see a use for JavaScript in the modern world, we can generate this JavaScript using TypeScript.

JavaScript is an interpreted language, and as such has benefits, but also has its drawbacks. Interpreted languages do not have a compilation step, and therefore cannot check that all code written has no minor mistakes in spelling or syntax before it is actually run. TypeScript is a strongly typed, object-oriented language that uses a compiler to generate JavaScript. The compiler will identify errors within the code base even before it is run in an interpreter.

## 1.1 A simple TypeScript IDE

TypeScript generates JavaScript through what is called a compilation step. This means that once you have written some TypeScript code, you will need to compile, or, more correctly, transpile this code, which will generate JavaScript. In order to do this compilation step, you will need a Node environment, and the TypeScript compiler itself.

### 1.1.1 Using npm

### 1.1.2 Hello TypeScript

It's as simple as creating a TypeScript file, generating JavaScript from it using the TypeScript compiler (tsc), and executing the resulting JavaScript using Node.

### 1.1.3 Template strings and JavaScript versions

TypeScript will generate JavaScript based on the target version of JavaScript that you specify. We can therefore write TypeScript code using any of the newest JavaScript standards, and TypeScript will correctly generate the equivalent JavaScript.

### 1.1.4 TypeScript project configuration

### 1.1.5 Watching files for changes

## 1.2 TypeScript basics

### 1.2.1 Strong typing

Strong typing, or static typing as it is also known, means that when we create a variable, or define a parameter in a function, we specify what type it is. Once this type has been specified, we cannot change it. Loose typing is the exact opposite of this concept, and JavaScript is a loosely typed language.

Changing the type of a variable at runtime can be a very dangerous thing to do. If your code is expecting a variable to be a number, and tries to perform calculations on it, the results of these calculations may be unexpected if the variable held a string. In a similar way, if a variable is a function that does something, and someone inadvertently changes that variable into a string, a whole block of functionality has suddenly become lost.

### 1.2.2 Basic types

### 1.2.3 Inferred typing

TypeScript also uses a technique called inferred typing, or type inference, to determine the type of a variable. This means that even if we do not explicitly specify the type of a variable, the compiler will determine its type based on when it was first assigned. Again, once the variable has a type, normal type comparisons will be used.

### 1.2.4 Duck typing

TypeScript also uses a method called duck typing for more complex variable types: two variables are considered to have the same type if they have the same properties and methods.

### 1.2.5 Function signatures and void

### 1.2.6 VS Code IntelliSense

### 1.2.7 VS Code debugging

Here, we have added the sourceMap property, and set it to true. This compiler option will now generate a .map file as well as a .js file for each of our TypeScript files. Remember that Node is a JavaScript runtime, and will only execute JavaScript code. The VS Code editor, therefore, needs to know how to map the executing JavaScript code back to our TypeScript source. This is what the .map file is used for.

### 1.2.8 Introducing third-party libraries

### 1.2.9 Declaration files

TypeScript uses files known as declaration files as a sort of header file, similar to languages such as C++, in order to superimpose strong typing on existing JavaScript libraries. These declaration files, which have a .d.ts extension, hold information that describes the available functions and variables that a library exposes, along with their associated type annotations.

We do not need to know the implementation of this library at this point; we just need to know that this library exists, what name it has, and what we can do with it.

# Chapter 2: Exploring the Type System

## 2.1 any, let, unions, and enums

### 2.1.1 The any type

Specifying that an object has a type of any will, in essence, remove the TypeScript strict type checking.

While the any type is a necessary feature of the TypeScript language, and is used for backward compatibility with JavaScript, its usage should be limited as much as possible. As we have seen with untyped JavaScript, excessive use of the any type will quickly lead to coding errors that will be difficult to find. Rather than using the any type, try to figure out the correct type of the object that you are using, and then use this type instead.

Using interfaces allows us to cover almost every possible combination of types, meaning that using the any type, in most cases, is unnecessary.

### 2.1.2 Explicit casting

### 2.1.3 The let keyword

### 2.1.4 Const values

### 2.1.5 Union types

TypeScript allows us to express a type as a combination of two or more other types. These types are known as union types, and they use the pipe symbol ( | ) to list all of the types that will make up this new type.

### 2.1.6 Type guards

A type guard is an expression that performs a check on our type, and then guarantees that type within its scope.

### 2.1.7 Type aliases

TypeScript introduces the concept of a type alias, where we can create a named type that can be used as a substitute for a type union. Type aliases are a handy way of specifying a type union and giving it a name, and are particularly useful when the type union is used over and over again.

### 2.1.8 Enums

Enums are a special type whose concept is similar to other languages such as C#, C++, or Java, and provides the solution to the problem of special numbers, or special strings. Enums are used to define a human-readable name for a specific number or string.

#### 2.1.8.1 String enums

#### 2.1.8.2 Const enums

Const enums have been introduced for performance reasons.

When we create an enum, the compiler will generate a fully fledged JavaScript object, complete with properties and functions for the enum's implementation. But there is no actual implementation of the const enum itself at all. The compiler has simply substituted the JavaScript code wherever we have used the const enum value.

This reduces the size of code that is generated, as the JavaScript runtime does not need to work with a fullblown JavaScript object in order to check a value.

## 2.2 More primitive types

### 2.2.1 Undefined

### 2.2.2 Null

Setting a value to null is intended to indicate that the variable is known, but has no value, as opposed to undefined, where the variable has not been defined in the current scope.

### 2.2.3 Conditional expressions

### 2.2.4 Nullish coalescing

TypeScript allows us to use a feature of the 2020 JavaScript standard called nullish coalescing, which is a handy shorthand that will provide a default value if a variable is either null or undefined.

### 2.2.5 Null or undefined operands

### 2.2.6 Definite assignment

### 2.2.7 Object

TypeScript introduces the object type to cover types that are not primitive types. This includes any type that is not number, boolean, string, null, symbol, or undefined.

### 2.2.8 Unknown

The unknown type can be seen as a type-safe alternative to the type any. A variable marked as unknown can hold any type of value, similar to a variable of type any. The difference between the two, however, is that a variable of type unknown cannot be assigned to a known type without explicit casting.

### 2.2.9 Never

### 2.2.10 Never and switch

## 2.3 Object spread

### 2.3.1 Spread precedence

### 2.3.2 Spread with arrays

## 2.4 Tuples

### 2.4.1 Tuple destructuring

### 2.4.2 Optional tuple elements

### 2.4.3 Tuples and spread syntax

### 2.4.4 Object destructuring

## 2.5 Functions

### 2.5.1 Optional parameters

### 2.5.2 Default parameters

### 2.5.3 Rest parameters

### 2.5.4 Function callbacks

### 2.5.5 Function signatures as parameters

### 2.5.6 Function overrides

### 2.5.7 Literals

# Chapter 3: Interfaces, Classes, Inheritance, and Modules

