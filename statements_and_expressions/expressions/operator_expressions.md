# Operator expressions

<div style="background-color: rgba(255, 255, 255, 0.15);">
<strong>Syntax</strong>

*OperatorExpression*: <br/>
 &nbsp;&nbsp; [*NegationExpression*](#negation-operators) <br/>
 &nbsp;&nbsp; | [*ArithmeticOrLogicalExpression*](#arithmetic-and-logical-binary-operators) <br/>
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
 2. [Arithmetic and logical binary operators](#arithmetic-and-logical-binary-operators)
 3. [Comparison operators](#comparison-operators)
 4. [Logical operators](#logical-operators)
 5. [Type cast expression](#type-cast-expression)
 6. [Assignment expression](#assignment-expression)
 7. [Compound assignment expressions](#compound-assignment-expressions)

## Negation operators

<div style="background-color: rgba(255, 255, 255, 0.15);">
<strong>Syntax</strong>

*NegationExpression*: <br/>
 &nbsp;&nbsp; `-` *Expression* <br/>
 &nbsp;&nbsp; | `!` *Expression*
</div>

Negation operators are two unary operators.
This table summarizes the behavior of them on primitive types.

They are not overloadable.

|  Symbol  |  Integer    |  Boolean    |  Floating point  |
|----------|-------------|-------------|------------------|
|   `-`    | Negation*   |             | Negation         |
|   `!`    | Bitwise NOT | Logical NOT |                  |

\* Only for signed integer types.

## Arithmetic and logical binary operators

<div style="background-color: rgba(255, 255, 255, 0.15);">
<strong>Syntax</strong>

*ArithmeticOrLogicalExpression*: <br/>
 &nbsp;&nbsp; *Expression* `+` *Expression* <br/>
 &nbsp;&nbsp; | *Expression* `-` *Expression* <br/>
 &nbsp;&nbsp; | *Expression* `*` *Expression* <br/>
 &nbsp;&nbsp; | *Expression* `/` *Expression* <br/>
 &nbsp;&nbsp; | *Expression* `%` *Expression* <br/>
 &nbsp;&nbsp; | *Expression* `//` *Expression* <br/>
 &nbsp;&nbsp; | *Expression* `<<` *Expression* <br/>
 &nbsp;&nbsp; | *Expression* `>>` *Expression* <br/>
 &nbsp;&nbsp; | *Expression* `|` *Expression* <br/>
 &nbsp;&nbsp; | *Expression* `&` *Expression* <br/>
 &nbsp;&nbsp; | *Expression* `^` *Expression* <br/>
</div>

WIP

|  Operator  |  Integer           |  Boolean    |  Floating point    |
|------------|--------------------|-------------|--------------------|
| `+`        | Addition           | Logical OR  | Addition           |
| `-`        | Subtraction        |             | Subtraction        |
| `*`        | Multiplication     | Logical AND | Multiplication     |
| `/`        | Division           |             | Division           |
| `%`        | Remainder          |             | Remainder          |
| `//`       | Euclidean division |             | Euclidean division |
| `<<`       | Left shift         |             |                    |
| `>>`       | Right shift        |             |                    |
| `|`        | Bitwise OR         | Logical OR  |                    |
| `&`        | Bitwise AND        | Logical AND |                    |
| `^`        | Bitwise XOR        | Logical XOR |                    |

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

The `=` operator is used to assign a value to a variable.
Its right-hand term is an expression and its left-hand term is where the data will be written.

The result of that expression will be put in the variable, assuming it is of the right type (otherwise the compiler will print out an error).

```lapis
let x = 3;

x = 5; // x will be 5

x = x * 2; // x will become 10
```

## Compound assignment expressions

<div style="background-color: rgba(255, 255, 255, 0.15);">
<strong>Syntax</strong>

*CompoundAssignmentExpression*: <br/>
 &nbsp;&nbsp; *Expression* `+=` *Expression* <br/>
 &nbsp;&nbsp; | *Expression* `-=` *Expression* <br/>
 &nbsp;&nbsp; | *Expression* `*=` *Expression* <br/>
 &nbsp;&nbsp; | *Expression* `/=` *Expression* <br/>
 &nbsp;&nbsp; | *Expression* `%=` *Expression* <br/>
 &nbsp;&nbsp; | *Expression* `//=` *Expression* <br/>
 &nbsp;&nbsp; | *Expression* `>>=` *Expression* <br/>
 &nbsp;&nbsp; | *Expression* `<<=` *Expression* <br/>
 &nbsp;&nbsp; | *Expression* `|=` *Expression* <br/>
 &nbsp;&nbsp; | *Expression* `&=` *Expression* <br/>
 &nbsp;&nbsp; | *Expression* `^=` *Expression* <br/>
</div>

The `+`, `-`, `*`, `/`, `%`, `//`, `>>`, `<<`, `|`, `&` and `^` operators may be composed with the `=` operator.
The expression `x OP= n` is equivalent to `x = x OP n`, as it can be seen on the equivalence table:

| Substitution | Equivalent                    |
|--------------|-------------------------------|
| `x += n`     | `x = x + n`                   |
| `x -= n`     | `x = x - n`                   |
| `x *= n`     | `x = x * n`                   |
| `x /= n`     | `x = x / n`                   |
| `x %= n`     | `x = x % n`                   |
| `x //= n`    | `x = x // n`                  |
| `x >>= n`    | `x = x >> n` (bitshift right) |
| `x <<= n`    | `x = x << n` (bitshift left)  |
| `x |= n`     | `x = x | n` (bitwise OR)      |
| `x &= n`     | `x = x & n` (bitwise AND)     |
| `x ^= n`     | `x = x ^ n` (bitwise XOR)     |

All of these expressions always has the [unit type](../../types.md).
These operators can all be overloaded.
