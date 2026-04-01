# Assignment Questions

## Instructions
Answer all 4 questions with detailed explanations. Each answer should be **3-5 sentences minimum** and demonstrate your understanding of the concepts.

---

## Question 1: Thread vs Process

**Question**: Explain the difference between a **thread** and a **process**. Why did we use threads in this assignment instead of creating separate processes?

**Your Answer:**
A process is an active program in execution that encompasses its own code, current activity, and allocated resources. In contrast, a thread is a smaller unit of execution within that process that shares the same memory space and resources, rather than requiring an isolated memory layout. We used threads for this assignment instead of separate processes because thread creation involves significantly less system overhead. Furthermore, because threads share the same data and heap, they can communicate much more efficiently, making them far more suitable for handling the concurrent tasks required in this simulation  
---

## Question 2: Ready Queue Behavior

**Question**: In Round-Robin scheduling, what happens when a process doesn't finish within its time quantum? Explain using an example from your program output.

**Your Answer:**

In Round-Robin scheduling, when a process does not finish its task within the allocated time quantum, it is forcefully preempted by the system. The process is transitioned from the "Running" state back to the "Ready" state and is moved to the very back of the ready queue. It will wait in this queue while other processes get their turn, and will only resume execution once it cycles back to the front of the line and the scheduler dispatches it again.
Example from my output:
```
▶ P1 executing quantum [4000ms] 
  ⚡ Quantum progress: [███████████████] 100%
  ⏸ P1 completed quantum 4000ms │ Overall progress: [█████████░░░░░░░░░░░] 45%
     Remaining time: 4701ms
  ↻ P1 yields CPU for context switch

  ➕ P1 (Priority: 3) added to ready queue │ Burst time: 8701ms
┌─ Ready Queue ─────────────────────────────────────────────────────────────────
│ [P3 → P4 → P5 → P6 → P7 → P8 → P9 → P10 → P11 → P12 → P13 → P14 → P15 → P16 → P17 → P18 → P19 → P20 → P1]
```

**Explanation of example:**
In this specific snippet, the global time quantum is set to 4000ms. Process P1 requires a total burst time of 8701ms. Because its burst time exceeds the 4000ms quantum, P1 executes until its time limit expires, reaching only 45% overall progress with 4701ms remaining. The system then preempts P1, forcing it to yield the CPU for a context switch. P1 is immediately placed at the very back of the Ready Queue (behind P20), and the CPU will move on to execute P2 and P3. P1 will not run again until all the other processes ahead of it in the queue take their turns.

---

## Question 3: Thread States

**Question**: A thread can be in different states: **New**, **Runnable**, **Running**, **Waiting**, **Terminated**. Walk through these states for one process (P1) from your simulation.

**Your Answer:**

[Write your answer here. For each state, explain when P1 enters that state during the simulation. Use your understanding of the code to trace through the lifecycle.]

1. **New**: P1 is in the New state at the very beginning of the simulation when its thread object is first created and its initial burst time (8701ms) and priority (3) are configured, but before it has been submitted to the scheduler.

2. **Runnable**: P1 enters the Runnable (or Ready) state when it is placed into the ready queue to wait for CPU allocation. In my output, this happens initially when the log shows + P1 ... added to ready queue, and it re-enters this state later after its 4000ms time quantum expires and it is forced to yield the CPU.

3. **Running**: P1 is in the Running state when the scheduler dispatches it and it actively holds the CPU. In the simulation, this is explicitly shown by the line ▶ P1 executing quantum [4000ms], where it makes 45% progress on its task.

4. **Waiting**: P1 would transition to the Waiting (or Blocked) state if it needed to request an I/O operation or wait for a specific external event. While my specific output snippet shows P1 as a CPU-bound task bouncing between Running and Runnable, it would pause in this state if it needed to wait for external data.

5. **Terminated**: P1 will enter the Terminated state once it successfully finishes its entire 8701ms burst time. Because it still has 4701ms remaining after its first quantum, it will need to cycle through the queue and run again before it can finally terminate.

---

## Question 4: Real-World Applications

**Question**: Give **TWO** real-world examples where Round-Robin scheduling with threads would be useful. Explain why this scheduling algorithm works well for those scenarios.

**Your Answer:**

### Example 1: [Interactive Graphical User Interfaces (GUIs)]

**Description**: 
Modern desktop environments and complex applications (like web browsers or media players) rely on multithreading to manage different tasks simultaneously. For instance, one thread might be actively decoding a video file while another thread listens for the user to click the "pause" or "volume" buttons.
**Why Round-Robin works well here**: 
In interactive systems, user-perceived latency is the most critical metric. Round-Robin works exceptionally well because it provides highly predictable response times. By rapidly cycling the CPU through all active threads using a short time quantum, it creates the illusion of true concurrency. This ensures that the thread responsible for handling user input gets regular, frequent access to the CPU, keeping the application from feeling "frozen" or laggy while heavy background processing continues.
### Example 2: [Web Server Handling Client Requests]

**Description**: 
When a web server (like Apache or Nginx) receives multiple simultaneous connections from different users—such as loading a webpage, downloading a file, or querying a database—it often assigns each incoming request to a separate worker thread to be processed.
**Why Round-Robin works well here**: 
Round-Robin scheduling is highly suitable for this scenario because its primary goal is fairness, ensuring no single thread monopolizes the CPU. If one user is downloading a massive file, a Round-Robin scheduler will preempt that thread after its time quantum expires, allowing threads handling smaller, quicker requests to get their turn. This prevents "starvation" and ensures that the web server remains highly responsive to all users rather than getting bogged down by a few heavy tasks.
---

## Summary

**Key concepts I understood through these questions:**
1. the differance between process and threads.
2. how ready queue is working
3. the states of threads
**Concepts I need to study more:**
1. more anderstading about threads and process
2. CPU scheduling algorithms and how waiting time is calculated in detail
