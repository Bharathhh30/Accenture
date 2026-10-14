# Pseudocode and Output Tracing

## Concepts to learn

- **Execution order:** Read statements top to bottom; a variable's latest assigned value is the one used next.
- **Conditions:** `if/else` selects one branch. For compound conditions, apply parentheses and operator precedence carefully.
- **Loops:** Track initialization, loop condition, update, and body. Check whether the end value is inclusive.
- **Counters and accumulators:** A counter often increments by one; an accumulator combines values (commonly by addition or multiplication).
- **Integer division and remainder:** In the questions here, `/` between integers means floor division for nonnegative values; `%` gives the remainder.
- **Arrays:** These questions use **zero-based indexing**, so the first element is at index 0.
- **Functions and recursion:** Follow argument values and return statements; each recursive call must make progress toward a base case.
- **Operators:** `AND` requires both operands true; `OR` requires at least one; `NOT` reverses truth. Compare values before updating them.
- **Tracing method:** Make a small table of variables per iteration. Don't mentally skip iterations.

## Original practice MCQs

Assume zero-based arrays, integer division as defined above, and inclusive loop bounds unless a question says otherwise.

### Questions

1. What is printed?
   ```
   x = 3
   x = x + 4
   x = x * 2
   print x
   ```
   A) 10  B) 11  C) 14  D) 16

2. What is the final value of `sum`?
   ```
   sum = 0
   for i = 1 to 4
       sum = sum + i
   ```
   A) 6  B) 10  C) 12  D) 16

3. What is printed?
   ```
   n = 17
   print n / 5, n % 5
   ```
   A) 3, 2  B) 3.4, 2  C) 2, 3  D) 4, 1

4. Given `A = [8, 3, 6, 1]`, what is `A[2] + A[0]`?
   A) 9  B) 11  C) 14  D) 17

5. What is printed?
   ```
   x = 5
   if x > 5
       print "A"
   else if x == 5
       print "B"
   else
       print "C"
   ```
   A) A  B) B  C) C  D) Nothing

6. How many times does the loop body execute?
   ```
   count = 0
   i = 2
   while i <= 10
       count = count + 1
       i = i + 2
   ```
   A) 4  B) 5  C) 6  D) 8

7. A function returns `x*x + 1`. What does `f(4)` return?
   A) 9  B) 16  C) 17  D) 25

8. What is printed?
   ```
   x = 1
   for i = 1 to 3
       x = x * 2
   print x
   ```
   A) 6  B) 7  C) 8  D) 9

### Answer key and explanations

1. **C — 14.** First `x` becomes 7, then 14.
2. **B — 10.** The loop adds 1 + 2 + 3 + 4.
3. **A — 3, 2.** 17 divided by 5 has quotient 3 and remainder 2.
4. **C — 14.** `A[2]` is 6 and `A[0]` is 8.
5. **B — B.** The first condition is false; equality with 5 is true.
6. **B — 5.** `i` takes 2, 4, 6, 8, and 10; then it becomes 12.
7. **C — 17.** `4*4 + 1 = 17`.
8. **C — 8.** Starting at 1, multiply by 2 three times.
