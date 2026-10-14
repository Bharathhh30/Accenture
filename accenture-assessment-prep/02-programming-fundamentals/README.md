# Programming Fundamentals

## Concepts to learn

- **Variables and types:** A variable stores a value; common types include integer, floating-point number, Boolean, and character/string. Type rules affect arithmetic and comparisons.
- **Assignment vs equality:** Assignment stores a value (`x = 5`); equality tests whether values match (`x == 5` in many languages).
- **Control flow:** Sequence, selection (`if`), and iteration (loops) are the basic ways a program chooses and repeats work.
- **Functions:** Named reusable units can accept parameters and return results. Know the difference between a parameter (definition) and argument (call).
- **Scope:** Local variables are limited to a function/block; global variables can be accessed more broadly, subject to language rules.
- **Errors:** Syntax errors violate grammar; runtime errors occur during execution; logic errors run but produce incorrect results.
- **Arrays and strings:** Arrays store indexed sequences; strings represent text and may be immutable depending on language.
- **Boolean logic:** De Morgan's laws: `NOT (A AND B)` equals `(NOT A) OR (NOT B)`; `NOT (A OR B)` equals `(NOT A) AND (NOT B)`.
- **Basic complexity:** `O(1)` is constant work, `O(n)` grows roughly with input size, and a simple nested `n`-by-`n` loop is often `O(n²)`.

## Original practice MCQs

### Questions

1. Which is a Boolean value?
   A) `"false"` (text)  B) `0.5`  C) `false`  D) `'F'`

2. In most C-like languages, what does `x = x + 1` do?
   A) Tests if x is 1  B) Increases x by one  C) Resets x to zero  D) Declares x

3. Which error most likely occurs when a program runs successfully but calculates the wrong total?
   A) Syntax error  B) Logic error  C) Linker error only  D) Hardware error

4. A function definition has `g(value)`. In a call `g(12)`, what is `12`?
   A) Return type  B) Argument  C) Loop  D) Scope

5. Which expression is equivalent to `NOT (P AND Q)`?
   A) `NOT P AND NOT Q`  B) `NOT P OR NOT Q`  C) `P OR Q`  D) `P AND NOT Q`

6. A loop processes each of `n` items once, doing constant work per item. Its time complexity is typically:
   A) O(1)  B) O(log n)  C) O(n)  D) O(n²)

7. Which is usually a runtime error?
   A) Missing closing parenthesis caught before execution
   B) Dividing an integer by zero during execution
   C) Using a misleading variable name
   D) A comment with a typo

8. A variable declared inside a function is generally:
   A) Local to that function  B) Always global  C) A data type  D) A compiler

### Answer key and explanations

1. **C.** `false` without quotation marks is a Boolean literal; `"false"` is text.
2. **B.** The expression adds one and assigns the new value back to `x`.
3. **B.** A logic error is syntactically valid but does not implement the intended behavior.
4. **B.** The supplied value in a call is an argument; `value` is the parameter name.
5. **B.** This is De Morgan's law.
6. **C.** Work increases proportionally with the number of items.
7. **B.** The failure happens while the program executes. The exact behavior is language-dependent, but it is a runtime failure in this scenario.
8. **A.** Function-local scope is the common default; details can vary by language.
