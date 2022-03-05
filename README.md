# Javascript-playground

This repository is my playground for JavaScript which I have created for two different Udemy courses, namely

- The Modern Javascript Bootcamp Course (2022)
- JavaScript Algorithms and Data Structures Masterclass

We won't explicitly write which content is from which course or which content was made by ourselves.

## Introduction

For the first part of the course we are using the developer console in a webbrowser directly (I have used `node` in the command line).

### Primitive Types

#### Numbers in JS

Some languages there are different types of numbers, e.g. in some languages there is a different between storing an integer number and storing a decimal number.

This is different in JS. In JS we have only ONE number type.

- Positive numbers
- Negative numbers
- Whole numbers (integers)
- Decimal numbers

The above is represented by the same number type.

We can clear the console as follows.

```javascript
clear()
```

#### Simple Operations

A comment in JS are creates using `//`, thus

```javascript
// this is a comment
```

is a comment which will not be interpreted by the JS interpreter.

**Addition:**

```javascript
50 + 5
```

**Substraction:**

```javascript
90 - 1
```

**Multiplication:**

```javascript
111 * 111
```

**Division:**

```javascript
400 / 25
```

**Modulo:**

```javascript
27 % 2
```

**Exponentiation:**

```javascript
2 ** 2
```

In JS we have the usual order of operations, e.g. `3 - 9 * 2` is done as usual, thus it is of course different from writing `(3 - 9) * 2`.

There is a special numeric value in JS called `NaN` (Not a Number) which is a numeric value that represents somethings that is not... a number. For example

```javascript
0/0 // NaN
```

or

```javascript
NaN + 1 // NaN
```

There is another special number called `Infinity`. For example

```javascript
1/0 // Infinity
```

In JS we also have values for `0` and `-0`.

#### Variables

We can store a value and give it a name, so that we can

- recall it
- use it
- or change it later on

The basic syntax is as follows (there are actually more ways to do this but we are going to talk about the other versions later).

```javascript
let someName = value;
```

Here is an example how we use variables.

```javascript
let a = 4;
let b = 2;

a + b //6

// update variables

a = a - 1; // 3
```

Notice that writing

```javascript
a + 1
```

does of course not changing the value reference by `a` while writing 

```javascript
a = a + 1;
```
does.

We cannot use reserved keywords as variable names, thus

```javascript
let let = 10;
```

does not work.

It is not possible to redeclare a variable, thus

```javascript
let x = 0

let x = 0
```

throws an exception, namely

```javascript
Uncaught SyntaxError: Identifier `x` has already been declared
```

#### Unary Operators

Instead of writing

```javascript
let x = 0;
x = x + 10;
```

we can write

```javascript
let x = 0;
x += 10;
```

This notation is possible for substraction, multiplication and division, e.g.

```javascript
let x = 0;
x -= 1;
x += 1;
x /= 2;
x *= 2;
```

Since incrementing a counter by one is a very common operation, there is a special way to do this in JS using a so called unary operator. This looks as follows.

```javascript
let x = 0;
x++; //increments by 1
```

The same is possible for decrementing by one, e.g.

```javascript
let x = 0;
x--;
```

#### Constants

The keyword `const` works just like `let`, except you cannot change the value. Consider the following.

```javascript
const x = 10;
x += 1;
```

The above yields to

```javascript
Uncaught TypeError: Assignment to constant variable.
```

since we are trying to assign a new value to the constant `x` which is not allowed.

Notice that it is also not possible to redeclare the same name of a variable even if one of them is declared as `const` and the other as `let`, e.g.

```javascript
const x = 10;
let x = 10;
```

does also not work.

#### The Legacy of Var

Before `let` and `const`, `var` was the only way of declaring variables. These days, there isn't really a reason to use it.

We will discuss the exact reasons why it should not be used anymore later in this course.

#### Booleans

Booleans are simply true or false values (Yes or No, 1 or 0). For example

```javascript
let a = true;
let b = false;
```
We are going to use it all the time later in this course when we are talking about how to implement logic in JS.

#### Variables can change type

In most programming language, once a variable gets assigned a value, then this variable needs to always have the same type later on, e.g.

```javascript
let x = 10;
```

would mean that `x` must always stay a number in the future. This is not the case in JS. Variables can change type! For example

```javascript
let x = 10; // x is a number
x = false; // x is a boolean
```

The above is perfectly valid in JS.

This is actually one of the reasons why TypeScript exist. In TypeScript this is not possible.

#### Strings

In JS Strings are pieces of text, or strings of characters. We use single or double quotes.

```javascript
let name = "David";
let lastName = 'Scholz';
```

Notice that it is not allowed to mix them, e.g.

```javascript
let name = "David';
```

is not  valid. It is usually a good idea to be consistent in your code, meaning either always use double quotes or single quotes when you introduce strings.

Notice that it is allowed to use quotes inside quotes, e.g.

```javascript
let name = '"David"';
```

We can concatenate strings using the `+` symbol as follows.

```javascript
let name = "David";
let lastName = "Scholz";
let fullName = name + lastName;
```

Strings are indexed. Each character has a corresponding index (a positional number).

C H I C K E N
0 1 2 3 4 5 6

Each string has a property called `length` which returns the number of characters of a string.

```javascript
"hello".length // returns 5
```

We can use the indices of a string to access individual characters as follows.

```javascript
let name = "David"
name[0] // returns "D"
```

Notice that accessing an index that does not exist in the string returns `undefined`. It does not throw an exception. For example

```javascript
let name = "David"
name[110] // returns undefined
```

Notice that strings immutable in JS, thus

```javascript
let name = "David"
name[0] = "S"
```

does not change the value of `name` since a string is immutable.