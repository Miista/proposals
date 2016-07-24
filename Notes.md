# Notes

This is just a list of features/suggestions that should probably
be considered at some point in the future.

### Concurrency

Handling the ABA problem

### Multi-threading

### Module system

One way of reducing global namespace cluttering.
A module or library system is also a way to group related types.

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

#### Variance

We should also think about whether to support co- and contravariance.
Some languages have only invariant arrays and collections.[^swift-variance]

#### Abstract Types

~ @jaxrtech

Instead of making the generics types parameterized, you can treat the generic
type as a member of the enclosing type.[^scala-abstract-types][^ocaml-module-system]

This effectively avoids dealing with co- and contravariance.[^scala-abstract-types-explained]

### Functional Programming

* Currying
* Partial application

### Documentation (ala Javadoc)

In-language documentation ala Javadoc.

### Overloading

* Method/function overloading
* Operator overloading (this could turn out nasty unless handled properly)

### Subtyping

Should we go with object-oriented, subtyping through inheritance is probably a must.
However, even if we do not go with object-oriented, we could still allow
subtyping between types.

For instance, `Int` could be a subtype of `Number` such that a function
could declare to work with just `Number`s.


### Footnotes

[^swift-main]: Only the `main.swift` file can contain top-level code   
[^swift-variance]: Swift comes to mind here  
[^scala-abstract-types-docs]: See [Scala's abstract types][AbstractTypes-Scala]  
[^ocaml-module-system]: See [OCaml's module system][AbstractTypes-OCaml]  
[^scala-abstract-types-explained]:
  See [this StackOverflow question][AbstractTypes-StackOverflow]
  which explains the difference between parameterized generics and abstract
  types in Scala. 

  Example from question quoted below:

  > For example,
  > 
  >     abstract class Buffer {
  >       type T
  >       val element: T
  >     }
  > 
  > rather that generics, for example,
  > 
  >     abstract class Buffer[T] {
  >       val element: T
  >     }


 [AbstractTypes-Scala]: http://docs.scala-lang.org/tutorials/tour/abstract-types.html
 [AbstractTypes-StackOverflow]: http://stackoverflow.com/q/1154571/809572
 [AbstractTypes-OCaml]: https://realworldocaml.org/v1/en/html/functors.html#a-bigger-example-computing-with-intervals
