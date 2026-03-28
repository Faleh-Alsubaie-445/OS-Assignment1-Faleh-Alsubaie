# Assignment Questions

## Instructions
Answer all 4 questions with detailed explanations. Each answer should be **3-5 sentences minimum** and demonstrate your understanding of the concepts.

---

## Question 1: Thread vs Process

**Question**: Explain the difference between a **thread** and a **process**. Why did we use threads in this assignment instead of creating separate processes?

**Your Answer:**

[A process is an independent program with its own memory and system resources, while a thread is a smaller unit of execution within a process that shares the same memory and resources. One key difference is memory sharing: processes have separate memory spaces, while threads share memory, as seen in SchedulerSimulation where threads access shared structures like processQueue and processMap. Another difference is creation overhead: processes are more expensive to create, while threads are lightweight, which is why we repeatedly create them using new Thread(process). Additionally, communication between threads is faster since they share data directly, unlike processes which require slower IPC mechanisms. Therefore, threads were used in this assignment because they are more efficient, faster, and better suited for simulating a CPU scheduler.]

---

## Question 2: Ready Queue Behavior

**Question**: In Round-Robin scheduling, what happens when a process doesn't finish within its time quantum? Explain using an example from your program output.

**Your Answer:**

[In Round-Robin scheduling, if a process does not finish within its time quantum, it is paused and moved to the end of the ready queue. This allows other processes to run before it gets another turn. For example, in my program output, process P2 executed for one quantum, but it still had remaining time, so it yielded the CPU and was added back to the ready queue. This means P2 will only run again after the other processes in the queue have executed. This behavior is important because it ensures fairness and prevents any single process from using the CPU for too long.]

Example from my output:
```
[P2 executing quantum [3000ms]
 P2 completed quantum 3000ms
Remaining time: 2000ms
 P2 yields CPU for context switch
 P2 (Priority: 3) added to ready queue]
```

**Explanation of example:**
[The output shows that P2 did not finish its execution within the given time quantum, so it stopped and returned to the ready queue. It will wait for its next turn and run again later, which demonstrates how Round-Robin scheduling shares CPU time fairly between processes.]

---

## Question 3: Thread States

**Question**: A thread can be in different states: **New**, **Runnable**, **Running**, **Waiting**, **Terminated**. Walk through these states for one process (P1) from your simulation.

**Your Answer:**

1. New: P1 is in the New state when its thread is first created using the Thread constructor, but before the start() method is called.

2. Runnable: P1 becomes Runnable when the start() method is called, which makes the thread ready to run and waiting for CPU scheduling.

3. Running: P1 enters the Running state when the CPU starts executing its run() method, where it performs its assigned time quantum.

4. Waiting: P1 goes into the Waiting state when Thread.sleep() is called inside the run() method to simulate execution time, causing it to pause temporarily.

5. Terminated: P1 reaches the Terminated state when its remaining time becomes zero, meaning it has completed execution and will not run again.


---

## Question 4: Real-World Applications

**Question**: Give **TWO** real-world examples where Round-Robin scheduling with threads would be useful. Explain why this scheduling algorithm works well for those scenarios.

**Your Answer:**

### Example 1: [Game Engine]

**Description**: 
[In a game engine, multiple threads handle different tasks such as player movement, physics calculations, and AI behavior. These tasks need to run continuously and smoothly to maintain gameplay.]

**Why Round-Robin works well here**: 
[Round-Robin scheduling ensures fairness by giving each thread a fixed time quantum, so no single task can dominate the CPU. This improves responsiveness, as all game components are updated frequently, resulting in smooth and predictable performance similar to the process scheduling in the assignment.]

### Example 2: [Web Server]

**Description**: 
[A web server handles multiple client requests at the same time, where each request can be managed by a separate thread. These requests may take different amounts of time to process.]

**Why Round-Robin works well here**: 
[Round-Robin allows each request to get a fair share of CPU time, preventing any single request from blocking others. This improves responsiveness and ensures that all users are served efficiently, just like how processes in the assignment are scheduled fairly using a ready queue.]

---

## Summary

**Key concepts I understood through these questions:**
1. Thread vs Process
2. Real-World Applications

**Concepts I need to study more:**
1. Thread States
