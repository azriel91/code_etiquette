# Git Workflow

## Changes

Ideally, changes should be separated by type to make it easier for reviewing:

* Whitespace / formatting changes ([example](https://github.com/conan-io/conan/pull/110/commits/d7a73c14f4672c0e3489991a0248d449ddc4e6a6))
* Logic changes ([example](https://github.com/conan-io/conan/pull/110/commits/ac2c98df9bf9a4eb5d9f651b42999bdfdf08ada3))
* Refactoring (pushing code around)

This makes it easier for the reviewer. Normally I group the changes by commit ([example](https://github.com/conan-io/conan/pull/110/commits)); some repositories like to group whitespace changes into a separate PR so they can see the logic/refactoring changes together.

This is analogous to:

```bash
y = (x + 1)(x + 2)

# when x = 5
# type-separated changes:
y = (x + 1)(x + 2)
  = 6 * 7
  = 42

# bits of each mixed together
y = x^2 + 3x + 2
  = 25 + 15 + 2
  = 42
```

## Rebase vs Merge

* **Rebase:** Rearrange history, optionally rewriting it in the process.
* **Merge:** Let's make these timelines cross.

## Squash vs Add

* **Squash:** Everything happens at once!
* **Add:** This happened, then this happened, and this happened, and this also happened, oh and this happened too.

This is analogous to:

```bash
y = (x + 1)(x + 2)

# when x = 5
# Squash:
y = 42

# Add:
y = (x + 1)(x + 2)
  = (5 + 1)(5 + 2)
  = (6)(5 + 2)
  = (6)(7)
  = 6 * 7
  = 42
```
