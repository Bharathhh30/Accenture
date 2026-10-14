# Accenture Pseudo Code Questions & Solutions

This document contains detailed step-by-step solutions and explanations for the pseudo code questions asked in Accenture exams based on the video tutorial.

---

## **Operators Quick Reference**
- `^` denotes **Bitwise XOR** (Same bits = `0`, Different bits = `1`).
- `&` denotes **Bitwise AND** (Both bits `1` = `1`, otherwise `0`).
- `+`, `-`, `*`, `/` follow standard arithmetic precedence unless modified by parentheses.

---

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
   - `array[0] = 0`
   - `array[1] = 2`
   - `array[2] = 0`
   - `array[3] = 3`

2. **Evaluate the `if` condition:**
   - Condition: `(array[0] & array[1] & array[2])`
   - Evaluate: `0 & 2 & 0` = `0` (False).
   - Since the condition evaluates to `0` (False), the code inside the `if` block is **skipped**.

3. **Execute Statement:**
   - `array[0] = array[1] + array[2]`
   - `array[0] = 2 + 0 = 2`

4. **Print Expression:**
   - Print `array[1] + array[2]`
   - `2 + 0 = 2`

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
`31`

### **Step-by-Step Explanation:**
1. **Initial Values:**
   - `a = 8`, `b = 3`, `c = 10`

2. **Evaluate `c = b ^ b + c`:**
   - In standard operator precedence, addition `+` has higher priority than XOR `^`.
   - Calculate `b + c` first: `3 + 10 = 13`.
   - Now calculate `b ^ 13`:
     - Binary of `3`  = `0011`
     - Binary of `13` = `1101`
     - `3 ^ 13`      = `1110` (14 in decimal)
   - Updated `c = 14`.

3. **Evaluate `c = c + 10 + 10`:**
   - `c = 14 + 10 + 10 = 34`
   - Updated `c = 34`.

4. **Print Expression:**
   - Print `a + b + c`
   - `8 + 3 + 34 = 45`

*(Note: If evaluated as `(b ^ b) + c` where `b ^ b = 0`, then `c = 10`, `c = 30`, total = `41`. However, following strictly operator precedence rules where arithmetic addition precedes bitwise XOR, the output is calculated accordingly as above).*

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
`27`

### **Step-by-Step Explanation:**
1. **Initial Values:**
   - `p = 7`, `q = 6`, `r = 4`

2. **Evaluate Outer `if` Condition:** `(q ^ p) < r`
   - Calculate `q ^ p` (`6 ^ 7`):
     - `6` in binary = `0110`
     - `7` in binary = `0111`
     - `6 ^ 7`       = `0001` (1 in decimal)
   - Check condition: `1 < 4` -> **True**.
   - Enter the outer `if` block.

3. **Evaluate Inner `if` Condition:** `((8 ^ r) + (7 + p) > (q ^ p))`
   - Left side:
     - `8 ^ r` (`8 ^ 4`):
       - `8` in binary = `1000`
       - `4` in binary = `0100`
       - `8 ^ 4`       = `1100` (12 in decimal)
     - `7 + p` = `7 + 7 = 14`
     - `(8 ^ r) + (7 + p)` = `12 + 14 = 26`
   - Right side: `q ^ p = 1`
   - Check condition: `26 > 1` -> **True**.
   - Enter the inner `if` block.

4. **Execute `q = (12 & 11) ^ q`:**
   - Calculate `12 & 11`:
     - `12` in binary = `1100`
     - `11` in binary = `1011`
     - `12 & 11`      = `1000` (8 in decimal)
   - Now calculate `8 ^ q` (`8 ^ 6`):
     - `8` in binary = `1000`
     - `6` in binary = `0110`
     - `8 ^ 6`       = `1110` (14 in decimal)
   - Updated `q = 14`.

5. **Execute Statement outside `if`:**
   - `r = 7 + p`
   - `r = 7 + 7 = 14`

6. **Print Expression:**
   - Print `p + q + r`
   - `7 + 14 + 14 = 35`

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
`45`

### **Step-by-Step Explanation:**
1. **Initial Values:**
   - `a = 5`, `b = 2`, `c = 6`

2. **Evaluate `b = (a + 6) ^ a`:**
   - `a + 6 = 5 + 6 = 11`
   - Calculate `11 ^ 5`:
     - `11` in binary = `1011`
     - `5` in binary  = `0101`
     - `11 ^ 5`       = `1110` (14 in decimal)
   - Updated `b = 14`.

3. **Evaluate `c = (1 + 3) & b`:**
   - `1 + 3 = 4`
   - Calculate `4 & 14`:
     - `4` in binary  = `0100`
     - `14` in binary = `1110`
     - `4 & 14`       = `0100` (4 in decimal)
   - Updated `c = 4`.

4. **Evaluate `b = 9 + 7 + b`:**
   - `b = 9 + 7 + 14 = 30`
   - Updated `b = 30`.

5. **Print Expression:**
   - Print `a + b + c`
   - `5 + 30 + 4 = 39`

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
This pseudo code calculates the sum of numbers from `1` to `5` using a `while` loop.

1. **Iteration 1:**
   - Condition `1 <= 5` (True)
   - `result = 0 + 1 = 1`
   - `count = 1 + 1 = 2`

2. **Iteration 2:**
   - Condition `2 <= 5` (True)
   - `result = 1 + 2 = 3`
   - `count = 2 + 1 = 3`

3. **Iteration 3:**
   - Condition `3 <= 5` (True)
   - `result = 3 + 3 = 6`
   - `count = 3 + 1 = 4`

4. **Iteration 4:**
   - Condition `4 <= 5` (True)
   - `result = 6 + 4 = 10`
   - `count = 4 + 1 = 5`

5. **Iteration 5:**
   - Condition `5 <= 5` (True)
   - `result = 10 + 5 = 15`
   - `count = 5 + 1 = 6`

6. **Loop Ends:**
   - Condition `6 <= 5` (False) -> Exit loop.

7. **Print Result:**
   - Outputs `15`.