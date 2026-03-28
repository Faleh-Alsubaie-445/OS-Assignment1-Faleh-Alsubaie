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

[Write your answer here. For each state, explain when P1 enters that state during the simulation. Use your understanding of the code to trace through the lifecycle.]

1. **New**: [When is P1 in New state?]

2. **Runnable**: [When does P1 become Runnable?]

3. **Running**: [When is P1 Running?]

4. **Waiting**: [When/why would P1 be Waiting?]

5. **Terminated**: [When is P1 Terminated?]

---

## Question 4: Real-World Applications

**Question**: Give **TWO** real-world examples where Round-Robin scheduling with threads would be useful. Explain why this scheduling algorithm works well for those scenarios.

**Your Answer:**

### Example 1: [Name of application/scenario]

**Description**: 
[Describe the real-world scenario or application]

**Why Round-Robin works well here**: 
[Explain why Round-Robin scheduling is suitable. Consider fairness, responsiveness, predictability, etc.]

### Example 2: [Name of application/scenario]

**Description**: 
[Describe the real-world scenario or application]

**Why Round-Robin works well here**: 
[Explain why Round-Robin scheduling is suitable. Consider fairness, responsiveness, predictability, etc.]

---

## Summary

**Key concepts I understood through these questions:**
1. 
2. 
3. 

**Concepts I need to study more:**
1. 
2. 
