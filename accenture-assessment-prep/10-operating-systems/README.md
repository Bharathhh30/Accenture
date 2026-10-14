# Operating Systems

## Concepts to learn

- **Operating system:** Manages hardware resources and provides services and abstractions for applications.
- **Process and thread:** A process is a running program with its own resource/address-space context; threads are execution paths within a process and typically share process resources.
- **Scheduling:** The OS chooses which ready task runs. FCFS, shortest-job-first, priority, and round-robin are common teaching algorithms.
- **Context switch:** Saves one execution context and restores another; it enables multitasking but has overhead.
- **Memory management:** Virtual memory gives processes an address-space abstraction; paging maps virtual pages to physical frames. A page fault occurs when a needed page is not currently resident in memory.
- **Deadlock:** A set of tasks waits indefinitely for resources. The classic necessary conditions are mutual exclusion, hold-and-wait, no preemption, and circular wait.
- **File system:** Organizes files/directories and manages metadata, naming, permissions, and storage allocation.
- **Synchronization:** Locks, semaphores, and related mechanisms coordinate concurrent access to shared data and help prevent race conditions.
- **Kernel and user mode:** Kernel mode has privileged access to hardware/resources; user mode restricts application privileges.
- **Virtual memory vs physical memory:** Virtual addresses are translated to physical locations; disk backing may extend the apparent address space but is much slower than RAM.

## Original practice MCQs

### Questions

1. A running instance of a program is generally called a:
   A) Process  B) Spreadsheet  C) Port  D) Query

2. Threads within the same process generally:
   A) Share the process's address space and resources
   B) Always run on separate computers
   C) Have unrelated program code
   D) Cannot communicate

3. Which scheduling approach gives each ready task a fixed time slice in rotation?
   A) Round-robin  B) DNS  C) Paging  D) Normalization

4. What is a context switch?
   A) Saving one task's execution state and loading another's
   B) Renaming a file
   C) Converting a table to a chart
   D) Changing an IP address

5. What is a page fault?
   A) A requested virtual-memory page is not currently resident and must be handled
   B) A typo in a web page
   C) A failed database join
   D) A network cable fault only

6. Which is one of the classic necessary conditions for deadlock?
   A) Circular wait  B) Unlimited resources  C) No shared state  D) Sorted input

7. What is a race condition?
   A) Program behavior depends on timing/interleaving of concurrent operations
   B) A CPU benchmark
   C) A network protocol
   D) A type of backup

8. Which mode normally has greater privileges to execute protected operations?
   A) Kernel mode  B) User mode  C) Guest browser tab  D) Read-only spreadsheet mode

### Answer key and explanations

1. **A — Process.** A process is a program in execution with associated resources.
2. **A.** Threads in the same process normally share its address space, though each has its own execution state/stack.
3. **A — Round-robin.** Each ready task gets a time quantum in rotation.
4. **A.** The OS changes the CPU from one execution context to another.
5. **A.** The OS must locate/load or otherwise handle the missing page; it is not necessarily an error.
6. **A — Circular wait.** Each task in a cycle waits for a resource held by the next.
7. **A.** Different interleavings can produce different results unless access is coordinated.
8. **A — Kernel mode.** It allows privileged operations unavailable to ordinary user-mode code.
