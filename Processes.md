## Introduction
Process is a program in execution A single program can create many processes when run multiple times; for example, when we open a .exe or binary file multiple times, multiple instances begin (multiple processes are created).

## Process management
The OS is responsible for starting , stopping and scheduling processes according to the functions they perform and their priorities .A process in memory is divided into several distinct sections, each serving a different purpose. 
- **Text Section**: A Process, sometimes known as the Text Section, also includes the current activity represented by the value of the [Program Counter](https://www.geeksforgeeks.org/what-is-program-counter).
- **Stack** : Contains temporary data such as return address , function parameters and local variables
- **Data Section** : contains global variables
- **Heap** : Contains dynamically allocated data elements
## Process Operations
Process operations in an operating system refer to the various activities the OS performs to manage processes. These operations include process creation, process scheduling, execution and killing the process.
![[Pasted image 20240908191642.png]]

## Process creation
Process creation in an operating system (OS) is the act of generating a new process. This new process is an instance of a program that can execute independently.

### Scheduling

Once a process is ready to run, it enters the “ready queue.” The scheduler’s job is to pick a process from this queue and start its execution.

### Execution

Execution means the CPU starts working on the process. During this time, the process might:

- Move to a waiting queue if it needs to perform an I/O operation.
- Get blocked if a higher-priority process needs the CPU.
### Killing the Process

After the process finishes its tasks, the operating system ends it and removes its [[Process Control Block (PCB)]].

## Context Switching of Process

The process of saving the context of one process and loading the context of another process is known as [[Context Switching]]. In simple terms, it is like loading and unloading the process from the running state to the ready state.
Context Switching Happen:
- When a high-priority process comes to a ready state (i.e. with higher priority than the running process). 
- An Interrupt occurs.
- User and kernel-mode switch (It is not necessary though) 
- Preemptive CPU scheduling is used.

## CPU Bound VS IO Bound Processes
A CPU bound Process spends more in the running state and an I/O-bound process requires more I/O time and less CPU time. An I/O-bound process spends more time in the waiting state.

## Process Scheduling Algorithms
- **First-Come, First-Served (FCFS) :** 
	- The Processes are executed on a first come first serve basis
	- non-preemptive 
- **Shortest Job First (SJF) :**  
	- Selects the Process based on the shortest burst time 
	- The burst time is the time a process takes to complete its execution
	- minimizes the average waiting time of the processes.
- **Round Robin :**
	- Reserves a fixed amount of time in a round for each process 
	-  If a process does not complete its execution within the specified time, it is blocked and added to the end of the queue.
	-  RR ensures fair distribution of CPU time to all processes and avoids starvation.
- **Priority Scheduling :**
	- The highest Priority Process is executed first 
	- Priority can be set based on process type, importance, or resource requirements.
- **Multi level queue :**
	- Divides the ready queue into several different queues 
	- each queues have different priorities
	- Processes are queued based on their priority
	- each queue uses its own scheduling algorithm
	- useful in scenarios where different types of processes have different priorities.