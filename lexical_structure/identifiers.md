# Identifiers

<div style="background-color: rgba(255, 255, 255, 0.15);">
<strong>Lexer</strong>

IDENTIFIER_OR_KEYWORD: <br/>
 &nbsp;&nbsp; [ `A` - `z` ] [ `A` - `z` | `0` - `9` | `_` ]* <br/>
 &nbsp;&nbsp; | `_` [ `A` - `z` | `0` - `9` | `_` ]+

IDENTIFIER: <br/>
 &nbsp;&nbsp; IDENTIFIER_OR_KEYWORD except [strict](keywords.md#strict-keywords) and [reserved](keywords.md#reserved-keywords) keywords.
</div>

An identifier is a non-empty ASCII string which is used to name [items](../items/items.md), [variables](../statements_and_expressions/statements.md#`let`-statements) and [types](../types.md).

An identifier can be of the following forms:

Either:

 * The first character is a letter.
 * The remaining characters are alphanumeric or `_`.

or:

 * The first character is `_`.
 * The remaining characters are alphanumeric or `_`.
 * The identifier is more than one character: `_` alone is not an identifier.

These are valid identifiers:

* `lapis`
* `john1234`
* `a4`
* `did_i_eat_salad`
* `Tomato`
* `T_o_M_a_T_o` <!-- (although I wouldn't recommend this) -->
* `_red`
* `__blue`

These are invalid identifiers:

* `4a`
* `is-this-home`
* `_`
