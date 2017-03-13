# Style

## What It Is

* [Indentation](https://en.wikipedia.org/wiki/Indent_style)
    - spaces vs tabs
    - width: 2 characters, 4 characters
* Braces

    ```c
    while (x == y) {
        something();
        somethingelse();
    }

    while (x == y)
    {
        something();
        somethingelse();
    }
    ```

* Case

    ```ruby
    snake_case # ruby, rust variables
    SCREAMING_SNAKE_CASE # Java statics, ruby, rust constants
    lowerCamelCase # Java, NodeJS
    UpperCamelCase # C# method names
    ```

## Why It Matters

* Makes code easier to read.

    ```rust
    fn x() { 1 }
    fn y() { 1 }

    fn main() {
        assert_eq!(x(), y());
    }
    ```

    ```rust
    fn x() { 1
    }


    fn y() {
        1
    }

    fn main() {
          assert_eq!(x(),
        y());
    }
    ```

* Reduce unnecessary noise in the diff:

    - [Diff with whitespace](https://github.com/conan-io/conan/pull/110/files#diff-9521e09680c5dd9a05e8d76c1bf4d84c)
    - [Diff without whitespace](https://github.com/conan-io/conan/pull/110/files?w=1#diff-9521e09680c5dd9a05e8d76c1bf4d84c)

## How To Address It

* **Linters:** Programs that complain when your code doesn't follow standards
* **Auto Correct:** Programs that automatically change your code to meet standards
* **Validation:** Make it part of the build - fail if code doesn't meet standards
