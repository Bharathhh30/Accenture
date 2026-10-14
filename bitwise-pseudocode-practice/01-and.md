# Bitwise AND (`AND`, commonly `&`)

## Rule

Compare matching bit positions: the result bit is 1 only if **both** input bits are 1.

| A | B | A AND B |
|---:|---:|---:|
| 0 | 0 | 0 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

## Worked example

Find `13 AND 11`.

```text
13 = 1101
11 = 1011
     ----
AND  1001 = 9
```

Only the `8` and `1` positions contain 1 in both operands, so the result is `1001₂ = 9`.

## Common uses

- **Mask bits:** `value AND mask` preserves only the positions where the mask contains 1.
- **Test bit k:** `(value AND (1 shifted left by k)) != 0` means bit `k` is set; bit positions start at 0 from the right.
- **Clear bits:** `value AND NOT(mask)` clears the mask's 1-bit positions, with NOT interpreted at the intended width.

## Practice

1. `10 AND 6` = ?  
   **Answer: 2.** `1010 AND 0110 = 0010`.

2. Is bit 2 set in `12`? (Use `12 AND (1 shifted left by 2)`.)  
   **Answer: Yes.** `12 = 1100`, the bit-2 mask is `0100`, and `1100 AND 0100 = 0100`, which is nonzero.
