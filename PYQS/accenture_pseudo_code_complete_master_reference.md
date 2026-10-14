# Accenture Pseudo Code Questions & Solutions (Master Collection)

This comprehensive document contains all pseudo code questions, options, final answers, and detailed step-by-step explanations gathered from the three video tutorials.

---

## **Operators Quick Reference**

* `^` denotes **Bitwise XOR** (Same bits = `0`, Different bits = `1`).
* `&` denotes **Bitwise AND** (Both bits `1` = `1`, otherwise `0`).
* `|` denotes **Bitwise OR** (Either bit `1` = `1`, otherwise `0`).
* `<<` denotes **Left Shift** (`a << b` is equivalent to $a \times 2^b$).
* `>>` denotes **Right Shift** (`a >> b` is equivalent to $\lfloor a / 2^b \rfloor$).
* `mod` or `%` denotes **Modulo Operator** (returns remainder after integer division).
* `+`, `-`, `*`, `/` follow standard arithmetic precedence unless modified by parentheses.

---

# PART 1: Core Pseudo Code Questions (Video 1)

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

### **Answer:** `2`

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

### **Answer:** `45`

### **Step-by-Step Explanation:**
1. **Initial Values:** `a = 8`, `b = 3`, `c = 10`

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

### **Answer:** `35`

### **Step-by-Step Explanation:**
1. **Initial Values:** `p = 7`, `q = 6`, `r = 4`

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

### **Answer:** `39`

### **Step-by-Step Explanation:**
1. **Initial Values:** `a = 5`, `b = 2`, `c = 6`

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

### **Answer:** `15`

### **Step-by-Step Explanation:**
1. **Initial Values:** `count = 1`, `result = 0`
2. **Loop Iterations:**
   * Iteration 1: `result = 0 + 1 = 1`, `count = 2`
   * Iteration 2: `result = 1 + 2 = 3`, `count = 3`
   * Iteration 3: `result = 3 + 3 = 6`, `count = 4`
   * Iteration 4: `result = 6 + 4 = 10`, `count = 5`
   * Iteration 5: `result = 10 + 5 = 15`, `count = 6`
3. Loop terminates as `6 <= 5` is False.
4. **Print:** `15`

---

# PART 2: Shift Operators & Loop Questions (Video 2)

## **Question 6**

### **Code Snippet:**
```text
Integer a, b, c
Set a = 4, b = 2

c = a << b
print c
```

### **Answer:** `16`

### **Step-by-Step Explanation:**
1. Left shift formula: `a << b` = $a \times 2^b$.
2. `c = 4 << 2` = $4 \times 2^2 = 4 \times 4 = 16$.
3. **Print:** `16`

---

## **Question 7**

### **Code Snippet:**
```text
Integer p, q, r
Set p = 32, q = 3

r = p >> q
print r
```

### **Answer:** `4`

### **Step-by-Step Explanation:**
1. Right shift formula: `p >> q` = $\lfloor p / 2^q \rfloor$.
2. `r = 32 >> 3` = $\lfloor 32 / 2^3 \rfloor = \lfloor 32 / 8 \rfloor = 4$.
3. **Print:** `4`

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

### **Answer:** `26`

### **Step-by-Step Explanation:**
1. **Initial Values:** `a = 5`, `b = 1`, `c = 2`
2. **Evaluate `a`:**
   * `a << b` = `5 << 1` = `10`
   * `a >> c` = `5 >> 2` = `1`
   * `a = 10 + 1 = 11`
3. **Evaluate `b`:**
   * `b << c` = `1 << 2` = `4`
   * `b = 4 ^ 11`: `0100 ^ 1011 = 1111` (15 in decimal)
4. **Print Expression:** `a + b = 11 + 15 = 26`

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

### **Answer:** `21`

### **Step-by-Step Explanation:**
1. **Initial Values:** `a = 12`, `b = 2`, `c = 1`
2. **Condition Check:** `(12 >> 2) < (12 << 1)` $\implies 3 < 24$ (**True**)
3. **Execute `if` block:**
   * `b = (12 >> 1) + 2`
   * `b = 6 + 2 = 8`
4. **Print Expression:** `a + b + c` = `12 + 8 + 1 = 21`

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

### **Answer:** `20`

### **Step-by-Step Explanation:**
1. **Initial Values:** `p = 6`, `q = 3`, `r = 1`
2. **Evaluate `p`:**
   * `p << r` = `6 << 1 = 12`
   * `q >> r` = `3 >> 1 = 1`
   * `p = 12 ^ 1`: `1100 ^ 0001 = 1101` (13 decimal)
3. **Evaluate `q`:**
   * `p >> r` = `13 >> 1 = 6`
   * `q << r` = `3 << 1 = 6`
   * `q = 6 & 6 = 6`
4. **Print Expression:** `p + q + r` = `13 + 6 + 1 = 20`

---

## **Question 11**

### **Code Snippet:**
```text
Integer a, b, c
Set a = 2, b = 8, c = 9

if ((a >> 1) || (b >> 1))
    a = (a + 1) + c
end if

print a + b + c
```

### **Answer:** `29`

### **Step-by-Step Explanation:**
1. **Initial Values:** `a = 2`, `b = 8`, `c = 9`
2. **Condition Evaluation:**
   * `a >> 1` = `2 >> 1 = 1` (Non-zero, so True).
   * Logical OR `||` short-circuits: condition is **True**.
3. **Execute `if` block:**
   * `a = (2 + 1) + 9 = 12`
4. **Print Expression:** `a + b + c = 12 + 8 + 9 = 29`

---

## **Question 12**

### **Code Snippet:**
```text
Integer a, b, c
Set a = 1, b = 2, c = 4

for (each c from 1 to 2)
    if (0 & a)
        a = a + 1
    end if
    b = b + 1
end for

print a + b
```

### **Answer:** `5`

### **Step-by-Step Explanation:**
1. **Initial Values:** `a = 1`, `b = 2`
2. **Loop Iterations (`c` from 1 to 2):**
   * Condition `0 & a` = `0` (False) in all iterations, so `a` remains `1`.
   * Iteration 1 (`c=1`): `b = 2 + 1 = 3`
   * Iteration 2 (`c=2`): `b = 3 + 1 = 4`
3. **Print Expression:** `a + b = 1 + 4 = 5`

---

## **Question 13**

### **Code Snippet:**
```text
Integer a, b, c
Set a = 5, b = 4, c = 3

if (a & b)
    c = a ^ b
    a = b + c
end if

print a + b + c
```

### **Answer:** `12`

### **Step-by-Step Explanation:**
1. **Initial Values:** `a = 5`, `b = 4`, `c = 3`
2. **Condition:** `5 & 4` = `0101 & 0100 = 0100` (4, which is non-zero / True).
3. **Execute `if` block:**
   * `c = 5 ^ 4`: `0101 ^ 0100 = 0001` (1 decimal).
   * `a = b + c = 4 + 1 = 5`.
4. **Print Expression:** `a + b + c = 5 + 4 + 1 = 12`

---

# PART 3: Recursion, MOD, Loops & Static Variables (Video 3)

## **Question 14**

### **Code Snippet:**
```text
Integer a, b, c
Set a = 170, b = 85

c = a ^ b

while (c > 0)
    c = c / 2
end while

print c
```

### **Answer:** `0`

### **Step-by-Step Explanation:**
1. **Initial Values:** `a = 170`, `b = 85`
2. `c = 170 ^ 85 = 255`.
3. **While Loop:** Repeatedly performs integer division `c = c / 2`.
   * Loop runs until `c` becomes `0`.
4. **Print:** `0`

---

## **Question 15**

### **Code Snippet:**
```text
Integer x, y, z
Set x = 7, y = 10

z = x mod y
print z
```

### **Answer:** `7`

### **Step-by-Step Explanation:**
1. `x mod y` computes remainder of $7 / 10$.
2. Since numerator ($7$) < denominator ($10$), remainder is simply $7$.
3. **Print:** `7`

---

## **Question 16**

### **Code Snippet:**
```text
function solve(n)
    if (n == 0)
        return
    end if
    solve(n - 1)
    print n
end function

// Main call:
solve(3)
```

### **Answer:** `1 2 3`

### **Step-by-Step Explanation:**
1. **Call Stack Tracing:**
   * `solve(3)` calls `solve(2)`
   * `solve(2)` calls `solve(1)`
   * `solve(1)` calls `solve(0)`
   * `solve(0)` returns immediately.
2. **Unwinding Stack:**
   * `solve(1)` prints `1`
   * `solve(2)` prints `2`
   * `solve(3)` prints `3`
3. **Output:** `1 2 3`

---

## **Question 17**

### **Code Snippet:**
```text
function fun(n)
    if (n == 1)
        return 1
    end if
    return n * fun(n - 1)
end function

// Main call:
print fun(5)
```

### **Answer:** `120`

### **Step-by-Step Explanation:**
1. Function implements Factorial $n!$.
2. `fun(5) = 5 * fun(4)` = $5 \times 4 \times 3 \times 2 \times 1 = 120$.
3. **Print:** `120`

---

## **Question 18**

### **Code Snippet:**
```text
Integer sum = 0
Integer i

for (i = 1 to 7)
    sum = sum + (i * i)
end for

print sum
```

### **Answer:** `140`

### **Step-by-Step Explanation:**
1. Calculates sum of squares $\sum_{i=1}^{7} i^2$.
2. Formula: $\frac{n(n+1)(2n+1)}{6}$ for $n = 7$:
   * $\frac{7 \times 8 \times 15}{6} = 140$.
3. **Print:** `140`

---

## **Question 19**

### **Code Snippet:**
```text
function test()
    static Integer count = 0
    count = count + 1
    return count
end function

// Main execution:
test()
test()
print test()
```

### **Answer:** `3`

### **Step-by-Step Explanation:**
1. `count` is `static`, retaining its value across function calls.
2. 1st call: `count` becomes `1`.
3. 2nd call: `count` becomes `2`.
4. 3rd call: `count` becomes `3` and is returned.