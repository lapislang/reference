# Types

From [Wikipedia](https://en.wikipedia.org/wiki/Data_type): `In computer science and computer programming, a data type or simply type is an attribute of data which tells the compiler or interpreter how the programmer intends to use the data.`

## Fundamental types

### Void type

`void` - type with an empty set of values. Arrays of `void` are disallowed.

### Boolean type

`bool` - type capable of holding one of the two values: `true` (1) or `false` (0).

### Integer types

|  Type  |  Size    |  Range                                                                                                      |  Meaning                  |
|--------|----------|-------------------------------------------------------------------------------------------------------------|---------------------------|
| `i8`   | 8 bits   | -128 .. 127                                                                                                 | 8-bits signed integer     |
| `u8`   | 8 bits   | 0 .. 255                                                                                                    | 8-bits unsigned integer   |
| `i16`  | 16 bits  | -32,768 .. 32,767                                                                                           | 16-bits signed integer    |
| `u16`  | 16 bits  | 0 .. 65,535                                                                                                 | 16-bits unsigned integer  |
| `i32`  | 32 bits  | -2,147,483,648 .. 2,147,483,647                                                                             | 32-bits signed integer    |
| `u32`  | 32 bits  | 0 .. 4,294,957,295                                                                                          | 32-bits unsigned integer  |
| `i64`  | 64 bits  | -9,223,372,036,854,775,808 .. 9,223,372,036,854,775,807                                                     | 64-bits signed integer    |
| `u64`  | 64 bits  | 0 .. 18,446,744,073,709,551,615                                                                             | 64-bits unsigned integer  |
| `i128` | 128 bits | -170,141,193,460,469,231,731,687,303,715,884,105,728 .. 170,141,183,460,469,231,731,687,303,715,884,105,727 | 128-bits signed integer   |
| `u128` | 128 bits | 0 .. 340,282,366,920,938,463,463,374,607,431,768,211,455                                                    | 128-bits unsigned integer |

Remark: 128 bits integers may not be available on every platform or on the first versions of Lapis.

### Floating types

|  Type  |  Size   |
|--------|---------|
| `f32`  | 32-bits |
| `f64`  | 64-bits |

## Additional basic types

### `usize`

The pointer-sized unsigned integer type.

The size of this primitive is how many bytes it takes to reference any location in memory. Its size will depend of the target.

## Complex types

Complex types, or tuples, represent a set of values.

A *complex type* is defined by types seperated by commas encapsulated by parentheses.

A quick example of a type holding an `i8` and an `usize`:
```lapis
(i8, usize)
```

## Type unions

(TODO)

## Type definition

Types can be user-defined with the `type` keyword.
It works as an assignement: the type keyword is followed by the name of the type then the `=` character and the value.

Here's a quick example with primitive types:

```lapis
type char = u8;
type char32 = u32;
type vec2 = (i32, i32);
```

