# Accenture Exam Coding Questions & Solutions

This document contains full coding problems from recent Accenture exams, complete with detailed explanations, algorithms, and implementations in **Java** and **Python**.

---

## **Problem 1: Number of 1 Bits (Set Bits / Hamming Weight)**

### **Problem Description**
Given a positive integer $n$, write a function that returns the number of set bits (1s) in its binary representation.

* **Example 1:**
  * **Input:** `n = 11` (Binary: `1011`)
  * **Output:** `3`
* **Example 2:**
  * **Input:** `n = 128` (Binary: `10000000`)
  * **Output:** `1`

---

### **Approach: Brian Kernighan's Algorithm (Optimal)**
Instead of inspecting all 32 bits, Brian Kernighan’s algorithm uses the bitwise operation `n = n & (n - 1)`, which directly erases the rightmost set bit in a single step.

* **Time Complexity:** $\mathcal{O}(K)$, where $K$ is the number of set bits (1s).
* **Space Complexity:** $\mathcal{O}(1)$.

#### **Dry Run for `n = 42` (`101010` in binary):**
1. `n = 42` (`101010`), `n - 1 = 41` (`101001`) $\rightarrow$ `42 & 41 = 40` (`101000`), `count = 1`
2. `n = 40` (`101000`), `n - 1 = 39` (`100111`) $\rightarrow$ `40 & 39 = 32` (`100000`), `count = 2`
3. `n = 32` (`100000`), `n - 1 = 31` (`011111`) $\rightarrow$ `32 & 31 = 0` (`000000`), `count = 3`
4. `n = 0`, loop terminates. **Output:** `3`

---

### **Java Implementation:**

```java
public class Solution {
    public static int countSetBits(int n) {
        int count = 0;
        while (n > 0) {
            n = n & (n - 1); // Clears the lowest set bit
            count++;
        }
        return count;
    }

    public static void main(String[] args) {
        System.out.println(countSetBits(11));  // Output: 3
        System.out.println(countSetBits(128)); // Output: 1
    }
}
```

### **Python Implementation:**

```python
def count_set_bits(n: int) -> int:
    count = 0
    while n > 0:
        n = n & (n - 1)  # Clears the lowest set bit
        count += 1
    return count

# Test Cases
print(count_set_bits(11))   # Output: 3
print(count_set_bits(128))  # Output: 1
```

---

## **Problem 2: Valid Anagram**

### **Problem Description**
Given two strings `s` and `t`, return `true` if `t` is an anagram of `s`, and `false` otherwise. An Anagram is formed by rearranging the letters of a string using all the original letters exactly once.

* **Example 1:** `s = "anagram"`, `t = "nagaram"` $\rightarrow$ `true`
* **Example 2:** `s = "rat"`, `t = "car"` $\rightarrow$ `false`

---

### **Approach: Frequency Count Array (Optimal)**
Track character frequencies using a fixed-size integer array of size 26 (for lowercase English letters).
1. Increment bucket value for each character in string `s`.
2. Decrement bucket value for each character in string `t`.
3. Verify that all 26 bucket entries are `0`.

* **Time Complexity:** $\mathcal{O}(N)$
* **Space Complexity:** $\mathcal{O}(1)$ (fixed frequency array of size 26).

---

### **Java Implementation:**

```java
public class Solution {
    public static boolean isAnagram(String str1, String str2) {
        // Clean and normalize strings
        str1 = str1.toLowerCase().replace(" ", "");
        str2 = str2.toLowerCase().replace(" ", "");

        if (str1.length() != str2.length()) {
            return false;
        }

        int[] counts = new int[26];

        for (int i = 0; i < str1.length(); i++) {
            counts[str1.charAt(i) - 'a']++;
            counts[str2.charAt(i) - 'a']--;
        }

        for (int count : counts) {
            if (count != 0) {
                return false;
            }
        }

        return true;
    }

    public static void main(String[] args) {
        System.out.println(isAnagram("anagram", "nagaram")); // Output: true
        System.out.println(isAnagram("rat", "car"));         // Output: false
    }
}
```

### **Python Implementation:**

```python
def is_anagram(str1: str, str2: str) -> bool:
    # Clean and normalize strings
    str1 = str1.lower().replace(" ", "")
    str2 = str2.lower().replace(" ", "")

    if len(str1) != len(str2):
        return False

    counts = [0] * 26

    for i in range(len(str1)):
        counts[ord(str1[i]) - ord('a')] += 1
        counts[ord(str2[i]) - ord('a')] -= 1

    for count in counts:
        if count != 0:
            return False

    return True

# Test Cases
print(is_anagram("anagram", "nagaram")) # Output: True
print(is_anagram("rat", "car"))         # Output: False
```

---

## **Problem 3: Floyd's Triangle**

### **Problem Description**
Given a positive integer $N$, print Floyd's Triangle with $N$ rows. Floyd's triangle is a right-angled triangular array of natural numbers incrementing continuously across rows.

* **Example Input:** `N = 4`
* **Example Output:**
  ```text
  1 
  2 3 
  4 5 6 
  7 8 9 10 
  ```

---

### **Approach:**
* **Outer Loop (`i`):** Controls row number from `1` to `N`.
* **Inner Loop (`j`):** Controls elements per row, running from `1` to `i`.
* **Counter:** Keeps a running total starting at `1` without resetting.

* **Time Complexity:** $\mathcal{O}(N^2)$
* **Space Complexity:** $\mathcal{O}(1)$

---

### **Java Implementation:**

```java
public class Solution {
    public static void printFloydsTriangle(int n) {
        int counter = 1;
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= i; j++) {
                System.out.print(counter + " ");
                counter++;
            }
            System.out.println();
        }
    }

    public static void main(String[] args) {
        printFloydsTriangle(4);
    }
}
```

### **Python Implementation:**

```python
def print_floyds_triangle(n: int):
    counter = 1
    for i in range(1, n + 1):
        for j in range(1, i + 1):
            print(counter, end=" ")
            counter += 1
        print()

# Test
print_floyds_triangle(4)
```

---

## **Problem 4: Array Transformation & Sum Calculation**

### **Problem Description**
Given a 0-indexed integer array `nums`, transform each element by subtracting $(i \bmod 7) \times 3$. Additionally, if the **original** element `nums[i]` is divisible by 11, add $\lfloor \text{nums}[i] / 11 \rfloor$ to the modified value. Return the total sum of transformed elements.

* **Example:**
  * **Input:** `nums = [22, 5, 14]`
  * **Output:** `34`

### **Step-by-Step Execution:**
1. `i = 0`: `22 - ((0 % 7) * 3) = 22`. Divisible by 11 $\rightarrow 22 + (22 / 11) = 24$.
2. `i = 1`: `5 - ((1 % 7) * 3) = 2`. Not divisible by 11 $\rightarrow 2$.
3. `i = 2`: `14 - ((2 % 7) * 3) = 8`. Not divisible by 11 $\rightarrow 8$.
4. **Total Sum:** $24 + 2 + 8 = 34$.

---

### **Java Implementation:**

```java
public class Solution {
    public static int transformArraySum(int[] nums) {
        int totalSum = 0;
        for (int i = 0; i < nums.length; i++) {
            int val = nums[i];
            int modified = val - ((i % 7) * 3);
            if (val % 11 == 0) {
                modified += val / 11;
            }
            totalSum += modified;
        }
        return totalSum;
    }

    public static void main(String[] args) {
        int[] nums = {22, 5, 14};
        System.out.println(transformArraySum(nums)); // Output: 34
    }
}
```

### **Python Implementation:**

```python
def transform_array_sum(nums: list[int]) -> int:
    total_sum = 0
    for i in range(len(nums)):
        val = nums[i]
        modified = val - ((i % 7) * 3)
        if val % 11 == 0:
            modified += val // 11
        total_sum += modified
    return total_sum

# Test
print(transform_array_sum([22, 5, 14])) # Output: 34
```

---

## **Problem 5: Equivalent Sum Count using Binary Search**

### **Problem Description**
For any positive integer $X$, its *Equivalent Sum* (`eq_sum(X)`) is defined as the sum of all prefix sub-numbers formed by reading $X$ from left to right (e.g., `eq_sum(105) = 1 + 10 + 105 = 116`). 

Given a target integer $N$, count all integers $X$ such that $1 \le X < N$ and $\text{eq\_sum}(X) > N$.

* **Example:**
  * **Input:** `N = 112`
  * **Output:** `10`

---

### **Approach: Binary Search Optimization**
Since `eq_sum(X)` strictly increases as $X$ increases, we can use **Binary Search** over the range $[1, N-1]$ to find the first $X$ where `eq_sum(X) > N`.
* Total valid integers = $(N - X_{\text{first\_valid}})$.
* **Time Complexity:** $\mathcal{O}(\log N \times \log_{10} N)$
* **Space Complexity:** $\mathcal{O}(1)$

---

### **Java Implementation:**

```java
public class Solution {
    private static long eqSum(long x) {
        String str = String.valueOf(x);
        long total = 0;
        long curr = 0;
        for (int i = 0; i < str.length(); i++) {
            curr = curr * 10 + (str.charAt(i) - '0');
            total += curr;
        }
        return total;
    }

    public static long countEquivalentSums(long n) {
        long low = 1, high = n - 1;
        long firstValid = n;

        while (low <= high) {
            long mid = low + (high - low) / 2;
            if (eqSum(mid) > n) {
                firstValid = mid;
                high = mid - 1; // Try to find a smaller valid number
            } else {
                low = mid + 1;
            }
        }

        return n - firstValid;
    }

    public static void main(String[] args) {
        System.out.println(countEquivalentSums(112)); // Output: 10
    }
}
```

### **Python Implementation:**

```python
def eq_sum(x: int) -> int:
    s_str = str(x)
    total = 0
    curr = 0
    for digit in s_str:
        curr = curr * 10 + int(digit)
        total += curr
    return total

def count_equivalent_sums(n: int) -> int:
    low, high = 1, n - 1
    first_valid = n

    while low <= high:
        mid = (low + high) // 2
        if eq_sum(mid) > n:
            first_valid = mid
            high = mid - 1  # Try to find a smaller valid number
        else:
            low = mid + 1

    return n - first_valid

# Test
print(count_equivalent_sums(112)) # Output: 10