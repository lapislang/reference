# Functions

<div style="background-color: rgba(255, 255, 255, 0.15);">
<strong>Syntax</strong>

*Function*: <br />
 &nbsp;&nbsp; `fn` *FunctionReturnType* [IDENTIFIER](../lexical_structure/identifiers.md) *Generics* `(` *FunctionParameters* `)` *FunctionQualifiers* [*BlockExpression*](../statements_and_expressions/expressions/block_expression.md)

*FunctionReturnType*: <br />
 &nbsp;&nbsp; [*Type*](../types.md)

*FunctionParameters*: <br />
 &nbsp;&nbsp; *FunctionParam*
</div>

A *function* consists of a block, along with a name and a set of parameters.

Functions are declared with the keyword `fn`.
Functions may declare a set of *input variables* as parameters and the *output type* of the value that the function will return to its caller once completed.
If the *output type* is `void` then the *output type* is optional.

Here are three examples of simple functions:

```lapis
fn i32 answer_to_life_the_universe_and_everything() {
    return 42;
}

/*!
 * Adds two numbers.
 *
 * @param a The number a.
 * @param b The number b.
 * @return The result of the addition between the number a and the number b.
 */
fn i32 add(i32 a, i32 b) {
    return a + b;
}

fn hello() {
    // Empty function.
}
```

## Summary

 1. [Functions & syntax](#functions)
 2. [Generic functions](#generic-functions)
 3. [Const functions](#const-functions)
 4. [Constexpr functions](#constexpr-functions)
 5. [Inline functions](#inline-functions)

## Generic functions

<!-- TODO -->

## Const functions

Const functions, or const methods, are methods of classes that cannot change the value of any of the class members.
They are defined with the `const` keyword preceding the classical function syntax.

They are the only methods of a class that can be called when its class instance is qualified as `const`.
They can only call const methods on member objects.

For instance:

```lapis
fn f64 get_length() const {
    return math::sqrt(this.x * this.x, this.y * this.y);
}
```

## Constexpr functions

Functions qualified with the `constexpr` keyword are const expr functions. *Const expr functions* can be called from within const contexts.
When called from a const context, the function is interpreted by the compiler at compile time. The interpretation happens in the environment of the compilation target and not the host.

For instance:

```lapis
fn i32 answer_to_life_the_universe_and_everything() constexpr {
    return 42;
}
```

## Inline functions

Inline functions are qualified with the `inline` keyword. *Inline functions* are a feature to reduce the execution time of a program.
At compile time, the call statement of *inline functions* will be replaced by the function's block expression.
It allows better execution time because it doesn't have to jump to another location to execute the function.

*Inline functions* may be ignored if the code inside the function is too long.

### Pros

- It speeds up the execution time.
- It avoids to pollute namespaces like macros do.

### Cons

- It increases the executable size due to code expansion, making it not useful in situations where there is few available memory
- *Inline functions* are resolved at compile time. Which means if you change the code of inlined function, you will need to recompile every part of the code using it to make sure it will be updated.

### Examples

```lapis
fn i32 add(i32 a, i32 b) inline {
    return a + b;
}

fn i32 call_add() {
    return add(2, 2);
}
```

Will be the same as the following code during runtime:

```lapis
fn i32 call_add() {
    return 2 + 2;
}
```
