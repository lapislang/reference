# Statements

<div style="background-color: rgba(255, 255, 255, 0.15);">
<strong>Syntax</strong>

*Statement*: <br />
 &nbsp;&nbsp; [*Item*](../items/items.md) <br />
 &nbsp;&nbsp; | [*LetStatement*](#let-statements) <br />
 &nbsp;&nbsp; | [*ExpressionStatement*](#expression-statements)
</div>

A *statement* is a component of a block.

## Summary

1. [Declaration statements](#declaration-statements)
    1. [Item statements](#item-statements)
    2. [`let` statements](#`let`-statements)
2. [Expression statements](#expression-statements)

## Declaration statements

### Item statements

### `let` statements

<div style="background-color: rgba(255, 255, 255, 0.15);">
<strong>Syntax</strong>

*LetStatement*: <br />
 &nbsp;&nbsp; `let` [*Type*](../types.md)? [IDENTIFIER](../lexical_structure/identifiers.md) (`=` *ExpressionWithoutBlock*)? `;`
</div>

A *`let` statement* is a statement which declares a new variable.

It is defined by the `let` keyword followed optionally by the variable's [*type*](../types.md), then followed by the IDENTIFIER of the variable then the optional [assignment expression](expressions/operator_expressions.md#assignment-expression): `=` followed by an *expression*.

When no [*type*](../types.md) is specified, the compiler will infer the type, or will signal an error if not enough information is given to infer the type.

## Expression statements

<div style="background-color: rgba(255, 255, 255, 0.15);">
<strong>Syntax</strong>

*ExpressionStatement*: <br />
 &nbsp;&nbsp; *ExpressionWithoutBlock* `;` <br />
 &nbsp;&nbsp; | *ExpressionWithBlock*
</div>

An *expression statements* is an statement which evaluates an *expression* and ignore its result.

<!-- @TODO: delete the rest of the file -->

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

Later on, new values may be given to a variable with the [assignement expression](expressions/operator_expressions#assignement-expression).

### Scope

Variables are *scoped*, that is, they can only be accessed in their *scope*.
A scope is defined by a set of curly brackets (`{`, `}`): it may be the body of an `if`/`else` statement, or the body of a function.
The scope to which a variable is bound is the deepest scope in which the variable was declared.

If you try to access a variable outside of its scope, the compiler will give you an error message.

On top of that, variables **cannot** be accessed before their declaration.
<!-- **and their first assignement**.-->
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
