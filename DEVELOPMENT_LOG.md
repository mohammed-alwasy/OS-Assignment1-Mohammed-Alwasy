# Development Log

## Instructions
Document your development process as you work on the assignment. Add entries showing:
- What you worked on
- Problems you encountered
- How you solved them
- Time spent

**Requirements**: Minimum 5 entries showing progression over time.

---

## Example Entry Format:

### Entry 1 - [April 1, 2026, 2:30 PM]
**What I did**: Forked the repository and set up my student ID

**Details**: 
- Created GitHub account with university email
- Forked the starter repository
- Changed student ID on line 92 to my actual ID (441234567)
- Compiled and ran the program successfully

**Challenges**: Had to install JDK first because javac wasn't recognized

**Solution**: Downloaded JDK 17 from Oracle website and set PATH variable

**Time spent**: 30 minutes

---

## Your Development Log:

### Entry 1 - [march 28, 2026, 12:30 pM]
**What I did**: 
Implemented Feature 1

**Details**: 
1-Added a new priority field to the Process class (range 1–5, where 5 is highest).
2-Updated the constructor to initialize the priority value.
3-Generated random priorities when creating processes using Random.nextInt().
4-Added a getter method getPriority().
5-Modified the ready queue output to display each process’s priority when it is added.
**Challenges**: 
1-Initially forgot to update the constructor, which caused errors when creating Process objects.
2-Needed to ensure the priority value stayed within the required range (1–5).
3-The output formatting in VS Code appeared incorrect (colors and layout were not displayed properly).

**Solution**: 
1-Updated all constructor calls to include the priority parameter.
2-Used 1 + random.nextInt(5) to correctly generate values between 1 and 5.
3-Switched to IntelliJ IDEA, which handled ANSI colors and console output formatting correctly.

**Time spent**: 
1 hour and 30 minutes

---

### Entry 2 - [march 29, 2026, 12:30 am]
**What I did**: 
Implemented Feature 2 by counting context switches in the scheduler.

**Details**:
1-Added a static variable contextSwitches in the SchedulerSimulation class.
2-Incremented the counter each time a process starts execution inside the main scheduling loop.
3-Placed the increment statement right before currentThread.start() to accurately reflect CPU switching.
4-Displayed the total number of context switches at the end of the simulation output.

**Challenges**: 
1-Was initially unsure where exactly to increment the counter in the loop.
2-Needed to understand the concept of a context switch and when it actually occurs in the program.
3-Ensuring the counter reflects all process executions, including re-queued processes.

**Solution**:
1-Identified that a context switch occurs whenever a new process begins execution.
2-Placed contextSwitches++ immediately before currentThread.start().
3-Tested the program multiple times to verify the counter increases correctly with each process run.

**Time spent**: 
1 hour 50 minute

---

### Entry 3 - [Date and Time]
**What I did**: 

**Details**: 

**Challenges**: 

**Solution**: 

**Time spent**: 

---

### Entry 4 - [Date and Time]
**What I did**: 

**Details**: 

**Challenges**: 

**Solution**: 

**Time spent**: 

---

### Entry 5 - [Date and Time]
**What I did**: 

**Details**: 

**Challenges**: 

**Solution**: 

**Time spent**: 

---

### Entry 6 - [Optional - Date and Time]
**What I did**: 

**Details**: 

**Challenges**: 

**Solution**: 

**Time spent**: 

---

## Summary

**Total time spent on assignment**: [X hours]

**Most challenging part**: 

**Most interesting learning**: 

**What I would do differently next time**: 
