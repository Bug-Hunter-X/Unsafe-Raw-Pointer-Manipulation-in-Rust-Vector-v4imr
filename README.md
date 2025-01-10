# Unsafe Raw Pointer Manipulation in Rust Vector

This repository demonstrates a potential issue in Rust where directly manipulating a vector's raw pointer using `as_mut_ptr()` can lead to data corruption and unexpected behavior if not handled carefully.  The example shows how modifying the vector's data directly through its raw pointer without updating the vector's internal length information is unsafe and can lead to memory safety violations.

The `bug.rs` file contains the problematic code.  The `bugSolution.rs` file shows a safer way to handle vector modification.

## How to Reproduce

1. Clone this repository
2. Navigate to the directory in your terminal
3. Run `rustc bug.rs && ./bug` to see the unexpected output
4. Run `rustc bugSolution.rs && ./bugSolution` to see the correct output

## Key takeaway

Always prioritize using safe Rust methods for vector manipulation.  Directly manipulating raw pointers is inherently unsafe and should be avoided unless absolutely necessary and you fully understand the implications.