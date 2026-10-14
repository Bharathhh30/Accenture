# Operating Systems

**Assessment priority: Role-dependent/core-CS** — useful fundamentals, but less clearly named in the public general-campus MCQ descriptions reviewed.

| Concept | One-line last-minute reminder |
|---|---|
| OS purpose | An operating system manages hardware resources and provides services/abstractions for applications. |
| Process | A process is a running program with its own execution context and allocated resources. |
| Thread | A thread is an execution path within a process; threads typically share process memory/resources. |
| Process states | Know the ready, running, blocked/waiting, and terminated states and the events that move a process between them. |
| Context switch | The OS saves one task's CPU state and restores another's, enabling multitasking with overhead. |
| Scheduler | The scheduler chooses which ready task receives CPU time. |
| FCFS | First-Come, First-Served runs tasks in arrival order and can cause a convoy effect. |
| SJF / SRTF | Shortest Job First chooses the shortest expected job; its preemptive form is Shortest Remaining Time First. |
| Round Robin | Round Robin gives each ready task a time quantum in rotation. |
| Priority scheduling | Priority scheduling favors higher-priority work and can starve lower-priority tasks without mitigation. |
| Starvation and aging | Starvation is indefinite waiting; aging gradually raises waiting-task priority to reduce it. |
| Race condition | A race occurs when concurrent operation ordering changes the result. |
| Critical section | A critical section accesses shared state and must be synchronized to avoid unsafe concurrent updates. |
| Mutex and semaphore | A mutex provides mutual exclusion; a semaphore maintains a counter for signaling/resource permits. |
| Deadlock | Deadlock is indefinite waiting for resources among processes. |
| Coffman conditions | Mutual exclusion, hold-and-wait, no preemption, and circular wait are the four necessary deadlock conditions. |
| Deadlock handling | Prevention breaks a necessary condition; avoidance checks safe states; detection and recovery handle deadlock after it occurs. |
| Physical vs virtual memory | Virtual memory gives each process an address-space abstraction mapped to physical memory. |
| Paging | Paging divides virtual memory into pages and physical memory into frames. |
| Page fault | A page fault occurs when a referenced virtual page is not currently resident and must be handled by the OS. |
| Page replacement | FIFO, LRU, and Optimal are classic page-replacement algorithms; Optimal is a theoretical benchmark. |
| Internal/external fragmentation | Internal fragmentation wastes space inside allocated blocks; external fragmentation leaves scattered free regions. |
| System call | A system call requests a protected OS service such as file access or process creation. |
| User/kernel mode | Kernel mode permits privileged operations; user mode restricts ordinary application privileges. |
| File system | A file system organizes files/directories and manages metadata, naming, permissions, and storage. |
| Virtualization | A hypervisor allows multiple virtual machines to share physical hardware. |
