# Proposal for Nominal & Structural typing in Proton

##### Status: Draft
##### Submitted: 2016-07-??
##### Author: Soren Palmund / Miista & jaxrtech

---

Introduction
------------

This proposal will introduce a mixed type system comprised of nominal and
structural typing (for giggles let's call it _structu-nominal_).

The nominal type system looks only if the names of the types matches
whereas the structural type system is only concerned with whether
the structure of the types matches.

Also this proposal will introduce syntax for creating an type alias.
That is, giving a new name to an already named type.

This proposal is based on the thoughts by @jaxrtech posted in a Gist
here: https://gist.github.com/jaxrtech/591555b239a97844183ba48da8d82339

Proposal
--------

### Structu-Nominal Type System

### Alias

In a further effort to deal with global namespace clutter, we propose to
introduce the concept of type alias.
That is, giving an already name type a new name.

The purpose of a type alias is to avoid creating an entirely new type
when a type exists that would fill the purpose -- but that type is not
immediately self-documenting.

Assume that type `String` exists, then the following:

    alias Name = String

would make type `Name` an alias for `String` meaning that in places where
a `Name` is the parameter type `String` would be accepted and vice versa.

Assume the following function:

    function (name: String) { ... }

From the name of the parameter (`name`) it is obvious that type `String`
is intended to be used for the name.
If, however, the parameter was called something like `person_directory_parent_guy`
then it wouldn't be immediately obvious.

This is where the self-documenting part of a type alias comes in.
Assume now that we create the following type alias:

    alias Name = String

We can then use this type in place of `String` as such:

    function (name: Name) { ... }

Now, even if the name of the parameter changes the type makes the function
declaration self-documenting.

Implementation
--------------

### Grammar
