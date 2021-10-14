# Wes Bos - ES6 For Everyone Course

## 1. About var, let & const

**Variable declaration**

There are 3 ways to declare variables in JavaScript:
- var
- let
- const

**var**

Using "var" we can *redefine or update* the same variable.

How they are scoped?
Function Scoped
var variables declared inside the function are available inside the function only.
They cannot be accessed outside the function in which they are declared.
They are the local variables of the function only.

OR

Global/Window Scoped
var variables declared outside the function are globally scoped.
They can be accessed everywhere.
Avaiable to entire Window and we can access it directly or by window.variableName.

**let/const**

They are *block* scoped.
It means they are only available inside the block in which they are declared.

We *cannot redeclare* the same variable using let/const in the same scope.

We can update let variables, but cannot update const variables.

**IIFE (Immediately Invoked Function Expression)**

Variables declared here won't be leaked to Global/Window scope.

**Temporal Dead Zone**

We can access the variables declared with var before their declaration point, but their value will be "undefined".

We cannot access the variables declared with let/const before their declaration point, it will give an error.
So in this case its kinda "temporal dead zone" for such variables.

**`const` creates an immutable binding**

ES6 `const` does not indicate that a value is 'constant' or 'immutable'.
A `const` value can definitely change.
Following is the perfectly valid ES6 code that does not throw an exception:

```
const foo = {};
foo.bar = 42;
console.log(foo);
foo.bar = 50;
console.log(foo);
```

The only thing that's immutable here is the binding.
`const` assigns a value `{}` to a variable `foo`, and guarantees that no rebinding will happen.

A Primitive value assigned to a `const` variable cannot be changed.
An Object assignment to a `const` cannot be changed, but we can change the Object itself by updating its properties.

**Thumbrules for using `var`, `let` & `const`**

1. use `const` by default
2. only use `let` if rebinding is required OR use `let` if you want to change the value later
3. don't use `var` in ES6

Some more,
1. Use `var` for top-level variables that are shared across many (especially larger) scopes.
2. Use `let` for localized variables in smaller scopes.
3. Refactor `let` to `const` only after some code has been written and you are reasonably sure that you have got a case where there should not be variable reassignment.

Read article - [ES2015 `const` is not about immutability](https://mathiasbynens.be/notes/es6-const)
