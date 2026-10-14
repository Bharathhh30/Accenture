# Accenture Exam Coding Questions & Solutions

This reference guide contains the coding problems asked in Accenture recruitment exams, complete with detailed problem statements, step-by-step logic, edge cases, complexity analyses, and implementation in **Python**, **C++**, and **Java**.

---

## **Problem 1: Array Element Transformation & Sum**

### **Problem Statement**
Given a 0-indexed integer array `nums` of length `N`, transform each element at index `i` according to the following rules:
1. **Base Decrement:** Subtract $(i \bmod 7) \times 3$ from `nums[i]`.
2. **Divisibility Bonus:** If the **original** value of `nums[i]` is divisible by `11`, add $\lfloor \text{nums}[i] / 11 \rfloor$ to the transformed value.

Calculate and return the **total sum** of all transformed array elements.

---

### **Input & Output Format**
* **Input:**
  * An integer `N` representing the length of the array.
  * An array `nums` of size `N`.
* **Output:**
  * A single integer representing the sum of transformed elements.

---

### **Sample Test Cases**

#### **Test Case 1**
* **Input:** `nums = [22, 5, 14]`
* **Step-by-Step Processing:**
  * **Index 0 (`val = 22`):**
    * Base transformation: $22 - ((0 \bmod 7) \times 3) = 22 - 0 = 22$
    * Divisibility check: $22 \bmod 11 == 0 \implies \text{add } 22 / 11 = 2$
    * Transformed value: $22 + 2 = \mathbf{24}$
  * **Index 1 (`val = 5`):**
    * Base transformation: $5 - ((1 \bmod 7) \times 3) = 5 - 3 = 2$
    * Divisibility check: $5 \bmod 11 \neq 0 \implies \text{add } 0$
    * Transformed value: $\mathbf{2}$
  * **Index 2 (`val = 14`):**
    * Base transformation: $14 - ((2 \bmod 7) \times 3) = 14 - 6 = 8$
    * Divisibility check: $14 \bmod 11 \neq 0 \implies \text{add } 0$
    * Transformed value: $\mathbf{8}$
* **Total Sum:** $24 + 2 + 8 = \mathbf{34}$
* **Output:** `34`

#### **Test Case 2**
* **Input:** `nums = [0, 11, 33]`
* **Step-by-Step Processing:**
  * **Index 0 (`val = 0`):**
    * Transformation: $0 - 0 = 0$. $0 \bmod 11 == 0 \implies \text{add } 0 / 11 = 0 \implies \mathbf{0}$
  * **Index 1 (`val = 11`):**
    * Transformation: $11 - 3 = 8$. $11 \bmod 11 == 0 \implies \text{add } 11 / 11 = 1 \implies \mathbf{9}$
  * **Index 2 (`val = 33`):**
    * Transformation: $33 - 6 = 27$. $33 \bmod 11 == 0 \implies \text{add } 33 / 11 = 3 \implies \mathbf{30}$
* **Total Sum:** $0 + 9 + 30 = \mathbf{39}$
* **Output:** `39`

---

### **Complexity Analysis**
* **Time Complexity:** $\mathcal{O}(N)$ where $N$ is the number of elements in `nums`. We traverse the array once.
* **Space Complexity:** $\mathcal{O}(1)$ auxiliary space as we only maintain running sums.

---

### **Code Solutions**

#### **Python 3**
```python
def transform_array_sum(nums):
    total_sum = 0
    for i, val in enumerate(nums):
        # Apply base subtraction
        modified = val - ((i % 7) * 3)
        
        # Check divisibility condition on original value
        if val % 11 == 0:
            modified += val // 11
            
        total_sum += modified
        
    return total_sum

# Example Usage
if __name__ == "__main__":
    nums = [22, 5, 14]
    print(transform_array_sum(nums))  # Output: 34
```

#### **C++**
```cpp
#include <iostream>
#include <vector>

long long transformArraySum(const std::vector<int>& nums) {
    long long total_sum = 0;
    for (size_t i = 0; i < nums.size(); ++i) {
        long long val = nums[i];
        long long modified = val - ((i % 7) * 3);
        
        if (val % 11 == 0) {
            modified += (val / 11);
        }
        
        total_sum += modified;
    }
    return total_sum;
}

int main() {
    std::vector<int> nums = {22, 5, 14};
    std::cout << transformArraySum(nums) << std::endl; // Output: 34
    return 0;
}
```

#### **Java**
```java
import java.util.Scanner;

public class ArrayTransformSum {
    public static long transformArraySum(int[] nums) {
        long totalSum = 0;
        for (int i = 0; i < nums.length; i++) {
            long val = nums[i];
            long modified = val - ((i % 7) * 3);
            
            if (val % 11 == 0) {
                modified += (val / 11);
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

---

## **Problem 2: Equivalent Sum Count (Binary Search Optimization)**

### **Problem Statement**
For any positive integer $X$, its **Equivalent Sum** ($\text{eq\_sum}(X)$) is defined as the sum of all prefix sub-numbers formed by reading $X$ digit-by-digit from left to right.

* **Example:** For $X = 105$:
  * Prefixes formed are: `1`, `10`, `105`.
  * $\text{eq\_sum}(105) = 1 + 10 + 105 = 116$.

Given a positive integer $N$, count how many integers $X$ in the range $1 \le X < N$ satisfy:
$$\text{eq\_sum}(X) > N$$

---

### **Key Insights & Algorithm**

1. **Monotonicity Property:** 
   * As $X$ increases, $\text{eq\_sum}(X)$ strictly increases.
   * Because of this monotonic nature, if $\text{eq\_sum}(X) > N$ holds for some $X$, it will also hold for all numbers $Y > X$.

2. **Why Linear Search Fails:**
   * Checking every number from $1$ to $N-1$ takes $\mathcal{O}(N \log_{10} N)$ time.
   * For $N = 10^9$, this will lead to a **Time Limit Exceeded (TLE)** error.

3. **Binary Search Optimization:**
   * Perform Binary Search over the integer range $[1, N-1]$ to find the **first (smallest) integer** $X_{\text{first}}$ such that $\text{eq\_sum}(X_{\text{first}}) > N$.
   * Since all integers in $[X_{\text{first}}, N-1]$ will also satisfy the condition, the total count of such valid numbers is:
     $$\text{Result} = N - X_{\text{first}}$$

---

### **Sample Test Case**

* **Input:** $N = 112$
* **Target:** Find count of $X \in [1, 111]$ where $\text{eq\_sum}(X) > 112$.
* **Trace:**
  * For $X = 101 \implies 1 + 10 + 101 = 112$ ($\le 112$, Invalid)
  * For $X = 102 \implies 1 + 10 + 102 = 113$ ($> 112$, First Valid $X$)
* **Valid Range:** $X \in [102, 111]$
* **Total Valid Count:** $112 - 102 = \mathbf{10}$
* **Output:** `10`

---

### **Complexity Analysis**
* **Time Complexity:** $\mathcal{O}(\log N \times \log_{10} N)$
  * Binary Search runs in $\mathcal{O}(\log N)$ iterations.
  * In each iteration, computing $\text{eq\_sum}(X)$ takes $\mathcal{O}(\log_{10} X)$ digit operations.
* **Space Complexity:** $\mathcal{O}(1)$ auxiliary space.

---

### **Code Solutions**

#### **Python 3**
```python
def get_eq_sum(x: int) -> int:
    s_str = str(x)
    total_sum = 0
    curr_prefix = 0
    for digit in s_str:
        curr_prefix = curr_prefix * 10 + int(digit)
        total_sum += curr_prefix
    return total_sum

def count_equivalent_sums(n: int) -> int:
    low = 1
    high = n - 1
    first_valid = n  # Default if no number satisfies condition
    
    while low <= high:
        mid = (low + high) // 2
        
        if get_eq_sum(mid) > n:
            first_valid = mid
            high = mid - 1  # Try finding a smaller valid X
        else:
            low = mid + 1   # X is too small, search right
            
    return n - first_valid

# Example Usage
if __name__ == "__main__":
    n = 112
    print(count_equivalent_sums(n))  # Output: 10
```

#### **C++**
```cpp
#include <iostream>
#include <string>

// Helper function to calculate equivalent sum
long long getEqSum(long long x) {
    std::string s = std::to_string(x);
    long long total_sum = 0;
    long long curr_prefix = 0;
    
    for (char digit : s) {
        curr_prefix = curr_prefix * 10 + (digit - '0');
        total_sum += curr_prefix;
    }
    return total_sum;
}

long long countEquivalentSums(long long n) {
    long long low = 1;
    long long high = n - 1;
    long long first_valid = n;
    
    while (low <= high) {
        long long mid = low + (high - low) / 2;
        
        if (getEqSum(mid) > n) {
            first_valid = mid;
            high = mid - 1; // Look for a smaller valid candidate on the left
        } else {
            low = mid + 1;  // Search right
        }
    }
    
    return n - first_valid;
}

int main() {
    long long n = 112;
    std::cout << countEquivalentSums(n) << std::endl; // Output: 10
    return 0;
}
```

#### **Java**
```java
public class EquivalentSumBinarySearch {
    
    // Function to calculate equivalent sum of X
    private static long getEqSum(long x) {
        String s = String.valueOf(x);
        long totalSum = 0;
        long currPrefix = 0;
        
        for (int i = 0; i < s.length(); i++) {
            currPrefix = currPrefix * 10 + (s.charAt(i) - '0');
            totalSum += currPrefix;
        }
        return totalSum;
    }

    public static long countEquivalentSums(long n) {
        long low = 1;
        long high = n - 1;
        long firstValid = n;
        
        while (low <= high) {
            long mid = low + (high - low) / 2;
            
            if (getEqSum(mid) > n) {
                firstValid = mid;
                high = mid - 1; // Try to find a smaller valid X
            } else {
                low = mid + 1;  // X is too small
            }
        }
        
        return n - firstValid;
    }

    public static void main(String[] args) {
        long n = 112;
        System.out.println(countEquivalentSums(n)); // Output: 10
    }
}
```