# Advanced Pseudocode / Output-Tracing Practice

These are additional **original** questions, written to practise patterns that recur in public pseudocode banks: increments, parameters, recursion, bitwise operations, arrays, and C storage/I/O behavior. They are not asserted to be recalled Accenture test questions.

## Conventions

- Zero-based array indexing.
- For the language-neutral questions, loop bounds are inclusive.
- For C questions, assume standard defined behavior; don't infer behavior from code with undefined or unspecified behavior.
- The ASCII question explicitly uses ASCII codes.

## Questions

1. What is printed in this C-like code?
   ```
   x = 3
   y = ++x
   z = x++
   print x, y, z
   ```
   A) `4, 4, 4`  B) `5, 4, 4`  C) `5, 5, 4`  D) `4, 3, 3`

2. `change(ref n)` adds 5 to `n`, where `ref` means the caller's variable is passed by reference. What is printed?
   ```
   value = 7
   change(ref value)
   print value
   ```
   A) 7  B) 10  C) 12  D) 35

3. Under ASCII, what is the numeric code of character `'C'`?
   A) 65  B) 66  C) 67  D) 97

4. With a bitwise left shift, what is `3 << 2`?
   A) 5  B) 6  C) 12  D) 32

5. Using bitwise XOR, what is `10 XOR 6`?
   A) 4  B) 10  C) 12  D) 14

6. What is printed?
   ```
   A = [2, 5, 7]
   A[1] = A[1] + A[0]
   A[2] = A[2] - A[1]
   print A[0] + A[1] + A[2]
   ```
   A) 7  B) 9  C) 14  D) 16

7. How many times is `hits` incremented? (A `break` immediately exits the inner loop.)
   ```
   hits = 0
   for i = 1 to 4
       for j = 1 to 4
           hits = hits + 1
           if j == 2
               break
   ```
   A) 4  B) 6  C) 8  D) 16

8. A function receives integer `n` by value and executes `n = n + 10`. The caller's variable `x` is 4 before calling `f(x)`. What is `x` after the call?
   A) 4  B) 10  C) 14  D) It is always undefined

9. What does `sum(4)` return?
   ```
   sum(n):
       if n == 0: return 0
       return n + sum(n - 1)
   ```
   A) 4  B) 6  C) 10  D) 24

10. What is printed?
    ```
    x = 0
    for i = 1 to 5
        if i % 2 == 0
            x = x + i
        else
            x = x - 1
    print x
    ```
    A) 1  B) 2  C) 3  D) 5

## Answers and explanations

1. **B — `5, 4, 4`.** Prefix increment updates `x` before assigning to `y`; postfix increment assigns the old value to `z` and then increments `x`.
2. **C — 12.** By-reference modification changes the caller's `value` from 7 to 12.
3. **C — 67.** ASCII uppercase letters begin with `A=65`.
4. **C — 12.** Shifting the binary value `0011` left twice gives `1100` (12).
5. **C — 12.** `10` is `1010₂`; `6` is `0110₂`; XOR is `1100₂` (12).
6. **B — 9.** The array changes from `[2,5,7]` to `[2,7,0]`; the sum is 9.
7. **C — 8.** For each of four outer-loop iterations, the inner loop increments at `j=1` and `j=2`, then breaks.
8. **A — 4.** Pass-by-value changes the local parameter copy, not the caller's variable.
9. **C — 10.** The function computes 4 + 3 + 2 + 1 + 0.
10. **C — 3.** Updates are `-1, +2, -1, +4, -1`, which total 3.
