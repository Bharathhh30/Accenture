# Data Structures and Algorithms Basics

## Concepts to learn

- **Array:** Contiguous indexed sequence with fast indexed access; inserting into the middle can require shifting elements.
- **Linked list:** Nodes link to neighboring nodes; insertion can be efficient when the node position is known, but indexed access requires traversal.
- **Stack:** Last-in, first-out (LIFO); common operations are push and pop.
- **Queue:** First-in, first-out (FIFO); common operations are enqueue and dequeue.
- **Hash table:** Maps keys to values using a hash function; average lookup is often near O(1), while collisions and worst cases matter.
- **Tree:** Hierarchical nodes; a binary tree has at most two children per node. A binary search tree has an ordering rule when implemented as one.
- **Graph:** Vertices connected by edges; can model routes, dependencies, and relationships. BFS uses a queue; DFS uses a stack or recursion.
- **Searching:** Linear search checks items in sequence, O(n). Binary search is O(log n) on sorted data with efficient random access.
- **Sorting:** Comparison sorts order values; know the basic purpose and typical costs, but exact complexity can depend on algorithm/input.
- **Big-O:** Describes growth rate while ignoring constants and lower-order terms; it is not a precise runtime in seconds.

## Original practice MCQs

### Questions

1. Which structure is LIFO?
   A) Queue  B) Stack  C) Graph  D) Hash table

2. Which structure is FIFO?
   A) Stack  B) Queue  C) Tree  D) Recursion

3. What is the typical time complexity of reading an array element by known index?
   A) O(1)  B) O(log n)  C) O(n)  D) O(n²)

4. Binary search requires which essential input property?
   A) The data is sorted  B) The data is encrypted  C) The data is a graph  D) The array is empty

5. Which traversal is commonly implemented using a queue?
   A) Breadth-first search  B) Depth-first search only  C) Binary search  D) Insertion sort

6. A hash table maps:
   A) Keys to values  B) Slides to transitions  C) Processes to pixels only  D) Rows to IP packets

7. Which structure naturally represents parent-child hierarchy?
   A) Tree  B) Queue  C) Stack only  D) Flat scalar

8. A simple loop nested inside another loop, each running `n` times, generally has what time complexity?
   A) O(1)  B) O(log n)  C) O(n)  D) O(n²)

### Answer key and explanations

1. **B — Stack.** The most recently pushed item is popped first.
2. **B — Queue.** The earliest enqueued item is removed first.
3. **A — O(1).** Array indexing computes the location directly in the standard model.
4. **A.** Binary search discards half the remaining sorted search range each step.
5. **A — BFS.** A queue processes nodes level by level.
6. **A.** A hash table uses keys to find associated values.
7. **A — Tree.** Trees represent hierarchical relationships.
8. **D — O(n²).** Approximately `n × n` iterations occur.
