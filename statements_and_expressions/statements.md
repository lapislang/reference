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
 &nbsp;&nbsp; `let` [IDENTIFIER](../lexical_structure/identifiers.md) ((`:` [*Type*](../types.md))? `=` *ExpressionWithoutBlock* | `:` [*Type*](../types.md) (`=` *ExpressionWithoutBlock*)?) `;`
</div>

A *`let` statement* is a statement which declares a new <!--@TODO: set of variables instead--> variable.

It is defined with the `let` keyword then followed by the [IDENTIFIER](../lexical_structure/identifiers.md) of the variable. This is then optionally followed by the variable's [*type*](../types.md) with `:` before, then the optional [assignment expression](expressions/operator_expressions.md#assignment-expression): `=`, followed by an *expression*.

When no [*type*](../types.md) is specified, the compiler will infer the type, or will signal an error if not enough information is given to infer the type.

## Expression statements

<div style="background-color: rgba(255, 255, 255, 0.15);">
<strong>Syntax</strong>

*ExpressionStatement*: <br />
 &nbsp;&nbsp; *ExpressionWithoutBlock* `;` <br />
 &nbsp;&nbsp; | *ExpressionWithBlock*
</div>

An *expression statements* is a statement which evaluates an *expression* and ignore its result.
