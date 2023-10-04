# Formula sheet

For n fork calls, then the number of child processes = $$2^n - 1$$
because it's number of processes - one parent process

------
**Arrival Time**: Time at which the process arrives in the ready queue.

**Completion Time**: Time at which process completes its execution.

**Burst Time**: Time required by a process for CPU execution.

**Turn Around Time**: Time Difference between completion time and arrival time.

**Waiting Time(W.T)**: Time Difference between turn around time and burst time.

Turn Around Time = Completion Time  –  Arrival Time

Waiting Time = Turn Around Time  –  Burst Time

Response time = Time at which the process gets the CPU for the first time - Arrival time

---

Highest Response Ratio Next:

response ratio = (W+S)/S

Here, W is the waiting time of the process so far and S is the Burst time of the process.

---
# Page fault
Effective Access time = (1-P)\*Memory Access Time + P\*(Page Fault Time)

(You dont have to add extra Memory access time after page miss)

---
## Free page list
Every free block has 1 address at the end which point to next free block in the free page list.

---
There is no relation between best,next,first and worst fit allocations. One can exist while the other can for certain situations.

---
# Always check bytes and bits
$$ PageSize = PS$$
$$Page Offset= log$$

---
In page-fault frequency strategy, process can exceed it's lower and upper bounds, but frames get removed and allocated respectively

--- 
# Do multi level paging questions

Check global and local replacement algorithms

---
# fork() and exec() and pids
Threads have nothing to do with IPC

---
