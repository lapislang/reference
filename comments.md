# Comments

## Single line comments

Single line comments can be placed anywhere in the code; they are prefixed by `//`; anything after the `//` will be considered as part of the comment.

Example:

```lapis
// This is a single line comment.
```

## Multiline comments

Multiline comments begin and end with the following statements: `/*` and `*/`.
Everything inside these two statements will be considered as comment.

This is what such comments may look like:

```lapis
/* 
 * This is a multi line comment!
 */

/* Multiline comments can also be used inline, which enables you to write code after it */
```

The asterisks `*` at the beginning of each line are not mandatory, but are recommended for readability.

## Documentation comments

Documentation comments are just like multiline comments, except that they start with the `/*!` statement.
They are only written outside of function bodies and are bound to a function, a variable declaration, etc.

They are exported in the header files, and can be used to generate easily readable documentation.

The content of a documentation comment is written in [Markdown](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).

Additionally, there are special fields that can be added to a documentation comment, which are prefixed by `@`.
It allows you to define the properties of a function/object/variable.

| Field       |  Description                                                                                                                 |  Syntax                           |
|-------------|------------------------------------------------------------------------------------------------------------------------------|-----------------------------------|
| `@deprecated` | Indicates that this API should no longer be used.                                                                          | `@deprecated`                       |
| `@param`      | Appends a parameter with the specified `parameter-name` followed its `description` to the "Parameters" section of the API. | `@param parameter-name description` |
| `@return`     | Used to describe the value returned by an function.                                                                        | `@return description`               |
| `@see`        | Adds a "See also" heading with a link or text entry pointing to `reference`.                                               | `@see reference`                    |
| `@since`      | Defines since which version a function/variable/etc is available.                                                          | `@since release`                    |
| `@version`    | Defines the current version of an API.                                                                                     | `@version release`                  |

Here is an example of such a documentation comment:

```lapis
/*!
 * My wonderful API, written in Lapis!
 *
 * @version 1.2.0
 * @since 1.0.0
 */
```

## Licence comments

