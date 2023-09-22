# Operating Systems

Operating systems connects users to computer hardware.

The purpose of an operating system is to provide an environment in which a user can execute programs conveniently and efficiently.

It manages resources and services, such as memory, processors, devices, and information. 

The operating system correspondingly includes programs to manage these resources, such as a traffic controller, a scheduler, a memory management module, I/O programs, and a file system.

![](https://media.geeksforgeeks.org/wp-content/uploads/20230512132248/Introduction-of-OS.webp)

## Batch Operating System

In this Operating System an **operator** sorts the jobs into various batches based on similar jobs and same requirements.

### Advantages

- Processors in the batch systems know how long the job would be when it is in the queue
- Multiple users can share the batch systems
- very less Idle time
- easy to manage large work repeatedly
### Disadvantages

- The operators should be well known with the batch systems
- Hard to debug
- Costly
- Jobs can wait unlimitedly (hence they fail)
![](https://media.geeksforgeeks.org/wp-content/uploads/20230511130815/types1-(1).webp)

## Multi-Programming System

More than one program can be stored in the main memory and any one of them can be kept in execution. Basically used for better uses of resources.

### Advantages

- Increased Throughput
- Decreased Response time

### Disadvantages

- No Facilty for User Interaction

![](https://media.geeksforgeeks.org/wp-content/uploads/20230516182714/Types-of-OS-03.webp)

## Multi-Processing System

More than one CPUs are used for the execution of resources

### Advantages
- Increased Throughput
- No single point of failure for processors 

### Disadvantages

- Complex to understand

![](https://media.geeksforgeeks.org/wp-content/uploads/20230516183450/Types-of-OS-02.webp)

## Multi-Tasking Operating System

Simply Multi Programming OS but with Round Robin Scheduling.

It can run multiple programs simultaneously.

Types: 

- Preemptive 
- Cooperative

| Preemptive |  Cooperative |
|-|-|
| Decides for how long a task should run then context switches | Never initiates a context switch from a running process to another process.
| Interrupts applications and gives control to other processes outside of Application's control | Process scheduler never interrupts a process unexpectedly 
| A malicious program initiates an infinite loop, it only hurts itself without affecting other programs or threads. | A malicious program can bring the entire system to a halt by busy waiting or running an infinite loop and not giving up control.
| Applications share CPU regardless of choice | All programs must cooperate. One program can hog up the entire CPU
| Old Windows Versions, UNIX | Old Mac Versions

### Advantages
- Multiple Programs can be executed simultaneously in Multi-Tasking Operating System.
- It comes with proper memory management.

### Disadvantages
- The system gets heated in case of heavy programs multiple times.

![](https://media.geeksforgeeks.org/wp-content/uploads/20230516183620/Types-of-OS-01.webp)

## Time-Sharing Operating System
Each task is given some time to execute so that all the tasks work smoothly.

Each user gets the time of the CPU as they use a single system. 

Similar to Multi Tasking but it's users here instead of tasks with time sharing concepts.

Integrating Multitasking and Multiprogramming.

The task can be from a single user or different users also. The time that each task gets to execute is called **quantum**. After this time interval is over OS switches over to the next task. 

### Advantages
- Every task gets equal opportunity
- Fewer chances of duplication of software
- Reduced CPU Idle time
- Resource Sharing
- Improved Productivity
- Improved User Experience

### Disadvantages
- Not reliable
- Securty Risks
- Data Communication problem
- High Overhead due to (multiple users,context switch etc.,)

![](https://media.geeksforgeeks.org/wp-content/uploads/20230512125908/Capture2210.png)

## Distributed Operating System
Loosely Coupled systems on a netork sharing computational resources, memory, CPUs etc.,

This also enables remote access to different systems on the network.

### Advantages
- No sigle point of failure when it comes to systems
- Shared resources give fast and durable computations
- Load on host computer reduces
- Scalable and can easily add more systems
- lesser delay in data processing
### Disadvantages
- Failure of the main network will stop the entire communication
- Expensive and Complex to understand

![](https://media.geeksforgeeks.org/wp-content/uploads/20230516183602/Types-of-OS-04.webp)

## Network Operating System
These systems run on a server and provide the capability to manage data, users, groups, security, applications, and other networking functions.

These types of operating systems allow shared access to files, printers, security, applications, and other networking functions over a small private network. 

One more important aspect of Network Operating Systems is that all the users are well aware of the underlying configuration, of all other users within the network, their individual connections, etc. 

They are tightly coupled systems.

### Advantages

- Stable Centralized Systems
- Security
- New Tech easily integrated
- Server access is possible remotely

### Disadvantages
- Costly Servers
- User has to depend on the central location most of the times
- Maintainance and updates required

![](https://media.geeksforgeeks.org/wp-content/uploads/20230511145829/types-7-(1).webp)

## Real-Time Operating System

Real-time systems are used when there are time requirements that are very strict like missile systems, air traffic control systems, robots, etc.

Very small response times are desired.
Types:

- Hard RTOS (Air traffic control, medical system)
- Soft RTOS (multimedia transsmission, video games)

### Advantages
- Maximum Utilization of resources
- Time taken to shift processes is less
- More focus on running applications and less focus on applications in queue
- Best memory management
### Disadvantages
- Limited Tasks
- Expensice resources
- Complex algorithms
- It is not good to set thread priority as these systems are very less prone to switching tasks.
- It needs specific device drivers and interrupts signal to respond earliest to interrupts.

![](https://media.geeksforgeeks.org/wp-content/uploads/20230511145635/Types8.webp)


## Functions of Operating Systems

- Memory Management
- Processor Management
- Device Management
- File Management
- Network Management
- UI
- Booting the Computer
- Security
- Control over System Performance
- Job Accounting
- Error Detecting aids
- Co-ordination between Other Software and Users
- Performs basic Computer Tasks

### <ins>Microkernel</ins>

A microkernel is a type of operating system kernel that is designed to provide only the most basic services required for an operating system to function such as:
- Memory management
- Process scheduling
- Inter process Communication

Other services, such as device drivers and file systems, are implemented as user-level processes that communicate with the microkernel via message passing. 

This design allows the operating system to be more modular and flexible than traditional monolithic kernels, which implement all operating system services in kernel space.

Being a kernel it manages all system resources. But in a microkernel, the user services and kernel services are implemented in different address spaces.


<ins>Advantages:</ins>
- more stability, crashes in user processes dont affect system
- more secure, due to reduced attack surface
- more modular and flexible
- simple development, deployment and testing

<ins>Disadvantages:</ins>
- slow message passing
- modular design increases complexity
- Higher memory consumed compared to monolithic
- tradeoffs beteen advantages and {complexity and performance}

Monolithic -> same address space for user and kernel

Micro -> diff address space

Nano -> Microlithic but clock resolution in nanoseconds, lesser user friendly than Microlithic but very efficient

Hybrid -> Microlithic + Monolithic

Exo -> application level handling of hardware resources

|Basics |Micro Kernel|Monolithic Kernel|
|-|-|-|
Size|Smaller in|Larger as OS and user both lie in the same address space.
Execution|Slower |Faster 
Extendible|Easily extendible|Complex to extend
Security|If the service crashes then there is no effect on working on the microkernel.|If the process/service crashes, the whole system crashes as both user and OS were in the same address space.
Code|More code is required to write a microkernel.|Less code is required to write a monolithic kernel. 
Examples|L4Linux, macOS|Windows, Linux BSD
Security|More secure because only essential services run in kernel mode|Susceptible to security vulnerabilities due to the amount of code running in kernel mode
Platform independence|More portable because most drivers and services run in user space|Less portable due to direct hardware access
Communication|Message passing between user-space servers|Direct function calls within kernel
Performance|Lower due to message passing and more overhead|High due to direct function calls and less overhead


### <ins>Kernel</ins>
Kernel is the core part of an operating system that manages system resources. 

It also acts as a bridge between the application and hardware of the computer. 

It is one of the first programs loaded on start-up (after the Bootloader). 

### <ins>[System Calls](https://www.geeksforgeeks.org/introduction-of-system-call/)</ins>
In computing, system call is a programmatic way in which a computer program requests a service from the kernel of the OS. 

This is a way for programs to interact with the OS.

These are usually invoked by software interrupts, but even users can do it with privileged instructions.

All programs needing resources must use system calls.

A system call is initiated by the program executing a specific instruction, which triggers a switch to kernel mode, allowing the program to request a service from the OS.

- Process creation and management
- Main memory management
- File access and management
- Device Handling
- Information maintainance
- Communication
- Protection


### Working of System calls
Users can use special predefined special instructions which lets them use special previledges like accessing files on the system.

When OS sees the system call, it realises that the executing program needs help so it temporarily stops the execution of the program and gives control to a special part of itself called the kernel.

(user mode -> kernal mode(highly privileged))

Process change requires kernel mode (**IMPORTANT**)

Kernel then solves the needs of the program and then it returns the control back to the process for further execution.

- open()
- read() : 3 arguments(path, buffer to save data in, how much data to read)
- wait()
- write() : 3 arguments(path, buffer to take data from, how much data to write from buffer to file)
- fork() : makes copies of it self(child processes), child finishes only then parent resumes
- exit() OS regains control over resources used by the program as the program exits execution.
- [pipe()](https://www.geeksforgeeks.org/pipe-system-call/?ref=ml_lbp)

[Codes in C](https://www.geeksforgeeks.org/input-output-system-calls-c-create-open-close-read-write/)

|Feature|Multiprogramming|Multitasking|Multithreading|Multiprocessing|
|-|-|-|-|-|
|Definition|Running multiple programs on a single CPU|Running multiple tasks (applications) on a single CPU|Running multiple threads within a single task (application)|Running multiple processes on multiple CPUs (or cores)
Resource Sharing|Resources shared among programs|Resources shared among tasks|Resources shared among threads|Each process has its own set of resources
Scheduling|Uses round-robin or priority-based scheduling to allocate CPU time to programs|Uses priority-based or time-slicing scheduling to allocate CPU time to tasks|Uses priority-based or time-slicing scheduling to allocate CPU time to threads|Each process can have its own scheduling algorithm
Memory Management|Each program has its own memory space|Each task has its own memory space|Threads share memory space within a task|Each process has its own memory space
Context Switching|Requires a context switch to switch between programs|Requires a context switch to switch between tasks|Requires a context switch to switch between threads|Requires a context switch to switch between processes
Inter-Process Communication (IPC)|Uses message passing or shared memory for IPC|Uses message passing or shared memory for IPC|Uses thread synchronization mechanisms (e.g., locks, semaphores) for IPC|Uses inter-process communication mechanisms (e.g., pipes, sockets) for IPC

!!! I dont know which one actually does round robin here

### Types of Memory

Primary Memory:
- RAM
- ROM

Secondary Memory:
- Hardrive
- SSD
- CD

![](https://media.geeksforgeeks.org/wp-content/uploads/memory.png)

## RAM

The programs and data that the CPU requires during the execution of a program are stored in this memory.

Volatile Memory, so data will be lost once the power is turned off.

- Static RAM
- Dynamic RAM

![](https://media.geeksforgeeks.org/wp-content/uploads/difference-1.png)

### Advantages of RAM

- Speed
- Flexibility
- Capacity: Upgradable
- Power Management

### Disadvantages of RAM

- Volatile
- Limited Capacity
- Cost

### Read-Only Memory
- Non-volatile
- Crucial information essential to operate the system, like program to boot the computer
- Always retains this info
- Used in embedded systems or where programming doesnt need change
- Used in calc and peripheral devices

### Types of ROM
- PROM
    - once programmed cant be erased
- EPROM (Erasible)
    - can be reprogrammed
- EEPROM (Electrically Erasible)
    - can be reprogrammed by applying electric field, without UVrays
- MROM (Mask)
    - Masked off at the time of production

### Advantages of ROM
- Non-volatile
- Reliable
- Power Management

### Disadvantages of ROM
- Limited capacity
- Limited flexibility
- Cost

![](https://media.geeksforgeeks.org/wp-content/uploads/ram.png)

Cost:
- RAM is more costlier than ROM.
- ROM is cheaper than RAM.

Chip Size: 
- A RAM chip can store only a few gigabytes (GB) of data.
- A ROM chip can store multiple megabytes (MB) of data.
⠀

⠀

32-bit OS can access 2^32 addresses ~ 4 GB RAM

64-bit OS can access 2^64 addresses ~ millions of times more than 4 GB RAM

When a system boots, BIOS first performs POST(Power on self test) to check if everything works fine

## Processes and threads

|S. No.|Parameters|User Level Thread|Kernel Level Thread|
|-|-|-|-|
|1.|Implemented by|User threads are implemented by users.|Kernel threads are implemented by Operating System (OS).
2.|Recognize|The operating System doesn’t recognize user-level threads.|Kernel threads are recognized by Operating System.
3.|Implementation|Implementation of User threads is easy.|Implementation of Kernel-Level thread is complicated.
4.|Context switch time|Context switch time is less.|Context switch time is more.
5.|Hardware support|Context switch requires no hardware support.|Hardware support is needed.
6.|Blocking operation|If one user-level thread performs a blocking operation then the entire process will be blocked.|If one kernel thread performs a blocking operation then another thread can continue execution.
7.|Multithreading|Multithread applications cannot take advantage of multiprocessing.|Kernels can be multithreaded.
8.|Creation and Management|User-level threads can be created and managed more quickly. |Kernel-level level threads take more time to create and manage. 
9.|Operating System|Any operating system can support user-level threads.|Kernel-level threads are operating system-specific.
10.|Thread Management|The thread library contains the code for thread creation, message passing, thread scheduling, data transfer, and thread destroying|The application code does not contain thread management code. It is merely an API to the kernel mode. The Windows operating system makes use of this feature.
11.|Example|Example: Java thread, POSIX threads.|Example: Window Solaris.
12.|Advantages|User Level Threads are simple and quick to create. Can run on any operating system. They perform better than kernel threads since they don’t need to make system calls to create threads. In user-level threads, switching between threads does not need kernel mode privileges. | Scheduling multiple threads that belong to the same process on different processors is possible in kernel-level threads. Multithreading can be there for kernel routines. When a thread at the kernel level is halted, the kernel can schedule another thread for the same process.
13.|Disadvantages| Multithreaded applications on user-level threads cannot benefit from multiprocessing. If a single user-level thread performs a blocking operation, the entire process is halted. | Transferring control within a process from one thread to another necessitates a mode switch to kernel mode. Kernel-level threads take more time to create and manage than user-level threads.
14.|Memory management|In user-level threads, each thread has its own stack, but they share the same address space.|In kernel-level threads have their own stacks and their own separate address spaces, so they are better isolated from each other.
15.|Fault tolerance|User-level threads are less fault-tolerant than kernel-level threads. If a user-level thread crashes, it can bring down the entire process.|Kernel-level threads can be managed independently, so if one thread crashes, it doesn’t necessarily affect the others.
16.|Resource utilization|User-level threads don’t take full advantage of the system resources, As they don’t have direct access to the system-level features like I/O operations|It can access to the system-level features like I/O operations.So it can take full Advantages of System Resources.
17.|Portability|User-level threads are  more portable than kernel-level threads.|Kernel-level threads are less portable than User-level threads.\

Simply put, kernel threads are independent of each other, slow, more time to switch context, once blocked wont terminate other threads, complex and arent made by users, whereas user level threads are exactly the opposite.

Threads can share the Code segments(Because they are threads afterall). They have only separate Registers and stack.

OS does not maintain virtual memory space for each individual threads.

|S.NO|Process|Thread|
|-|-|-|
1.|Process means any program is in execution.|Thread means a segment of a process.
2.|The process takes more time to terminate.|The thread takes less time to terminate.
3.|It takes more time for creation.|It takes less time for creation.
4.|It also takes more time for context switching.|It takes less time for context switching.
5.|The process is less efficient in terms of communication.|Thread is more efficient in terms of communication.
6.|Multiprogramming holds the concepts of multi-process.|We don’t need multi programs in action for multiple threads because a single process consists of multiple threads.
7.|The process is isolated.|Threads share memory.
8.|The process is called the heavyweight process.|A Thread is lightweight as each thread in a process shares code, data, and resources.
9.|Process switching uses an interface in an operating system.|Thread switching does not require calling an operating system and causes an interrupt to the kernel.
10.|If one process is blocked then it will not affect the execution of other processes |If a user-level thread is blocked, then all other user-level threads are blocked. 
11.|The process has its own Process Control Block, Stack, and Address Space.|Thread has Parents’ PCB, its own Thread Control Block, and Stack and common Address space.
12.|Changes to the parent process do not affect child processes.|Since all threads of the same process share address space and other resources so any changes to the main thread may affect the behavior of the other threads of the process.
13.|A system call is involved in it.|No system call is involved, it is created using APIs.
14.|The process does not share data with each other.|Threads share data with each other.

### Components of Threads
These are the basic components of the Operating System.

- Stack Space
- Register Set
- Program Counter

Multitasking Programming has Two Types: 

- Process-based Multitasking
- Thread-based Multitasking

|Process-Based Multitasking|Thread-Based Multitasking|
|-|-|
In process-based multitasking, two or more processes and programs can be run concurrently.|In thread-based multitasking, two or more threads can be run concurrently.
In process-based multitasking, a process or a program is the smallest unit.|In thread-based multitasking, a thread is the smallest unit.
The program is a bigger unit.|Thread is a smaller unit.
Process-based multitasking requires more overhead.|Thread-based multitasking requires less overhead.
The process requires its own address space.|Threads share the same address space.
The process to Process communication is expensive.|Thread to Thread communication is not expensive.
Here, it is unable to gain access over the idle time of the CPU.|It allows taking gain access over idle time taken by the CPU.
It is a comparatively heavyweight.|It is comparatively lightweight.
It has a faster data rate for multi-tasking because two or more processes/programs can be run simultaneously.|It has a comparatively slower data rate multi-tasking.
Example: We can listen to music and browse the internet at the same time. The processes in this example are the music player and browser. |Example: Using a browser we can navigate through the webpage and at the same time download a file. In this example, navigation is one thread, and downloading is another thread. Also in a word-processing application like MS Word, we can type text in one thread, and spell checker checks for mistakes in another thread. 

Playing with threads

[fork()](https://www.geeksforgeeks.org/fork-system-call/)
Fork in a loop will always make 2^n-1 children, dont forget the first process is the parent :)

[exec()](https://www.geeksforgeeks.org/difference-fork-exec/)




















# TOPICS TO BE EXPLORED


interrupt service routine
INTERRUPTS
SPOOLING
SPOOLED DEVICE
Rest of processes and threads then cpu scheduling

# GATE TIPS

always read if it's True or False statements that they are asking for

# Formula sheet
do it