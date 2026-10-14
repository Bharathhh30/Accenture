# Mixed Bitwise Pseudocode Practice

Assume operands are nonnegative integers, array-like binary notation is unsigned, and leading zeroes may be added for alignment. **Questions that use NOT explicitly say 8-bit unsigned.** Apply parentheses first and trace pseudocode statements in order.

## Questions

1. What is `14 AND 11`?
   A) 8  B) 10  C) 12  D) 15

2. What is `18 OR 5`?
   A) 19  B) 21  C) 23  D) 27

3. What is `25 XOR 19`?
   A) 10  B) 12  C) 14  D) 18

4. What is the 8-bit unsigned NOT of `00010110`?
   A) `11101001`  B) `11101010`  C) `00001001`  D) `11110110`

5. What is `9 << 2`, assuming no overflow?
   A) 18  B) 27  C) 36  D) 81

6. What is `100 >> 3` using an unsigned logical shift?
   A) 10  B) 12  C) 13  D) 25

7. Evaluate `(12 AND 10) OR 3`.
   A) 8  B) 9  C) 11  D) 15

8. What is the value of `x`?
   ```
   x = 6
   x = x << 2
   x = x XOR 5
   ```
   A) 21  B) 24  C) 29  D) 31

9. Is bit position 3 set in decimal 40? (Position 0 is the rightmost bit.)
   A) Yes  B) No

10. Set bit position 2 in decimal 9 using OR and a one-bit mask; what is the result?
    A) 9  B) 11  C) 13  D) 15

11. Toggle bit position 1 in decimal 12 using XOR and a one-bit mask; what is the result?
    A) 8  B) 10  C) 14  D) 12

12. Clear bit position 2 in decimal 15 using an 8-bit mask; what is the result?
    A) 7  B) 11  C) 13  D) 15

13. Which expression checks whether bit 0 of `n` is set?
    A) `n AND 1 != 0`  B) `n OR 1 == 0`  C) `NOT n == 0`  D) `n << 1 == 0`

14. What is decimal 45 in 8-bit binary?
    A) `00101101`  B) `00110101`  C) `01001101`  D) `10110010`

15. Convert `110010₂` to decimal.
    A) 48  B) 50  C) 54  D) 58

## Answer key with approach

1. **B — 10.** `14=1110`, `11=1011`; `1110 AND 1011 = 1010₂ = 10`.
2. **C — 23.** `18=10010`, `5=00101`; OR gives `10111₂ = 23`.
3. **A — 10.** `25=11001`, `19=10011`; XOR gives `01010₂ = 10`.
4. **A — `11101001`.** Flip each of the eight bits in `00010110`.
5. **C — 36.** Left shift two places multiplies by 4: `9 × 4 = 36`.
6. **B — 12.** `100 / 8 = 12` remainder 4; logical shift discards the remainder bits.
7. **C — 11.** `12 AND 10 = 8`; `8 OR 3 = 1000 OR 0011 = 1011₂ = 11`.
8. **C — 29.** `6 << 2 = 24`; `24 XOR 5 = 11000 XOR 00101 = 11101₂ = 29`.
9. **A — Yes.** `40 = 101000₂`; bit position 3 has weight 8 and is 1.
10. **C — 13.** `9=1001`; bit-2 mask is `0100`; OR gives `1101₂=13`.
11. **C — 14.** `12=1100`; bit-1 mask is `0010`; XOR gives `1110₂=14`.
12. **B — 11.** `15=00001111`; clearing bit 2 gives `00001011₂=11`.
13. **A.** AND with the mask `1` isolates bit 0; a nonzero result means the bit is set.
14. **A — `00101101`.** `32+8+4+1 = 45`.
15. **B — 50.** `110010₂ = 32+16+2 = 50`.

## Quick solving checklist

1. Convert operands to binary; pad to the same width.
2. For AND/OR/XOR, calculate each column using the truth table.
3. For NOT, flip exactly the stated number of bits.
4. For shifts, move bits and state whether overflow/sign-fill rules apply.
5. Convert the final bit pattern to decimal only after the operation is complete.
6. Check the result by an identity: left shift ≈ multiply by a power of 2; unsigned right shift = floor-divide by a power of 2.
