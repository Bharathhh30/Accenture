# Advanced Bitwise Pseudocode — Assessment-Style Mock

The earlier mixed set was intentionally introductory. This set is a harder step: it combines bitwise operators with loops, masks, array accumulation, precedence, field extraction, and state changes across several statements.

**Important:** These are original practice problems in a technical-assessment style, **not verified or leaked Accenture questions**. Accenture's public recruiting information does not publish a fixed bitwise question bank or guarantee that bitwise MCQs appear in every drive. Use this to practise reasoning, not to assume exact exam content.

## Rules for this mock

- Values are **unsigned integers**; calculations use the width explicitly stated in a question, otherwise use at least 16 bits.
- Binary literals such as `0b1010` are allowed.
- For fixed-width assignment, bits above the width are discarded.
- Right shift is logical: zeroes enter from the left.
- Bitwise precedence follows C-like rules: shifts before bitwise AND, then XOR, then OR; parentheses override precedence.
- `AND`, `OR`, and `NOT` written as words are logical operators only when applied to Boolean conditions; `&`, `|`, `^`, and `~` are bitwise operators.
- Loops have inclusive bounds; bit positions start at 0 from the right.

## Questions

### 1. Extract, mask, then combine

```text
x = 0b10110110
y = ((x >> 2) & 0b00001111) ^ 0b00000101
print y
```

A) 6  B) 8  C) 10  D) 13

### 2. Count set bits efficiently

```text
x = 0b11010100
count = 0
while x != 0
    x = x & (x - 1)
    count = count + 1
print count
```

A) 3  B) 4  C) 5  D) 6

### 3. Find the non-repeated value

Every value in the array appears exactly twice except one value:

```text
A = [12, 7, 5, 12, 9, 7, 5]
result = 0
for i = 0 to length(A) - 1
    result = result ^ A[i]
print result
```

A) 5  B) 7  C) 9  D) 12

### 4. Scan a value using a shifting mask

Add the **even bit positions** that are set in `x`:

```text
x = 0b10110101
mask = 1
total = 0
for i = 0 to 7
    if ((x & mask) != 0) AND (i % 2 == 0)
        total = total + i
    mask = mask << 1
print total
```

A) 4  B) 5  C) 6  D) 7

### 5. Apply three masks in sequence

All operations are 8-bit unsigned:

```text
x = 0b01101010
x = x ^ (1 << 1)
x = x | (1 << 0)
x = x & ~(1 << 6)
print x
```

A) 37  B) 41  C) 45  D) 73

### 6. Swap two selected bits

The following logic swaps bits 1 and 6 of `x`:

```text
x = 0b10010110
i = 1
j = 6
different = ((x >> i) ^ (x >> j)) & 1
x = x ^ ((different << i) | (different << j))
print x
```

A) 148  B) 180  C) 212  D) 214

### 7. Rotate an 8-bit value left

```text
x = 0b10110011
k = 3
rotated = ((x << k) | (x >> (8 - k))) & 0xFF
print rotated
```

A) 157  B) 179  C) 206  D) 237

### 8. Decode a Gray-coded value

For this question, decode using the standard prefix-XOR method:

```text
g = 0b1110101
b = g
shift = 1
while shift < 7
    b = b ^ (b >> shift)
    shift = shift << 1
print b
```

A) 77  B) 89  C) 101  D) 117

### 9. Transform, then test for a power of two

```text
x = 0b00101010
y = x ^ (x >> 2)
if y > 0 AND (y & (y - 1)) == 0
    print y
else
    print 0
```

A) 0  B) 16  C) 32  D) 42

### 10. Resolve bitwise precedence

Use the precedence rules stated above:

```text
a = 0b110110
b = 0b101011
c = 0b001101
d = 0b000010
result = a & b ^ c << 1 | d
print result
```

A) 42  B) 50  C) 56  D) 58

### 11. Extract bytes and form a checksum nibble

```text
word = 0xAB37
high = (word >> 8) & 0xFF
low = word & 0xFF
check = (high ^ low) & 0x0F
print check
```

A) 10  B) 12  C) 14  D) 15

### 12. Reverse the low four bits

```text
x = 0b101101
acc = 0
for i = 0 to 3
    bit = (x >> i) & 1
    acc = (acc << 1) | bit
print acc
```

A) 9  B) 11  C) 13  D) 14

### 13. Nested-loop filter with XOR parity

```text
score = 0
for i = 1 to 4
    for j = 0 to 2
        if (((i ^ j) & 1) == 1)
            score = score + ((i << 1) | j)
print score
```

A) 24  B) 28  C) 30  D) 32

### 14. Update flags, then pack two fields

All operations are 8-bit unsigned:

```text
flags = 0b01010100
flags = flags | (1 << 1)
flags = flags ^ (1 << 4)
flags = flags & ~(1 << 6)
packed = ((flags & 0b00001111) << 1) | ((flags >> 4) & 0b00001111)
print packed
```

A) 6  B) 10  C) 12  D) 14

### 15. Rotate an 8-bit value right

```text
x = 0b01101001
k = 2
rotated = ((x >> k) | (x << (8 - k))) & 0xFF
print rotated
```

A) 26  B) 74  C) 90  D) 105

## Answer key — detailed traces

1. **B — 8.** `x >> 2 = 00101101`; masking the low nibble gives `1101` (13); `1101 XOR 0101 = 1000` (8).
2. **B — 4.** Each `x & (x-1)` removes the lowest set bit; `11010100` contains four 1-bits, so the loop runs four times.
3. **C — 9.** XOR cancels equal pairs because `v XOR v = 0` and `0 XOR v = v`; only 9 remains.
4. **C — 6.** Set positions in `10110101` are 0, 2, 4, 5, and 7; the even set positions sum to `0+2+4 = 6`.
5. **B — 41.** Start `01101010`; toggle bit 1 → `01101000`; set bit 0 → `01101001`; clear bit 6 → `00101001` = 41.
6. **C — 212.** Original bit 1 is 1 and bit 6 is 0, so both toggle: `150 - 2 + 64 = 212`.
7. **A — 157.** The 8-bit rotate gives `10011101₂`, which is 157; the mask discards overflow above bit 7.
8. **B — 89.** The loop uses shifts 1, 2, and 4: `117 XOR 58 = 79`; `79 XOR 19 = 92`; `92 XOR 5 = 89`.
9. **C — 32.** `x >> 2 = 10`; `42 XOR 10 = 32`; 32 is positive and has exactly one set bit, so it passes the power-of-two test.
10. **D — 58.** `a & b = 34`; `c << 1 = 26`; `34 XOR 26 = 56`; `56 OR 2 = 58`.
11. **B — 12.** `high=0xAB`, `low=0x37`; `0xAB XOR 0x37 = 0x9C`; the low nibble is `0xC = 12`.
12. **B — 11.** The low four bits of `x` are `1101`; reading them from bit 0 upward gives `1,0,1,1`, accumulated as `1011₂ = 11`.
13. **C — 30.** Passing `(i ^ j) & 1` pairs contribute: `i=1 → 2+2=4`; `i=2 → 5`; `i=3 → 6+6=12`; `i=4 → 9`; total `4+5+12+9=30`.
14. **C — 12.** Flags move `01010100 → 01010110 → 01000110 → 00000110`; low nibble is 6, high nibble is 0, so packed value is `(6<<1)|0 = 12`.
15. **C — 90.** Logical right part is `00011010` (26); shifted-left wrap part retained by the 8-bit mask is `01000000` (64); OR gives `01011010` (90).

## What makes these harder

- Several questions require tracking a value after multiple mutations, not applying one operator once.
- Masks and shifts are used to extract, set, clear, toggle, pack, rotate, and test fields.
- Loops combine indices, parity checks, accumulation, and bit operations.
- The XOR questions use cancellation, population-count logic, and Gray-code decoding.
- The precedence problem requires applying language-like precedence rather than reading strictly left to right.

For additional self-study on operator definitions and language precedence, see [Microsoft's C bitwise-operator reference](https://learn.microsoft.com/en-us/cpp/c-language/c-bitwise-operators?view=msvc-170), [Microsoft's C shift-operator reference](https://learn.microsoft.com/en-us/cpp/c-language/bitwise-shift-operators?view=msvc-170), and [the public C operator-precedence reference](https://en.cppreference.com/w/c/language/operator_precedence).
