# Statements

A *statement* is a component of a block.

## Summary

1. [Variables](#variables)
    1. [Variable declaration](#variable-declaration)
    2. [Variable assignement](#variable-assignement)
    3. [Scope](#scope)

## Variables

Variables allow you to store the result of an expression or of a function to use it later in your code.

### Variable declaration

Variables are declared using the `let` keyword.
It may be followed by the type of the variable, though the compiler will often deduce its type.

This is then followed by the name of the variable.

This if followed by the `=` operator and an expression, whose result will be put in the variable.

Here are a few examples:

```lapis
let x = 3; // the compiler will decide which type `x` will have
let i8 y = 4; // `y` will have as type `i8`
```

Later on, new values may be given to a variable with the [variable assignement operator](expressions/operator_expressions#variable-assignement)

### Scope

Variables are *scoped*, that is, they can only be accessed in their *scope*.
A scope is defined by a set of curly brackets (`{`, `}`): it may be the body of an `if`/`else` statement, or the body of a function.
The scope to which a variable is bound is the deepest scope in which the variable was declared.

If you try to access a variable outside of its scope, the compiler will give you an error message.

On top of that, variables **cannot** be accessed before their declaration **and their first assignement**.
A variable **cannot** have the same name as a previously defined variable in the same scope **or in a parent scope**.

Here is an example demonstrating this:

```lapis
fn main() {
  let a = 3; // <- `a` is declared and can now be used throughout the `main` function

  if (a == 3) { // <- here `a` can be accessed as usual
    let b = a * 2;

    let a = "bits"; // <- ERROR: we cannot re-declare `a`
  }

  b = b + 1; // <- ERROR: `b` isn't defined in this scope, so the compiler prints an error

  a = c / 2; // <- ERROR: `c` hasn't been defined yet
  let i32 c;
}
```

## Expression statements

<!-- TODO -->
