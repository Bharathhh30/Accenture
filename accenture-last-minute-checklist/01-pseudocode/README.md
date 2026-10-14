# Pseudocode

**Assessment priority: High evidence** — named in recent candidate/preparation descriptions; output-tracing style and syntax can vary.

| Concept | One-line last-minute reminder |
|---|---|
| Statement order | Execute assignments and output statements in order, carrying each updated value forward. |
| Assignment vs comparison | Assignment stores a value; equality comparison tests whether two values are equal. |
| Operator precedence | Apply parentheses first, then unary, multiplicative, additive, comparison, and logical operations according to the language's rules. |
| Integer division and modulo | For nonnegative integers, quotient drops the fractional part and modulo returns the remainder. |
| Pre/post increment | Prefix increment changes the variable before its value is used; postfix uses the old value and increments afterward. |
| Conditional branches | Only the first matching branch of an `if / else if / else` chain executes. |
| Boolean logic | `AND` needs both true, `OR` needs at least one true, and `NOT` reverses a truth value. |
| Short-circuit evaluation | In short-circuit logic, a decisive first operand may prevent evaluation of the second operand. |
| Loop boundaries | Check start, end inclusivity, condition, update, and whether the loop can execute zero times. |
| Nested loops | Multiply iteration counts when independent; add iterations when an inner bound changes with the outer index. |
| `break` and `continue` | `break` exits the nearest loop; `continue` skips to that loop's next iteration. |
| Counters and accumulators | A counter tracks events; an accumulator combines values such as a running sum or product. |
| Arrays and indexing | Confirm zero- versus one-based indexing and update array elements in statement order. |
| Strings and character codes | Know the stated encoding and whether an operation counts characters, bytes, or a substring. |
| Functions and return | Substitute arguments into parameters and follow the exact return path, including early returns. |
| Pass-by-value | A copied argument can change inside a function without changing the caller's variable. |
| Pass-by-reference | A reference parameter can modify the caller's original variable. |
| Recursion | Trace each call until the base case, then unwind return values from deepest call upward. |
| Scope and lifetime | A local variable's visibility and lifetime depend on its block and language storage rules. |
| Bitwise operators | Convert to binary for AND/OR/XOR/shifts; do not confuse bitwise operators with Boolean logic. |
| Pointers and aliases | Follow whether two names refer to the same storage location before predicting a mutation. |
| Dry-run table | Record loop index and changed variables after every iteration to avoid skipped updates. |
| Edge cases | Check empty/one-element inputs, zero, negative values, repeated values, and boundary indices. |
| Complexity basics | One pass is commonly O(n); nested full passes O(n²); halving search ranges O(log n). |
| Language-specific semantics | Do not assume C, Java, Python, or pseudocode share integer, overflow, evaluation, or increment behavior. |
