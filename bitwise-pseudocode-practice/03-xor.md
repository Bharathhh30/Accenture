# Bitwise XOR (`XOR`, commonly `^`)

## Rule

XOR (“exclusive OR”) gives 1 when the two bits are **different** and 0 when they are the same.

| A | B | A XOR B |
|---:|---:|---:|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

## Worked example

Find `12 XOR 10`.

```text
12 = 1100
10 = 1010
     ----
XOR  0110 = 6
```

Only the 4-bit and 1-bit columns differ, giving `0110₂ = 6₁₀`.

## Common use — toggle a bit

XOR with 1 flips a bit; XOR with 0 leaves it unchanged. Therefore, `value XOR (1 shifted left by k)` toggles bit `k`.

```text
value = 10                // 1010
mask  = 1 shifted left 1  // 0010
result = value XOR mask   // 1000 = 8
```

## Useful identities

- `x XOR 0 = x`.
- `x XOR x = 0`.
- XOR is order-independent: `a XOR b = b XOR a`.

## Practice

1. `15 XOR 9` = ?  
   **Answer: 6.** `1111 XOR 1001 = 0110`.

2. Toggle bit 2 in `9`.  
   **Answer: 13.** `9 = 1001`, the bit-2 mask is `0100`, and `1001 XOR 0100 = 1101`.
