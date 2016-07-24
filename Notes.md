# Notes

This is just a list of features/suggestions that should probably
be considered at some point in the future.

### Concurrency

Handling the ABA problem

### Multi-threading

### Module system

One way of reducing global namespace cluttering

### Launching the app

How do we want the app to be started?

* By using a `main` method?
* By declaring one file to be the main file? (Like Swift[^swift-main])

### Scoping

Scoping is partially handled by the expanded `let` expression.

#### Block Scoping

Do we want to use braces or significant whitespace?
If we choose to use braces, do we allow optional braces around single-line
expressions?

### Generics

Do we want generics in the language?
Generics reduce the amount of code that is written for common cases.

If we choose to have generics in the language, do we then want reified generics?
That is, to have the type be available at runtime.

[^swift-main]: Only the `main.swift` file can contain top-level code

