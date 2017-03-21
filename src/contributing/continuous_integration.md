# Continuous Integration

> "It works on my machine." &mdash; said every developer, ever.

Continuous integration (CI) is a process in which every set of changes that is pushed to a repository is compiled and tested by a **build server**.

![continuous integration](http://www.continuousintegrationtools.com/cicycle.jpg)

* Everything you need to build is specified by the repository. Paraphrased: you do not have the software that is installed on the developer's machine that can affect the building / testing of the software.
* Confidence that "the code is good" before merging.
* You can build across multiple operating systems (Windows, Linux, MacOS) from the same source, and ensure it works before merging code from a branch into `master`.

## CI Software

* [Travis](https://travis-ci.org/): Linux and MacOS (free for open source, paid for closed source)
* [Appveyor](https://ci.appveyor.com/): Windows (free for open source, paid for closed source)
* [Bitbucket Pipelines](https://bitbucket.org/product/features/pipelines): Free for small closed source projects, but limited by minutes.
* [Bamboo](https://www.atlassian.com/software/bamboo): $10 license if you want to play around. Hooks into many other Atlassian software.
* Many others: Jenkins, Circle CI, Team City, Go CD

## Example Projects

* [Conan](https://github.com/conan-io/conan)
