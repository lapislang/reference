# Operator expressions

<div style="background-color: rgba(255, 255, 255, 0.15);">
<strong>Syntax</strong>

*OperatorExpression*: <br/>
 &nbsp;&nbsp; [*NegationExpression*](#negation-operators) <br/>
 &nbsp;&nbsp; | [*ComparisonExpression*](#comparison-operators) <br/>
 &nbsp;&nbsp; | [*LogicalExpression*](#logical-operators) <br/>
 &nbsp;&nbsp; | [*TypeCastExpression*](#type-cast-expression) <br/>
 &nbsp;&nbsp; | [*AssignmentExpression*](#assignment-expression) <br/>
 &nbsp;&nbsp; | [*CompoundAssignmentExpression*](#compound-assignment-expressions)
</div>

Operators are defined for built in types by the Lapis language.
Many of the following operators can also be overloaded (WIP).

## Summary
 1. [Negation operators](#negation-operators)
 2. [Comparison operators](#comparison-operators)
 3. [Logical operators](#logical-operators)
 4. [Type cast expression](#type-cast-expression)
 5. [Assignment expression](#assignment-expression)
 6. [Compound assignment expressions](#compound-assignment-expressions)

## Negation operators

<div style="background-color: rgba(255, 255, 255, 0.15);">
<strong>Syntax</strong>

*NegationExpression*: <br/>
 &nbsp;&nbsp; `-` *Expression* <br/>
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

*ComparisonExpression*: <br/>
 &nbsp;&nbsp; *Expression* `==` *Expression* <br/>
 &nbsp;&nbsp; | *Expression* `!=` *Expression* <br/>
 &nbsp;&nbsp; | *Expression* `>` *Expression* <br/>
 &nbsp;&nbsp; | *Expression* `<` *Expression* <br/>
 &nbsp;&nbsp; | *Expression* `>=` *Expression* <br/>
 &nbsp;&nbsp; | *Expression* `<=` *Expression* <br/>
 &nbsp;&nbsp; | *Expression* `<=>` *Expression* <br/>
</div>

Comparison operators compare two operands and return a boolean value, except for the `<=>` operator which return an `i8` value.

WIP

## Logical operators

<div style="background-color: rgba(255, 255, 255, 0.15);">
<strong>Syntax</strong>

*LogicalExpression*: <br/>
 &nbsp;&nbsp; *Expression* `||` *Expression* <br/>
 &nbsp;&nbsp; | *Expression* `&&` *Expression*
</div>

Two or more relations can be logically joined using the logical operators "and" and "or".
The operator `||` represents the logical "or", and the operator `&&` represents the logical "and".

The operators `||` and `&&` may be applied to operands of boolean type. So the operators cannot be overloaded.

The right-hand operand is only evaluated when the left-hand operand does not already determine the result of the expression.
For the operator `||`, the right-hand operand is evaluated if the left-hand operand evaluates to `false`.
For the operator `&&`, the right-hand operand is evaluated if the left-hand operand evaluates to `true`.

Here's an example:
```lapis
let x = false || true; // true
let y = false && true; // false
let z = (2 == 2) && true; // true
```

## Type cast expression

<div style="background-color: rgba(255, 255, 255, 0.15);">
<strong>Syntax</strong>

*TypeCastExpression*: <br/>
 &nbsp;&nbsp; *Expression* `as` [*Type*](../../types.md)
</div>

A type cast expression is denoted with the binary operator `as`.

Executing an `as` expression casts the value on the left-hand side to the type of the right-hand side.

An example of an `as` expression:
```lapis
5 as i8
```

See: [Type#Type casting](../../types.md#type-casting) for further information.

## Assignment expression

<div style="background-color: rgba(255, 255, 255, 0.15);">
<strong>Syntax</strong>

*AssignmentExpression*: <br/>
 &nbsp;&nbsp; *Expression* `=` *Expression*
</div>

## Compound assignment expressions

<div style="background-color: rgba(255, 255, 255, 0.15);">
<strong>Syntax</strong>

*CompoundAssignmentExpression*: <br/>
 &nbsp;&nbsp; *Expression* `+=` *Expression* <br/>
 &nbsp;&nbsp; | *Expression* `-=` *Expression* <br/>
 &nbsp;&nbsp; | *Expression* `*=` *Expression* <br/>
 &nbsp;&nbsp; | *Expression* `/=` *Expression* <br/>
 &nbsp;&nbsp; | *Expression* `>>=` *Expression* <br/>
 &nbsp;&nbsp; | *Expression* `<<=` *Expression* <br/>
 &nbsp;&nbsp; | *Expression* `|=` *Expression* <br/>
 &nbsp;&nbsp; | *Expression* `&=` *Expression* <br/>
 &nbsp;&nbsp; | *Expression* `^=` *Expression* <br/>
</div>
