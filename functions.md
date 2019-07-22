# Functions

```
Syntax:

Function:
  `fn` FunctionReturnType IDENTIFIER Generics `(` FunctionParameters `)` FunctionQualifiers BlockExpression

FunctionReturnType:
  Type

FunctionParam:
  FunctionParam
```

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

## Generic functions

<!-- TODO -->

## Const functions

Const functions, or const methods, are methods of classes that cannot change the value of any of the class members.
They are defined with the `const` keyword preceding the classical function syntax.

They are the only methods of a class that can be called when its class instance is qualified as `const`.

For instance:

```lapis
const fn f64 get_length() {
    return math::sqrt(this.x * this.x, this.y * this.y);
}
```

## Constexpr functions

Functions qualified with the `constexpr` keyword are const expr functions. *Const expr functions* can be called from within const contexts.
When called from a const context, the function is interpreted by the compiler at compile time. The interpretation happens in the environment of the compilation target and not the host.

