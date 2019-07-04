# Comments

## Single line comment

Single line comments can be place anywhere in the code, everything after the `//` prefix will be considered as comment.

Example:

```lapis
// This is a single line comment.
```

## Multi line comment

Multi line comments have begin and end statements: `/*` and `*/`.
Everything inside the statements will be considered as comment.

Example:

```lapis
/* 
 * This is a multi line comment!
 */

/* But also can be used inline so we can write code after the comment on the same line. */
```

## Documentation comment

Documentation comments are very similar with multi line comments: they have a begin and end statements.
The difference is the begin statements which is `/*!`.

Documentation comments cannot be inside function scopes, they are only available before every statement outside a function.
They are also assigned to a statement like a function declaration, a variable declaration, etc...

They are exported in the header files, and can be used to generate human readable documentation.

To format the content of a documentation comment, Markdown should be used.

There is special fields which their prefix is `@`. It allows to define properties.

| Field       |  Description                                                                                                           |  Syntax                           |
|-------------|------------------------------------------------------------------------------------------------------------------------|-----------------------------------|
| @deprecated | Indicates that this API should no longer be used.                                                                      | @deprecated                       |
| @param      | Adds a parameter with the specified parameter-name followed by the specified description to the "Parameters" section." | @param parameter-name description |
| @return     | Defines the description of the value returned by the API.                                                              | @return description               |
| @see        | Adds a "See also" heading with a link or text entry that points to reference.                                          | @see reference                    |
| @since      | Defines since which version the function/variable/etc is available.                                                    | @since release                    |
| @version    | Defines the current version of the API.                                                                                | @version release                  |

Example:

```lapis
/*!
 * API description.
 *
 * @version 1.2.0
 * @since 1.0.0
 */
```

## Licence comment

