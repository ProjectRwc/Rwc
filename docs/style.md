---
title: Style Guide for C-Style Languages
layout: default
---

C-Style languages include Java, JavaScript, C, C++, Rust, etc.

## Braces & Indentation
Indents are 4 spaces using the "one true brace style" (1TBS):
- Opening braces always belong on the same line as the code that created them -- do not put them on
their own line.
- Never use an inline version of control flow statements (`if`, `else`, `while`, etc.); always use
the block form instead (see example).

Statements which are too long to fit on one line (>100 characters) should wrap onto a new line, and
other statements may optionally be split into multiple lines for readibility.
When one statement goes onto a new line, that new line should be indented *twice* compared to the
first line.

### Example
```c
// Good
void handle_number(int my_long_number_name) {
    if (x < 0) {
        handle_negative(my_long_number_name);
    } else {
        my_long_number_name
                .doSomething()
                .doSomethingElse();
    }
}

// Bad!
void handle_number(int x) {
    if (x < 0) 
        handle_negative(x)
    else 
        my_long_number_name
        .doSomething()
        .doSomethingElse();
}
```

## Layout
There should be no more than two empty lines between non-empty lines. There should not be more than
100 characters on one line.

## Naming
- Acronyms/abbreviations: treat as one word, i.e. write `PidController` rather than `PIDController`.
- Generics: Use a single letter (such as `T`) if the meaning is obvious, or `T` followed by a type
name, eg. `TScale`, otherwise.
- GitHub Repository Naming: `PascalCase`
### C/C++/Rust
- Functions, variables: `snake_case`
- Types (classes, structs, etc.): `PascalCase`
- Constants: `SCREAMING_SNAKE_CASE`
### Java/JavaScript/TypeScript
- Functions, variables: `camelCase`
- Types (classes, prototypes, interfaces, etc.): `PascalCase`
    - **Java**/**TypeScript**: Do not prefix interfaces with `I`. Instead, if you need an interface
    and a class with the same name, use that name for the interface and use that name with `Impl`
    appended to the end for the class. Ex: `interface NumConsumer { ... }
    class NumConsumerImpl { ... }`
- Compile-time constants: `SCREAMING_SNAKE_CASE`
### Web
- CSS classes: `camelCase`
- String values: `camelCase`
    - Example: ```ts
        const action = 'createPage';
    ```
- Do not use `var`. Use `let` instead.
- Do not use `function <functionName>() { ... }`. Use `const <functionName> = () => { ... }`
instead. (Never use the `function` keyword.)
- JavaScript allows you to omit semicolons in some cases. Always put the semicolon anyways.

## Argument Order
Destination first, source second. Example:
```
const copyData = (destination, source) => {
    ...
}
```