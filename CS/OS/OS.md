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

A microkernel is a type of operating system kernel that is designed to provide only the most basic services required for an operating system to function, such as memory management and process scheduling. 

Other services, such as device drivers and file systems, are implemented as user-level processes that communicate with the microkernel via message passing. 

This design allows the operating system to be more modular and flexible than traditional monolithic kernels, which implement all operating system services in kernel space.

### <ins>Kernel</ins>
Kernel is the core part of an operating system that manages system resources. 

It also acts as a bridge between the application and hardware of the computer. 

It is one of the first programs loaded on start-up (after the Bootloader). 

### <ins>[System Calls](https://www.geeksforgeeks.org/introduction-of-system-call/)</ins>
In computing, system call is a programmatic way in which a computer program requests a service from the kernel of the OS. 

This is a way for programs to interact with the OS.

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

Kernel then solves the needs of the program and then it returns the control back to the process for further execution.

- open()
- read() : 3 arguments(path, buffer to save data in, how much data to read)
- wait()
- write() : 3 arguments(path, buffer to take data from, how much data to write from buffer to file)
- fork() : makes copies of it self(child processes), child finishes only then parent resumes
- exit() OS regains control over resources used by the program as the program exits execution.