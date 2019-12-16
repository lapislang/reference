# Type aliases

<div style="background-color: rgba(255, 255, 255, 0.15);">
<strong>Syntax</strong>

*TypeAlias*: <br />
 &nbsp;&nbsp; `type` [IDENTIFIER](../lexical_structure/identifiers.md) *Generics*? `=` [*Type*](../types.md) `;`
</div>

A *type alias* defines a new name for an existing [*type*](../types.md).
Type aliases are declared with the keyword `type`.

The following example defines the type `Point` as an alias for the type `(i64, i64)`:
```lapis
type Point = (i64, i64);
let a: Point = (20, -50);
```
