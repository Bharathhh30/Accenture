
---

# Accenture Technical MCQ & Coding 1-SHOT | Preparation Notes

---

## 📌 Section 1: Technical MCQs & Core Computer Science Concepts

### **Question 1: Operating System - Process State Transitions**

A process is currently in the **Running State** and issues a request for an I/O operation. What transition will most likely happen to the process?

* A) Moves to the Ready State
* B) Moves to the Terminated State
* C) Moves to the Wait / Blocked State
* D) Remains in the Running State

**Answer:** **C) Moves to the Wait / Blocked State**

* **Explanation:** When a running process requests I/O or secondary storage file retrieval, the CPU suspends its execution and shifts it to the **Wait / Blocked State** until the I/O completes.

```
[New] --> [Ready] <=====> [Running] --> [Terminated]
           ^                |
           |                v
           +--- [Wait/Block]

```

---

### **Question 2: Operating System - CPU Schedulers**

Which CPU scheduler is primarily responsible for selecting a process from the **Ready Queue** and dispatching it to the CPU for execution?

* A) Long-Term Scheduler (LTS)
* B) Medium-Term Scheduler (MTS)
* C) Short-Term Scheduler (STS) / CPU Scheduler
* D) Job Scheduler

**Answer:** **C) Short-Term Scheduler (STS) / CPU Scheduler**

* **Explanation:**
* **Long-Term Scheduler (LTS):** Controls the degree of multiprogramming by bringing jobs from secondary memory (disk) to main memory (RAM / Ready Queue).
* **Short-Term Scheduler (STS):** Selects process from Ready Queue (RAM) and assigns CPU time.
* **Medium-Term Scheduler (MTS):** Handles process swapping between main memory and secondary storage (suspended states).



---

### **Question 3: Operating System - Scheduler Statements**

Which of the following statements regarding schedulers is **correct**?

* A) Long-Term Scheduler controls CPU allocation every few milliseconds.
* B) Short-Term Scheduler controls the degree of multiprogramming.
* C) Medium-Term Scheduler can temporarily remove processes from memory (swapping).
* D) Long-Term Scheduler performs context switching for every CPU burst.

**Answer:** **C) Medium-Term Scheduler can temporarily remove processes from memory (swapping).**

* **Explanation:** MTS manages process swapping between RAM and disk whenever memory becomes full, moving them into suspended wait/ready states.

---

### **Question 4: Operating System - Synchronization Mechanisms**

A shared resource must be accessed by **at most one thread at a time**. Which synchronization mechanism is directly suited for enforcing this mutual exclusion?

* A) Counting Semaphore
* B) Mutex (Mutual Exclusion Lock)
* C) Barrier
* D) Condition Variable

**Answer:** **B) Mutex (Mutual Exclusion Lock)**

* **Explanation:**
* **Mutex:** Binary locking mechanism (`0` or `1`) allowing only **one thread** to access the critical section at a time.
* **Counting Semaphore:** Integer counter allowing **up to $N$ threads** simultaneously.



---

### **Question 5: Operating System - Counting Semaphore Logic**

A Counting Semaphore has an initial value of **3**. Four processes simultaneously attempt to perform a `wait()` operation on it. How many processes can immediately enter the critical section?

* A) 1
* B) 2
* C) 3
* D) 4

**Answer:** **C) 3**

* **Explanation:** The counting semaphore permits entry to $N$ processes matching its initial counter value ($3$). The $4^{\text{th}}$ process blocks until one of the active processes calls `signal()`.

---

## 📌 Section 2: Coding Questions & Implementation

---

### **Problem 1: Validate Password (Easy Track)**

#### **Problem Description**

Implement a function `checkPassword(str, n)` that returns `1` if the password string `str` is valid, and `0` otherwise.

#### **Validation Rules:**

1. Length must be **at least 4 characters** (`n >= 4`).
2. Must contain at least **1 numeric digit** (`0–9`).
3. Must contain at least **1 capital letter** (`A–Z`).
4. Must **NOT** contain any white space (`' '`) or forward slash (`'/'`).
5. The **first character cannot be a number**.

---

#### **Java Implementation:**

```java
public class Solution {
    public static int checkPassword(String str, int n) {
        // Rule 1: Minimum length check
        if (n < 4) return 0;

        // Rule 5: First character cannot be a digit
        if (str.charAt(0) >= '0' && str.charAt(0) <= '9') {
            return 0;
        }

        boolean hasNum = false;
        boolean hasCap = false;

        for (int i = 0; i < n; i++) {
            char ch = str.charAt(i);

            // Rule 4: No whitespace or slashes
            if (ch == ' ' || ch == '/') {
                return 0;
            }

            // Rule 3: Capital letter check
            if (ch >= 'A' && ch <= 'Z') {
                hasCap = true;
            }

            // Rule 2: Numeric digit check
            if (ch >= '0' && ch <= '9') {
                hasNum = true;
            }
        }

        return (hasCap && hasNum) ? 1 : 0;
    }

    public static void main(String[] args) {
        String pass1 = "aA1_67";
        System.out.println(checkPassword(pass1, pass1.length())); // Output: 1

        String pass2 = "aA 1_67";
        System.out.println(checkPassword(pass2, pass2.length())); // Output: 0
    }
}

```

#### **Python Implementation:**

```python
def check_password(s: str, n: int) -> int:
    # Rule 1: Minimum length check
    if n < 4:
        return 0

    # Rule 5: First character cannot be a number
    if '0' <= s[0] <= '9':
        return 0

    has_num = False
    has_cap = False

    for char in s:
        # Rule 4: No space or slash
        if char == ' ' or char == '/':
            return 0

        # Rule 3: Capital letter check
        if 'A' <= char <= 'Z':
            has_cap = True

        # Rule 2: Numeric digit check
        if '0' <= char <= '9':
            has_num = True

    return 1 if (has_cap and has_num) else 0

# Test cases
print(check_password("aA1_67", 6))  # Output: 1
print(check_password("1aA_67", 6))  # Output: 0

```

---

### **Problem 2: Linked List Cycle II (Find Start of Cycle)**

#### **Problem Description**

Given the head of a linked list, return the node where the cycle begins. If there is no cycle, return `null`.

---

#### **Algorithm (Floyd's Cycle-Finding / Two Pointers):**

1. **Phase 1 (Cycle Detection):** Use `slow` (moves 1 step) and `fast` (moves 2 steps) pointers. If `slow == fast`, a cycle exists.
2. **Phase 2 (Find Entry Point):** Reset `temp` pointer to `head`. Move `temp` and `slow` 1 step at a time until `temp == slow`. Their intersection node is the start of the cycle.

---

#### **Java Implementation:**

```java
class ListNode {
    int val;
    ListNode next;
    ListNode(int x) {
        val = x;
        next = null;
    }
}

public class SolutionLinkedList {
    public static ListNode detectCycle(ListNode head) {
        if (head == null || head.next == null) {
            return null;
        }

        ListNode slow = head;
        ListNode fast = head;
        boolean hasCycle = false;

        // Phase 1: Detect Cycle
        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;
            if (slow == fast) {
                hasCycle = true;
                break;
            }
        }

        if (!hasCycle) {
            return null;
        }

        // Phase 2: Locate Cycle Start Node
        ListNode temp = head;
        while (temp != slow) {
            temp = temp.next;
            slow = slow.next;
        }

        return temp; // Starting node of the cycle
    }
}

```

#### **Python Implementation:**

```python
class ListNode:
    def __init__(self, x):
        self.val = x
        self.next = None

def detect_cycle(head: ListNode) -> ListNode:
    if not head or not head.next:
        return None

    slow = head
    fast = head
    has_cycle = False

    # Phase 1: Detect Cycle
    while fast and fast.next:
        slow = slow.next
        fast = fast.next.next
        if slow == fast:
            has_cycle = True
            break

    if not has_cycle:
        return None

    # Phase 2: Find Cycle Entrance
    temp = head
    while temp != slow:
        temp = temp.next
        slow = slow.next

    return temp

```