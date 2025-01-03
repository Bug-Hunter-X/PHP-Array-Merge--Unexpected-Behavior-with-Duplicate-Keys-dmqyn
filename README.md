# PHP Array Merge Bug: Unexpected Key Behavior

This repository demonstrates a subtle bug related to array merging in PHP. When using the `+` operator or `array_merge()` to combine arrays with duplicate keys, the results might not be what you expect. The first array's values for duplicate keys are kept, losing values from the second array, leading to data loss.

## Bug Description
The issue lies in how PHP handles array key collisions during merging. The behavior is non-intuitive and can be difficult to debug because it doesn't throw an error, but simply omits some values.

## How to Reproduce
Clone this repository and run `bug.php`. The output will show that the value '3' for key 'b' from the second array is lost.

## Solution
The `bugSolution.php` file provides a solution using `array_replace()` which keeps all keys and values.  This function replaces values with the same key from later arrays rather than ignoring them.

## Conclusion
This example highlights the importance of being aware of the behavior of PHP array functions and using appropriate techniques to handle key collisions when merging arrays.