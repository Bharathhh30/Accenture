# Left Shift (`<<`)

## Rule

Shift every bit left by the stated number of positions; zeroes enter from the right and bits shifted beyond the chosen width are discarded in a fixed-width model.

## Worked example

Find decimal `13 << 2` using an 8-bit unsigned width.

```text
13          = 00001101
shift left 2
            = 00110100 = 52
```

The result is 52; without overflow, shifting an unsigned value left by `k` positions is equivalent to multiplying by `2^k`.

## Common use — make a one-bit mask

`1 << k` creates a mask with bit `k` set; for example, `1 << 3 = 00001000₂ = 8`.

## Overflow warning

With an 8-bit width, `200` is `11001000`; shifting left once gives the low eight bits `10010000` (144) if the operation is defined as 8-bit truncation. Actual programming languages have different overflow/type rules, so never assume wraparound unless the question says so.

## Practice

1. `7 << 1` = ? (assume no overflow)  
   **Answer: 14.** `0111 → 1110`.

2. `5 << 3` = ? (assume no overflow)  
   **Answer: 40.** `00000101 → 00101000`, or `5 × 8`.
