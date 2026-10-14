# Source-Informed Technical Mock — 45 MCQs

**Suggested time: 45 minutes.** This is a fresh, original mock—not a reproduced Accenture test. Its section sizes follow one 2026 preparation-provider outline (12 Common Applications, 22 Pseudocode, 11 Network Security/Cloud). That is only one reported pattern; assessment content and timing can differ by role and hiring drive. A 2026 candidate account supports the broad topic mix but does not supply exact MCQs or a confirmed count. See the evidence notes in the [study-pack index](../README.md).

The pseudocode section deliberately includes code tracing plus OOP, data structures, DBMS, C I/O, and storage-class basics, because preparation material groups those subjects under “Pseudocode.” Assume zero-based indexing; loop endpoints are inclusive; integer division of nonnegative integers rounds down. C-specific items are explicitly marked.

## Section A — Common Applications / MS Office (12)

### Questions

1. In Excel, which reference remains fixed in both row and column when copied?
   A) `A1`  B) `$A$1`  C) `A$`  D) `1A`

2. Which Excel function counts cells that satisfy a specified condition?
   A) `COUNTIF`  B) `SUM`  C) `NOW`  D) `LEFT`

3. A formula needs to refer to a tax-rate cell in `$B$2` while being copied down rows. Which reference is most appropriate?
   A) `B2`  B) `$B$2`  C) `B$3`  D) `$C2`

4. Which Word feature records edits so another person can review and accept or reject them?
   A) Track Changes  B) Slide Master  C) Freeze Panes  D) Mailbox Rules

5. You need to send a document to many recipients without revealing their email addresses to one another. Which email field is intended for this?
   A) To  B) Cc  C) Bcc  D) Subject

6. In PowerPoint, an animation is generally applied to:
   A) An object on a slide  B) The transition between two slides only  C) An Excel cell  D) An Outlook folder

7. In Microsoft Access, which object stores the underlying records in rows and fields in columns?
   A) Table  B) Slide  C) Theme  D) Mail merge

8. In Access or SQL, which clause selects records meeting a condition?
   A) `WHERE`  B) `ORDER BY`  C) `INTO`  D) `PRINT`

9. Which application is the best fit for laying out a flyer or brochure for print?
   A) Publisher  B) Outlook  C) Access  D) Calculator

10. You want to display only Excel rows where the Status column is “Open,” without deleting the other rows. Use:
    A) Filter  B) Sort A to Z  C) Delete Sheet  D) Track Changes

11. Which Word feature can create personalized letters using a common template and a recipient list?
    A) Mail Merge  B) Page Color  C) AutoSum  D) Slide Sorter

12. In PowerPoint, where can a presenter keep private prompts that do not normally appear on the audience slide?
    A) Speaker Notes  B) Formula Bar  C) Bcc  D) Query Design

### Answer key

1. **B — `$A$1`.** Dollar signs fix both the column and row.
2. **A — `COUNTIF`.** It counts cells in a range that meet one criterion.
3. **B — `$B$2`.** An absolute reference stays on that cell when copied.
4. **A — Track Changes.** It records edits for review.
5. **C — Bcc.** Bcc hides those recipients from other recipients.
6. **A.** Animations affect slide objects; transitions control movement between slides.
7. **A — Table.** Access tables store the records and fields.
8. **A — `WHERE`.** It filters rows by a condition.
9. **A — Publisher.** It is a desktop-publishing/page-layout application.
10. **A — Filter.** Filtering hides nonmatching rows without removing the data.
11. **A — Mail Merge.** It combines a template with recipient data.
12. **A — Speaker Notes.** Notes support the presenter and are distinct from slide content shown to the audience.

## Section B — Pseudocode and Core CS (22)

### Questions

13. What is printed?
    ```
    total = 0
    for i = 1 to 4
        total = total + i
    print total
    ```
    A) 4  B) 6  C) 10  D) 16

14. For nonnegative integers, what does this print?
    ```
    n = 23
    print n / 4, n % 4
    ```
    A) 5, 3  B) 5.75, 3  C) 6, 1  D) 4, 7

15. Given `A = [5, 8, 2]`, execute `temp=A[0]; A[0]=A[2]; A[2]=temp`. What is `A[0]`?
    A) 2  B) 5  C) 8  D) 15

16. How many times does `count = count + 1` run?
    ```
    count = 0
    for i = 1 to 3
        for j = 1 to i
            count = count + 1
    ```
    A) 3  B) 5  C) 6  D) 9

17. A recursive function returns `1` when `n == 0`; otherwise it returns `n * f(n-1)`. What is `f(4)`?
    A) 10  B) 16  C) 24  D) 120

18. What is printed?
    ```
    values = [4, 9, 1, 7]
    largest = values[0]
    for i = 1 to 3
        if values[i] > largest
            largest = values[i]
    print largest
    ```
    A) 1  B) 4  C) 7  D) 9

19. Using bitwise AND, what is `6 AND 3`?
    A) 1  B) 2  C) 5  D) 7

20. A function `h(x)` returns `2*x - 3`. What does `h(6)` return?
    A) 6  B) 9  C) 12  D) 15

21. In a short-circuit language, `x != 0 AND (10 / x > 1)` is evaluated with `x = 0`. What happens?
    A) The second condition is skipped; the overall condition is false.
    B) The result is true.
    C) It must divide by zero.
    D) The program loops forever.

22. A sorted array is searched by repeatedly halving the remaining range. Which algorithm is being used?
    A) Linear search  B) Binary search  C) Bubble sort  D) Depth-first search

23. Start with an empty stack; `push(4)`, `push(7)`, `pop()`, `push(2)`, `pop()`. What is on top?
    A) 2  B) 4  C) 7  D) Empty

24. Enqueue 3, then 5, then 8 into an empty queue; dequeue once. What is at the front?
    A) 3  B) 5  C) 8  D) Empty

25. In a singly linked list with no tail pointer, what is the typical time to access the element at position `k` by index?
    A) O(1)  B) O(log n)  C) O(n)  D) O(n²)

26. Two distinct keys produce the same hash-table bucket. This is called:
    A) A collision  B) Inheritance  C) A page fault  D) A deadlock

27. A base-typed reference points to a derived object, and an overridden method is called. With dynamic dispatch, which implementation runs?
    A) Always the base implementation
    B) The derived object's override
    C) Neither; overriding is impossible
    D) The constructor runs again

28. Restricting direct access to an object's fields and exposing controlled methods is:
    A) Encapsulation  B) Recursion  C) Paging  D) Sorting

29. Same method name, different parameter lists (in a language supporting the feature) is:
    A) Overloading  B) Overriding  C) Deadlock  D) Normalization

30. What is the primary purpose of a constructor?
    A) Initialize a newly created object
    B) Sort a database table
    C) Route network packets
    D) End an operating system process

31. Which constraint ensures every row has a unique identifier?
    A) Primary key  B) `ORDER BY`  C) `GROUP BY`  D) View

32. In SQL, which clause filters grouped/aggregated results?
    A) `HAVING`  B) `WHERE`  C) `FROM`  D) `VALUES`

33. In C, what does `scanf("%s", name)` normally read into `name`?
    A) A whitespace-delimited token  B) The entire input stream including spaces  C) One integer only  D) A whole file

34. In C, a block-scope variable declared `static` generally:
    A) Retains its stored value between function calls
    B) Is recreated as a fresh automatic variable on every call
    C) Becomes a network socket
    D) Can only hold text

### Answer key

13. **C — 10.** The loop sums 1 + 2 + 3 + 4.
14. **A — 5, 3.** Integer quotient is 5 and remainder is 3.
15. **A — 2.** The values at indexes 0 and 2 are swapped.
16. **C — 6.** The inner loop runs 1 + 2 + 3 times.
17. **C — 24.** `4 × 3 × 2 × 1`.
18. **D — 9.** The loop tracks the largest array value.
19. **B — 2.** `6` is `110₂`, `3` is `011₂`; AND gives `010₂`.
20. **B — 9.** `2 × 6 - 3 = 9`.
21. **A.** Short-circuit AND stops after the first false operand, avoiding division by zero.
22. **B — Binary search.** It requires sorted data and halves the search interval.
23. **B — 4.** The pops remove 7 and then 2; 4 remains.
24. **B — 5.** A queue is FIFO, so 3 leaves first.
25. **C — O(n).** The list must be traversed node by node.
26. **A — Collision.** Collision-handling strategy is needed when keys map to the same bucket.
27. **B.** Dynamic dispatch selects the override for the actual object's runtime type.
28. **A — Encapsulation.** It protects internal state behind a controlled interface.
29. **A — Overloading.** Overriding changes inherited behavior; overloading changes the parameter signature.
30. **A.** Constructors establish an object's initial state.
31. **A — Primary key.** A primary key uniquely identifies table rows.
32. **A — `HAVING`.** `WHERE` filters rows before grouping; `HAVING` filters groups.
33. **A.** `%s` stops at whitespace; bounded input is important to avoid buffer overflow.
34. **A.** A local static object has persistent storage duration across calls; its block scope remains local.

## Section C — Network, Security, and Cloud (11)

### Questions

35. Which device typically forwards traffic between different IP networks?
    A) Router  B) Layer-2 switch  C) Hub  D) Access point only

36. A switch in a typical Ethernet LAN forwards frames mainly using:
    A) MAC addresses  B) Domain names  C) File extensions  D) Email addresses

37. Which protocol provides reliable, ordered delivery to applications by default?
    A) TCP  B) UDP  C) DNS  D) ARP

38. Which service resolves a domain name to an IP address?
    A) DNS  B) DHCP  C) SMTP only  D) SNMP

39. A `/24` IPv4 subnet is commonly described as having how many usable host addresses under traditional subnetting rules?
    A) 24  B) 128  C) 254  D) 256

40. A firewall is primarily used to:
    A) Allow or block network traffic according to rules
    B) Create database tables
    C) Guarantee that a computer has no malware
    D) Replace all user passwords

41. A web connection using HTTPS protects data in transit primarily with:
    A) TLS  B) DHCP  C) FTP  D) A spreadsheet macro

42. Which cloud model gives the customer virtual machines and networking while the customer typically manages the guest OS?
    A) IaaS  B) PaaS  C) SaaS  D) Bcc

43. A customer uses a provider-hosted CRM application through a browser. This is most commonly:
    A) SaaS  B) IaaS  C) PaaS  D) On-premises hardware

44. Which action best follows least-privilege security?
    A) Grant only the access required for a user's current tasks
    B) Give every employee administrator rights
    C) Share one team password
    D) Leave former employees' accounts active indefinitely

45. Which security property is mainly provided by encrypting sensitive stored files?
    A) Confidentiality  B) Availability only  C) Faster network routing  D) Higher bandwidth

### Answer key

35. **A — Router.** It forwards IP packets across networks. A Layer-3 switch can also route; the question describes the typical distinction.
36. **A — MAC addresses.** A Layer-2 Ethernet switch learns and forwards based on MAC addresses.
37. **A — TCP.** TCP provides ordered, reliable byte-stream delivery.
38. **A — DNS.** DNS performs name resolution.
39. **C — 254.** A `/24` contains 256 addresses; traditionally, network and broadcast addresses are not assignable to ordinary hosts.
40. **A.** A firewall enforces traffic policy; it is not a complete anti-malware guarantee.
41. **A — TLS.** HTTPS uses TLS to protect the communication channel.
42. **A — IaaS.** The provider manages underlying infrastructure; the customer typically manages the guest operating system and workloads.
43. **A — SaaS.** The customer uses a complete hosted application.
44. **A.** Minimum necessary permissions reduce exposure and potential impact.
45. **A — Confidentiality.** Encryption at rest helps prevent unauthorized parties from reading stored data if they lack the key.

## Review your result

- **40–45:** Strong on this mock; check any guessed answers and review timing.
- **32–39:** Good base; revisit missed concepts and repeat the set.
- **Below 32:** Work through the ten topic guides first, then retake without a timer.

This score guide is only for self-study; it does not correspond to an Accenture cutoff or hiring decision.
