# Comments

All programmers should want to make their code easy to understand, but sometimes extra explanation is warranted. In these cases, programmers leave notes, or *comments*, in their code source. It can also be used for documentation generation or licensing. The compiler will ignore basic comments, but people reading the source code may find them useful.

## Summary

 1. [Single line comments](#single-line-comments)
 2. [Multiline comments](#multiline-comments)
 3. [Documentation comments](#documentation-comments)
 4. [License comments](#license-comments)

## Single line comments

Single line comments can be placed anywhere in the code; they are prefixed by `//`. Anything after `//` will be considered as part of the comment.

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

/* Multiline comments can also be used inline, which allows you to write code after it */
```

The asterisk `*` at the beginning of each line is not mandatory, but is recommended for readability.

## Documentation comments

Documentation comments are just like multiline comments, except that they start with the `/*!` statement.
They are only written outside of function bodies and are bound to a function, a variable declaration, etc.
They may be exported in header files by the compiler and can be used to generate easily readable documentation.

If misplaced, the compiler will warn the programmer and ignore them.

The content of a documentation comment is written in [Markdown](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).

Additionally, there are special fields that can be added to a documentation comment, which are prefixed by `@`.
They allow you to define the properties of a function/object/variable.

| Field         |  Description                                                                                                               |  Syntax                             |
|---------------|----------------------------------------------------------------------------------------------------------------------------|-------------------------------------|
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

## License comments

License comments are like multiline comments, except that they start with the `/*?` statement.
They are only written at the beginning of a file, they are also exported in header files by the compiler.
The license comment allows you to write the license under which your file is licensed.

If misplaced and the warning option `misplaced_license_comments` is enabled, then the compiler will warn the programmer about the misplacement.

Here is a quick example with a MIT license:

```lapis
/*?
 * Copyright © year author
 *
 * This file is part of project-name.
 *
 * Licensed under the MIT license. For more information,
 * see the LICENSE file.
 */
```
