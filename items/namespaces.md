# Namespaces

<div style="background-color: rgba(255, 255, 255, 0.15);">
<strong>Syntax</strong>

*Namespace*: <br />
 &nbsp;&nbsp; `namespace` [PATH](../lexical_structure/identifiers.md) `{` [*Item*](./items.md)\* `}`
</div>

*Namespaces* provide a method for preventing name conflicts in large projects.

*Namespace* definitions are only allowed at *namespace* scope, including the global scope. 

[*Items*](./items.md) declared inside a *namespace* block are placed in a named scope that prevents them from being mistaken for identically-named [*items*](./items.md) in other scopes.

Multiple *namespace* blocks with the same name are allowed. All declarations within those blocks are declared in the named scope.

## Summary

 1. [Namespaces](#namespaces)
 2. [Namespace aliases](#namespace-aliases)

## Namespace aliases

<div style="background-color: rgba(255, 255, 255, 0.15);">
<strong>Syntax</strong>

*NamespaceAlias*: <br />
 &nbsp;&nbsp; `namespace` [PATH](../lexical_structure/identifiers.md) `=` [PATH](../lexical_structure/identifiers.md) `;`
</div>

Considering `namespace ns_alias = ns_name;`, the new alias `ns_alias` provides an alternate method of accessign `ns_name`.

They are commonly used as a convenient shortcut for long or deeply-nested namespaces.

`ns_alias` must be a name not previously used. `ns_alias` is valid for the duration of the scope in which it is introduced. 
