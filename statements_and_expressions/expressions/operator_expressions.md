# Operator expressions

<div style="background-color: rgba(255, 255, 255, 0.15);">
<strong>Syntax</strong>

*OperatorExpression*: <br />
 &nbsp;&nbsp; [*NegationExpression*](#negation-operators) <br />
 &nbsp;&nbsp; | [*ComparisonExpression*](#comparison-operators) <br />
 &nbsp;&nbsp; | [*TypeCastExpression*](#type-cast-expression)
</div>

Operators are defined for built in types by the Lapis language.
Many of the following operators can also be overloaded (WIP).

## Summary
 1. [Negation operators](#negation-operators)
 2. [Comparison operators](#comparison-operators)
 3. [Logical operators](#logical-operators)
 4. [Type cast expression](#type-cast-expression)

## Negation operators

<div style="background-color: rgba(255, 255, 255, 0.15);">
<strong>Syntax</strong>

*NegationExpression*: <br />
 &nbsp;&nbsp; `-` *Expression* <br />
 &nbsp;&nbsp; `!` *Expression*
</div>

Negation operators are two unary operators. 
This table summarizes the behavior of them on primitive types.

They are not overloadable.

|  Symbol  |  Integer    |  Boolean    |  Floating point  |
|----------|-------------|-------------|------------------|
|   `-`    | Negation*   |             | Negation         |
|   `!`    | Bitwise NOT | Logical NOT |                  |

\* Only for signed integer types.

## Comparison operators

<div style="background-color: rgba(255, 255, 255, 0.15);">
<strong>Syntax</strong>

*ComparisonExpression*: <br />
 &nbsp;&nbsp; *Expression* `==` *Expression* <br />
 &nbsp;&nbsp; | *Expression* `!=` *Expression* <br />
 &nbsp;&nbsp; | *Expression* `>` *Expression* <br />
 &nbsp;&nbsp; | *Expression* `<` *Expression* <br />
 &nbsp;&nbsp; | *Expression* `>=` *Expression* <br />
 &nbsp;&nbsp; | *Expression* `<=` *Expression* <br />
 &nbsp;&nbsp; | *Expression* `<=>` *Expression* <br />
</div>

WIP

## Logical operators

## Type cast expression

<div style="background-color: rgba(255, 255, 255, 0.15);">
<strong>Syntax</strong>

*TypeCastExpression*: <br />
 &nbsp;&nbsp; *Expression* `as` [*Type*](../../types.md)
</div>

A type cast expression is denoted with the binary operator `as`.

Executing an `as` expression casts the value on the left-hand side to the type of the right-hand side.

An example of an `as` expression:
```lapis
5 as i8
```

See: [Type#Type casting](../../types.md#type-casting) for further information.