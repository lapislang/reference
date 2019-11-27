# Memory model

## Primitives

Primitives are by default passed by value.
They can be referenced with through boxing.

## Objects

Objects (`struct` instances) are passed by reference.
The `copy` keyword may be used to override this behavior.

Objects may be referenced in several ways:

* [Unique reference](#unique-reference)
* [Plural reference](#plural-reference)

<!-- DRAFT:
Unique reference - `u&Type`, `u:Type`, `unique:Type`, `u#Type`, `Type#u`, `Type #u`, `unique Type`
Plural reference - `p&Type`, `p:Type`, `plural:Type`, `p#Type`, `Type#p`, `Type #p`, `plural Type`, `Type` (as default)

Also have a user-managed reference type?
Have cycle management, weak references?
-->

### Unique reference

Unique references guarantee that an object is only referenced once.

As variables, they are "fragile": if the variable is used for something else than (compatible) method calls or field lookups/writes, it will be consumed and the original variable will no longer be usable.

As fields, they can only be used to lookup/write inner fields, call inner methods.
They can be extracted through [destructive reading](https://tutorial.ponylang.io/reference-capabilities/consume-and-destructive-read.html#destructive-read), akin to `C++`'s `std::move` function (destructive reads, however, assign a new value to the field).

Uniquely referenced objects are cleared as soon as the reference falls out of scope.

Unique references can be promoted to plural references.

### Plural reference

Plural references allow an object to be referenced multiple times.

They are (as of right now) reference-counted.

<!-- Dear code reader, I (Shad) have been thinking about a memory management model extending reference counting. If you are interested, check out: https://github.com/adri326/bound-lifetimes-poc -->
