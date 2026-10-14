# Right Shift (`>>`)

## Rule

Shift bits right by the stated number of positions; bits falling off the right are discarded. The new bits entering from the left depend on whether the shift is logical/unsigned or arithmetic/signed.

## Worked example — unsigned/logical

Find `173 >> 3` using an 8-bit **unsigned logical** right shift.

```text
173          = 10101101
shift right 3
             = 00010101 = 21
```

For unsigned values, a logical right shift by `k` is equivalent to floor division by `2^k`; `floor(173 / 8) = 21`.

## Logical vs arithmetic right shift

- **Logical right shift:** zeroes enter from the left; use for unsigned bit patterns.
- **Arithmetic right shift:** the sign bit is copied from the left for signed values in languages that define this behavior; check the language specification.

## Practice

1. `20 >> 2` using an unsigned logical shift = ?  
   **Answer: 5.** `00010100 → 00000101`; equivalently, `20 / 4 = 5`.

2. `255 >> 4` using an 8-bit unsigned logical shift = ?  
   **Answer: 15.** `11111111 → 00001111`.
