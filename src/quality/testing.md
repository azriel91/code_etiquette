# Testing

Code that verifies other code is correct.

* **Unit tests:** Blazingly fast &mdash; ~ nano to milliseconds.

    Test a single class &mdash; 1 to many independent functions.

* **Integration tests:** Relatively fast &mdash; ~ seconds to minutes.

    Test multiple classes together &mdash; interaction between functions.

* **Acceptance tests:** May be slow &mdash; ~ minutes to hours.

    Test the "full usage scenario". e.g. launch 6 servers and send in some data to one of them. Make sure the data can be read from all the other servers.

## Example: Celsius to Fahrenheit calculator

```rust
/// Returns the temperature in Fahrenheit
///
/// T(F) = T(C) x 9 / 5 + 32
pub fn to_fahrenheit(t_in_celsius: i32) -> i32 {
    // naive
    // t_in_celsius * 9 / 5 + 32

    // properly rounded
    let t_in_celsius = t_in_celsius as f64;
    (t_in_celsius * 9.0 / 5.0 + 32.0).round() as i32
}

#[cfg(test)]
mod test {
    use super::to_fahrenheit;

    #[test]
    fn converts_zero_to_fahrenheit() {
        assert_eq!(32, to_fahrenheit(0));
    }

    #[test]
    fn converts_whole_number_to_fahrenheit() {
        assert_eq!(41, to_fahrenheit(5));
    }

    #[test]
    fn rounds_up_when_fraction_is_greater_than_point_5() {
        assert_eq!(36, to_fahrenheit(2)); // 32 + 3.6 rounds up
    }

    #[test]
    fn rounds_down_when_fraction_is_less_than_point_5() {
        assert_eq!(37, to_fahrenheit(3)); // 32 + 5.4 rounds down
    }

    // What's missing?
    // Does -0.5 round up or down?
    // Does -0.4 round up or down?
    // Integer overflows
}
```

Sample output:

* Naive:

    ```
    $ rustc main.rs --test && ./main

    running 4 tests
    test test::converts_whole_number_to_fahrenheit ... ok
    test test::rounds_down_when_fraction_is_less_than_point_5 ... ok
    test test::converts_zero_to_fahrenheit ... ok
    test test::rounds_up_when_fraction_is_greater_than_point_5 ... FAILED

    failures:

    ---- test::rounds_up_when_fraction_is_greater_than_point_5 stdout ----
        thread 'test::rounds_up_when_fraction_is_greater_than_point_5' panicked at 'assertion failed: `(left == right)` (left: `36`, right: `35`)', main.rs:29
    note: Run with `RUST_BACKTRACE=1` for a backtrace.


    failures:
        test::rounds_up_when_fraction_is_greater_than_point_5

    test result: FAILED. 3 passed; 1 failed; 0 ignored; 0 measured
    ```

* Properly rounded:

    ```
    $ rustc main.rs --test && ./main

    running 4 tests
    test test::converts_whole_number_to_fahrenheit ... ok
    test test::converts_zero_to_fahrenheit ... ok
    test test::rounds_down_when_fraction_is_less_than_point_5 ... ok
    test test::rounds_up_when_fraction_is_greater_than_point_5 ... ok

    test result: ok. 4 passed; 0 failed; 0 ignored; 0 measured
    ```
