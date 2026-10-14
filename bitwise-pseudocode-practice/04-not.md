# Bitwise NOT (`NOT`, commonly `~`)

## Rule

NOT flips each bit: 0 becomes 1 and 1 becomes 0.

## Width matters

NOT has no single decimal answer until the representation width and signedness are known. This guide uses **8-bit unsigned** values for its main NOT examples.

## Worked example — 8-bit unsigned

Find the 8-bit NOT of decimal 12.

```text
12          = 00001100
NOT 00001100 = 11110011
```

`11110011₂ = 128 + 64 + 32 + 16 + 2 + 1 = 243`, so the 8-bit **unsigned** result is 243.

Those same eight bits interpreted as signed two's complement represent -13. In common unbounded-integer languages, `~12` may instead evaluate to `-13`, because the language models sign extension/negative integers differently. Always follow the problem's declared representation.

## Common use — clear selected bits

To clear selected bits, AND with the width-limited complement of a mask.

```text
value = 11101111
mask  = 00000010
NOT mask (8-bit) = 11111101
value AND NOT mask = 11101101
```

The bit-1 position is cleared while the other positions remain as before.

## Practice

1. What is the 8-bit unsigned NOT of `00000101`?  
   **Answer: `11111010` = 250.** Flip all eight bits; `128+64+32+16+8+2 = 250`.

2. In 8 bits, what is NOT of `11110000`?  
   **Answer: `00001111` = 15.** Every 1 becomes 0 and every 0 becomes 1.
