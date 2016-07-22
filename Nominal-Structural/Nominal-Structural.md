# Proposal for Nominal & Structural typing in Proton

Introduction
============

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
========

Structu-Nominal Type System
---------------------------

Alias
-----

Grammar
=======
