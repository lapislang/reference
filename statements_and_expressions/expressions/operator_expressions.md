# Operator expressions

<div style="background-color: rgba(255, 255, 255, 0.15);">
<strong>Syntax</strong>

*OperatorExpression*: <br />
 &nbsp;&nbsp; [*NegationExpression*](#negation-expression) <br />
 &nbsp;&nbsp; | [*ComparisonExpression*](#comparison-operators) <br />
 &nbsp;&nbsp; | [*TypeCastExpression*](#type-cast-expression)
</div>

Operators are defined for built in types by the Lapis language.
Many of the following operators can also be overloaded (WIP).

## Summary
 1. [Negation expression](#negation-expression)
 2. [Comparison operators](#comparison-operators)
 3. [Type cast expression](#type-cast-expression)

## Negation expression

<div style="background-color: rgba(255, 255, 255, 0.15);">
<strong>Syntax</strong>

*NegationExpression*: <br />
 &nbsp;&nbsp; `!` *Expression*
</div>

WIP

## Comparison operators

<div style="background-color: rgba(255, 255, 255, 0.15);">
<strong>Syntax</strong>

*ComparisonExpression*: <br />
 &nbsp;&nbsp; *Expression* `==` *Expression* <br />
 &nbsp;&nbsp; | *Expression* `!=` *Expression* <br />
 &nbsp;&nbsp; | *Expression* `>` *Expression* <br />
 &nbsp;&nbsp; | *Expression* `<` *Expression* <br />
 &nbsp;&nbsp; | *Expression* `>=` *Expression* <br />
 &nbsp;&nbsp; | *Expression* `<=` *Expression*
</div>

WIP

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