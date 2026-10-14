# Bitwise Operators — Pseudocode Study and Practice

This folder teaches the binary skills needed to solve bitwise pseudocode questions, then covers **AND, OR, XOR, NOT, left shift, and right shift** with worked examples and a mixed practice set.

## 1. Binary is place value in base 2

Each binary digit (bit) is either 0 or 1. From right to left, bit positions have weights that are powers of 2:

| Bit position | 7 | 6 | 5 | 4 | 3 | 2 | 1 | 0 |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Weight | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |

To convert a binary number to decimal, add the weights wherever the bit is 1.

**Example:** `00101101₂ = 32 + 8 + 4 + 1 = 45₁₀`.

The subscript ₂ means binary; the subscript ₁₀ means decimal.

## 2. Convert decimal to binary

### Method A — repeated division by 2

Divide by 2 repeatedly, recording each remainder. Read the remainders **from bottom to top**.

| Division | Quotient | Remainder |
|---|---:|---:|
| 45 ÷ 2 | 22 | 1 |
| 22 ÷ 2 | 11 | 0 |
| 11 ÷ 2 | 5 | 1 |
| 5 ÷ 2 | 2 | 1 |
| 2 ÷ 2 | 1 | 0 |
| 1 ÷ 2 | 0 | 1 |

Reading remainders bottom-to-top gives `101101₂`; padded to 8 bits, `00101101₂`. Therefore, `45₁₀ = 00101101₂`.

### Method B — subtract powers of 2

For 45, the largest power of 2 that fits is 32; the remainder 13 contains 8 + 4 + 1, so the 32, 8, 4, and 1 columns are 1: `00101101₂`.

### Convert binary to decimal

Label positions from the right starting at 0, then add `bit × 2^position`.

**Example:** `110101₂ = 1×32 + 1×16 + 0×8 + 1×4 + 0×2 + 1×1 = 53₁₀`.

## 2's complement for negative integers

For an `n`-bit two's-complement integer, the representable range is `−2^(n−1)` through `2^(n−1)−1`; the leftmost bit is the sign bit.

To encode `−13` in 8 bits: write `+13` as `00001101`, invert all bits to `11110010`, then add 1 to get `11110011`. Decoding a negative bit pattern uses the reverse process; do not interpret a signed pattern as an unsigned value unless the question says to.

> Questions involving negative values must identify the signed representation or language rules; never guess the meaning of a right shift or NOT result.

## 3. Use a fixed width when doing NOT

For practice here, use **8-bit unsigned values** unless a question says otherwise; pad with leading zeroes before comparing bits. Leading zeroes do not change the decimal value, but they make the width visible.

For 8-bit `00001100`, flipping every bit gives `11110011`. Interpreted as **unsigned 8-bit**, that is 243. Interpreted as an 8-bit two's-complement signed value, it is -13. Thus a NOT question must specify the width and whether the result is signed or unsigned; programming languages can also define signed shifts and integer width differently.

## 4. Bitwise truth tables

Apply each operator **one column at a time**.

| A | B | A AND B | A OR B | A XOR B |
|---:|---:|---:|---:|---:|
| 0 | 0 | 0 | 0 | 0 |
| 0 | 1 | 0 | 1 | 1 |
| 1 | 0 | 0 | 1 | 1 |
| 1 | 1 | 1 | 1 | 0 |

- **AND** gives 1 only when both bits are 1.
- **OR** gives 1 when at least one bit is 1.
- **XOR** gives 1 when the bits differ.
- **NOT** flips each bit: 0 becomes 1 and 1 becomes 0.

## 5. How to solve bitwise pseudocode questions

1. Write down the operator width and signedness; if omitted in a learning question, state your assumption.
2. Convert each decimal operand to binary and pad operands to the same width.
3. Apply the operator column by column, or move bits for a shift.
4. For a compound expression, use parentheses and precedence; when unsure, evaluate the innermost operation first.
5. Convert the resulting binary value back to decimal if the question asks for a number.
6. For pseudocode, update variables after every statement; do not confuse bitwise `AND` with logical `AND`.

## Operator guides

- [Bitwise AND](01-and.md)
- [Bitwise OR](02-or.md)
- [Bitwise XOR](03-xor.md)
- [Bitwise NOT](04-not.md)
- [Left shift](05-left-shift.md)
- [Right shift](06-right-shift.md)
- [Mixed worked practice and answer key](07-mixed-practice.md)
- [Advanced assessment-style pseudocode mock](08-advanced-assessment-mock.md)

## Fast memory cues

- **AND:** keep only bits that are 1 in both; useful for masking/checking bits.
- **OR:** turn on any bit that is 1 in either; useful for setting bits.
- **XOR:** keep bits that differ; useful for toggling bits.
- **NOT:** invert every bit; define the width before interpreting the result.
- **Left shift:** move bits left; for unsigned values and no overflow, shifting left by `k` multiplies by `2^k`.
- **Right shift:** move bits right; for unsigned values, shifting right by `k` is floor division by `2^k`.

> Symbols such as `&`, `|`, `^`, `~`, `<<`, and `>>` are common in C-like languages, but symbol meanings can vary (for example, `^` means XOR in C-like languages but exponentiation in some others). Follow the language named in the question.
