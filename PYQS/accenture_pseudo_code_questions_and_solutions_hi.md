# Accenture Pseudo Code Questions & Solutions

This document contains detailed step-by-step solutions and explanations for the pseudo code questions asked in Accenture exams based on the video tutorials.

## **Operators Quick Reference**

* `^` denotes **Bitwise XOR** (Same bits = `0`, Different bits = `1`).
* `&` denotes **Bitwise AND** (Both bits `1` = `1`, otherwise `0`).
* `|` denotes **Bitwise OR** (Either bit `1` = `1`, otherwise `0`).
* `<<` denotes **Left Shift** (`a << b` is equivalent to $a \times 2^b$).
* `>>` denotes **Right Shift** (`a >> b` is equivalent to $\lfloor a / 2^b \rfloor$).
* `+`, `-`, `*`, `/` follow standard arithmetic precedence unless modified by parentheses.

---

# Part 1: Previous Year Questions & Short Tricks

## **Question 1**

### **Code Snippet:**

```text
Integer J
Integer array[4] = {0, 2, 0, 3}

if (array[0] & array[1] & array[2])
    array[0] = array[1] + array[3]
end if

array[0] = array[1] + array[2]

print array[1] + array[2]
```

### **Answer:**

`2`

### **Step-by-Step Explanation:**

1. **Initial Array Values:**
   * `array[0] = 0`
   * `array[1] = 2`
   * `array[2] = 0`
   * `array[3] = 3`

2. **Evaluate the `if` condition:**
   * Condition: `(array[0] & array[1] & array[2])`
   * Evaluate: `0 & 2 & 0` = `0` (False).
   * Since the condition evaluates to `0` (False), the code inside the `if` block is **skipped**.

3. **Execute Statement:**
   * `array[0] = array[1] + array[2]`
   * `array[0] = 2 + 0 = 2`

4. **Print Expression:**
   * Print `array[1] + array[2]`
   * `2 + 0 = 2`

---

## **Question 2**

### **Code Snippet:**

```text
Integer a, b, c
Set a = 8, b = 3, c = 10

c = b ^ b + c
c = c + 10 + 10

print a + b + c
```

### **Answer:**

`45`

### **Step-by-Step Explanation:**

1. **Initial Values:**
   * `a = 8`, `b = 3`, `c = 10`

2. **Evaluate `c = b ^ b + c`:**
   * Addition `+` has higher priority than XOR `^`.
   * Calculate `b + c` first: `3 + 10 = 13`.
   * Calculate `b ^ 13` (`3 ^ 13`):
     * Binary `3`  = `0011`
     * Binary `13` = `1101`
     * `3 ^ 13`   = `1110` (14 in decimal)
   * Updated `c = 14`.

3. **Evaluate `c = c + 10 + 10`:**
   * `c = 14 + 10 + 10 = 34`
   * Updated `c = 34`.

4. **Print Expression:**
   * Print `a + b + c`
   * `8 + 3 + 34 = 45`

---

## **Question 3**

### **Code Snippet:**

```text
Integer p, q, r
Set p = 7, q = 6, r = 4

if ((q ^ p) < r)
    if ((8 ^ r) + (7 + p) > (q ^ p))
        q = (12 & 11) ^ q
    else
        p = (r & q) + p
    end if
end if

r = 7 + p

print p + q + r
```

### **Answer:**

`35`

### **Step-by-Step Explanation:**

1. **Initial Values:**
   * `p = 7`, `q = 6`, `r = 4`

2. **Evaluate Outer `if` Condition:** `(q ^ p) < r`
   * `q ^ p` (`6 ^ 7`): `0110 ^ 0111 = 0001` (1 in decimal).
   * Check: `1 < 4` -> **True**.

3. **Evaluate Inner `if` Condition:** `((8 ^ r) + (7 + p) > (q ^ p))`
   * `8 ^ r` (`8 ^ 4`): `1000 ^ 0100 = 1100` (12 in decimal).
   * `7 + p` = `7 + 7 = 14`.
   * Left side: `12 + 14 = 26`.
   * Right side: `q ^ p = 1`.
   * Check: `26 > 1` -> **True**.

4. **Execute `q = (12 & 11) ^ q`:**
   * `12 & 11`: `1100 & 1011 = 1000` (8 in decimal).
   * `8 ^ q` (`8 ^ 6`): `1000 ^ 0110 = 1110` (14 in decimal).
   * Updated `q = 14`.

5. **Execute Statement outside `if`:**
   * `r = 7 + p = 7 + 7 = 14`

6. **Print Expression:**
   * Print `p + q + r` = `7 + 14 + 14 = 35`

---

## **Question 4**

### **Code Snippet:**

```text
Integer a, b, c
Set a = 5, b = 2, c = 6

b = (a + 6) ^ a
c = (1 + 3) & b
b = 9 + 7 + b

print a + b + c
```

### **Answer:**

`39`

### **Step-by-Step Explanation:**

1. **Initial Values:**
   * `a = 5`, `b = 2`, `c = 6`

2. **Evaluate `b = (a + 6) ^ a`:**
   * `a + 6 = 5 + 6 = 11`
   * `11 ^ 5`: `1011 ^ 0101 = 1110` (14 in decimal).
   * Updated `b = 14`.

3. **Evaluate `c = (1 + 3) & b`:**
   * `1 + 3 = 4`
   * `4 & 14`: `0100 & 1110 = 0100` (4 in decimal).
   * Updated `c = 4`.

4. **Evaluate `b = 9 + 7 + b`:**
   * `b = 9 + 7 + 14 = 30`
   * Updated `b = 30`.

5. **Print Expression:**
   * Print `a + b + c` = `5 + 30 + 4 = 39`

---

## **Question 5**

### **Code Snippet:**

```text
Integer count = 1
Integer result = 0

while (count <= 5)
    result = result + count
    count = count + 1
end while

print result
```

### **Answer:**

`15`

### **Step-by-Step Explanation:**

Calculates the sum of integers from 1 to 5:
* Iteration 1: `result = 0 + 1 = 1`, `count = 2`
* Iteration 2: `result = 1 + 2 = 3`, `count = 3`
* Iteration 3: `result = 3 + 3 = 6`, `count = 4`
* Iteration 4: `result = 6 + 4 = 10`, `count = 5`
* Iteration 5: `result = 10 + 5 = 15`, `count = 6`
* Loop exits since `6 <= 5` is False.
* Output is `15`.

---

# Part 2: Left & Right Shift Operator Questions

## **Question 6**

### **Code Snippet:**

```text
Integer a, b, c
Set a = 4, b = 2

c = a << b
print c
```

### **Answer:**

`16`

### **Step-by-Step Explanation:**

1. **Understand Left Shift (`<<`):**
   * `a << b` shifts the binary representation of `a` to the left by `b` positions.
   * Quick formula: `a << b` = $a \times 2^b$.

2. **Evaluate `c = 4 << 2`:**
   * Calculation: $4 \times 2^2 = 4 \times 4 = 16$.

3. **Binary Verification:**
   * Binary of `4` = `0000 0100`
   * Shift left by 2 bits = `0001 0000` (16 in decimal).

4. **Print:** `16`

---

## **Question 7**

### **Code Snippet:**

```text
Integer p, q, r
Set p = 32, q = 3

r = p >> q
print r
```

### **Answer:**

`4`

### **Step-by-Step Explanation:**

1. **Understand Right Shift (`>>`):**
   * `p >> q` shifts the binary representation of `p` to the right by `q` positions.
   * Quick formula: `p >> q` = $\lfloor p / 2^q \rfloor$.

2. **Evaluate `r = 32 >> 3`:**
   * Calculation: $\lfloor 32 / 2^3 \rfloor = \lfloor 32 / 8 \rfloor = 4$.

3. **Binary Verification:**
   * Binary of `32` = `0010 0000`
   * Shift right by 3 bits = `0000 0100` (4 in decimal).

4. **Print:** `4`

---

## **Question 8**

### **Code Snippet:**

```text
Integer a, b, c
Set a = 5, b = 1, c = 2

a = (a << b) + (a >> c)
b = (b << c) ^ a

print a + b
```

### **Answer:**

`25`

### **Step-by-Step Explanation:**

1. **Initial Values:**
   * `a = 5`, `b = 1`, `c = 2`

2. **Evaluate `a = (a << b) + (a >> c)`:**
   * `a << b` = `5 << 1` = $5 \times 2^1 = 10$.
   * `a >> c` = `5 >> 2` = $\lfloor 5 / 2^2 \rfloor = \lfloor 5 / 4 \rfloor = 1$.
   * `a = 10 + 1 = 11`.
   * Updated `a = 11`.

3. **Evaluate `b = (b << c) ^ a`:**
   * `b << c` = `1 << 2` = $1 \times 2^2 = 4$.
   * `b = 4 ^ 11`:
     * `4` in binary  = `0100`
     * `11` in binary = `1011`
     * `4 ^ 11`       = `1111` (15 in decimal).
   * Updated `b = 15`.

4. **Print Expression:**
   * Print `a + b` = `11 + 15 = 26`

---

## **Question 9**

### **Code Snippet:**

```text
Integer a, b, c
Set a = 12, b = 2, c = 1

if ((a >> b) < (a << c))
    b = (a >> c) + b
else
    c = (a << b) ^ c
end if

print a + b + c
```

### **Answer:**

`21`

### **Step-by-Step Explanation:**

1. **Initial Values:**
   * `a = 12`, `b = 2`, `c = 1`

2. **Evaluate `if` condition:** `(a >> b) < (a << c)`
   * `a >> b` = `12 >> 2` = $\lfloor 12 / 4 \rfloor = 3$.
   * `a << c` = `12 << 1` = $12 \times 2 = 24$.
   * Check: `3 < 24` -> **True**.

3. **Execute `if` block:**
   * `b = (a >> c) + b`
   * `a >> c` = `12 >> 1` = $\lfloor 12 / 2 \rfloor = 6$.
   * `b = 6 + 2 = 8`.
   * Updated `b = 8`.

4. **Print Expression:**
   * Print `a + b + c` = `12 + 8 + 1 = 21`

---

## **Question 10**

### **Code Snippet:**

```text
Integer p, q, r
Set p = 6, q = 3, r = 1

p = (p << r) ^ (q >> r)
q = (p >> r) & (q << r)

print p + q + r
```

### **Answer:**

`18`

### **Step-by-Step Explanation:**

1. **Initial Values:**
   * `p = 6`, `q = 3`, `r = 1`

2. **Evaluate `p = (p << r) ^ (q >> r)`:**
   * `p << r` = `6 << 1` = $6 \times 2 = 12$.
   * `q >> r` = `3 >> 1` = $\lfloor 3 / 2 \rfloor = 1$.
   * `p = 12 ^ 1`:
     * `12` in binary = `1100`
     * `1` in binary  = `0001`
     * `12 ^ 1`       = `1101` (13 in decimal).
   * Updated `p = 13`.

3. **Evaluate `q = (p >> r) & (q << r)`:**
   * `p >> r` = `13 >> 1` = $\lfloor 13 / 2 \rfloor = 6$.
   * `q << r` = `3 << 1` = $3 \times 2 = 6$.
   * `q = 6 & 6 = 6`.
   * Updated `q = 6`.

4. **Print Expression:**
   * Print `p + q + r` = `13 + 6 + 1 = 20`