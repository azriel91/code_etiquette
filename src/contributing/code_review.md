# Code Review

Code review lets someone else make sure what you write is correct before accepting it.

## Changes

What you change normally would include:

* Code
* Tests
* Documentation

## Commits

Ideally, changes should be separated by type to make it easier for reviewing:

* Whitespace / formatting changes ([example](https://github.com/conan-io/conan/pull/110/commits/d7a73c14f4672c0e3489991a0248d449ddc4e6a6))
* Logic changes ([example](https://github.com/conan-io/conan/pull/110/commits/ac2c98df9bf9a4eb5d9f651b42999bdfdf08ada3))
* Refactoring (pushing code around)

This makes it easier for the reviewer. Normally I group the changes by commit ([example](https://github.com/conan-io/conan/pull/110/commits)); some repositories like to group whitespace changes into a separate PR so they can see the logic/refactoring changes together.
