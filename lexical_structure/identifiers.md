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
