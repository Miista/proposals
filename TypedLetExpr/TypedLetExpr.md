# Typed `let` expression

##### Status: Draft
##### Submitted: YYYY-MM-DD
##### Author: Soren Palmund / Miista

---

## Introduction

Currently, `let` expressions do not allow for declaring the type of the variable
being initialized.
This proposal will attempt to fix this by allowing type declaration in `let`
expressions.
Furthermore this proposal will also introduce _type casting_ into `let` expressions.

## Proposal

The motivation for this proposal is being able to put a type to the initialized
variable in the `let` expression.

## Use cases

This proposal has several use cases some of which will be listed below.

### Declaring the type

Even though we might have inferred typing, sometimes the programmer knows best.
In this case, the programmer can explicitly declare the type of a variable as such:

    let a: Float = 0

or

    let a = 0 as Float

Which of the above two syntaxes is most easy on the eyes is up for discussion.
I am leaning towards the example #1, see paragraph on "Type casting".

### Type casting

There are cases in which one wants to "change" the type of a variable (either by
up-casting or down-casting it).
We would support this by allowing an already declared variable to be casted in
the `let` expression as such:

    let b = a as Double

This way `b` will hold the same value as `a` however its type will be `Double`
whereas type type of variable `a` is of type `Float`.

Given that type casting uses `let-as`, we probably should not allow this syntax
to also describe when a type is declared for a variable.
In other words, `let b = a as Double` should _only_ be used for type casting, and
not for declaring the type of `b`.

## Implementation

### Grammar

This is an optional body. Here you can paste grammar, code and anything
regarding how to implement your proposal. You can put here as many as
subsections as needed.
