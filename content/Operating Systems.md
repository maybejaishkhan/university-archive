Operating Systems - Finals Notes
# Operating Systems
A program that connects the user of the computer with its hardware.

You can divide a computer system into 4 parts
Users <-> Applications <-> Operating System <-> Hardware
## User Interface
An OS requires a User Interface for users to interact with. There are two kinds of OS UIs
- Graphical User Interface -> Interactions using mouse(drag-and-drop).
- Command Line Interface -> Interactions using commands(keyboard).

## OS Programs
Operating Systems have two modes of operations which are controlled by the *Mode Bit Flag*. This protects the OS by not allowing programs to manipulate each other. 

**User Mode** (1) -> It has less privileges. Applications operate in user mode.
**Kernel Mode** (0) -> The core of an OS. It has all the privileges. System Programs operate in kernel mode.

## Jobs/Responsibilities of OS
An Operating System has many different jobs and responsibilities.

1. **Resource Management** -> Effectively managing resources between multiple processes.
	- *Resource Allocation -*> Assigning the available resources to processes in the operating system. This can be done automatically or manually.
	- *Scheduling* -> Deciding the order/time that resources are allocated between multiple processes. There are scheduling algorithms like FCFS, SJF, Round-Robin etc.
2. **Process Management** -> Managing (creating/deleting) processes.
	- A *program* is a set of instructions that is not under execution. (Passive Entity)
	- A *process* is a program that is running/under execution. (Active Entity)
	- A *resource* can be anything between CPU time, Input/Output devices, Disk Space, Memory, Network Bandwidth. 
3. **File Management** -> Having a logical and structured view of all the files and directories.
4. **Memory Management** -> Handling the transferring of instructions to and fro the memory.
5. **Network Management** -> Handling network requests and facilitating in connecting to a network.
6. **Communication** -> Facilitates communication between multiple running programs.
7. **Protection/Security** -> Controlling the access of processes(protection) and Defending from malware attacks (security).
8. **User Interface** -> Having an interface to interact with.
9. **Program Execution** -> Responsible for execution for all programs.
10. **I/O Operations** -> Communicating and helping devices for smooth experience.
11. **Error Detection** -> Helping in detecting and correcting errors constantly.
12. **Logging/Accounting** -> Keeping a track record of resource usage.
13. **Virtualization** -> Allows operating systems to run applications that are not native to its platform.
	- This is done using a **VM** (Virtual Machine) via **Emulation**.

## Operating Systems Structure
An operating system can be architectured in one of these many ways
### Monolithic Approach
A monolithic kernel is a single, large program that includes all OS services and functions, such as device management, memory management, and process management.
**Example ->** MS-DOS, Windows 95. 

### Layered Approach
A design methodology that organizes an Operating System (OS) into a hierarchical structure of layers, each layer building upon the services and functions of lower layers.
**Examples ->** Mac OS X, Windows, Android

- **Layer 0**: Hardware
- **Layer 1**: Basic Input/Output Services
- **Layer 2**: Device Management
- **Layer 3**: Kernel Services
- **Layer 4**: System Services
- **Layer 5**: Application Services
- **Layer N**: User Interface

### Microkernels 
A small, core kernel that provides basic services and manages hardware resources, while moving most services to user-space programs.
**Example ->** Mach, QNX, Symbian, L4.
### Modules
A design method that divides an operating system into separate, independent modules, each with a specific function.
**Examples ->** Linux, Solaris, Mac OS X.
### Hybrid
A combination of different architectural approaches to achieve a balance between performance, security, and usability
**Examples ->** Windows NT, Mac OS X, Android.
# Computer System Organization

Devices connect though the **system bus** (the central wire/highway) which provides access to memory. Every device has a *device controller* which has a *local buffer*.

1. **System Bus** -> A central wire (highway) that is used by different parts of the system to communicate/share data.
2. **Device Controller** -> Handles the incoming/outgoing signals between CPU and I/O.
3. **Local Buffer** -> Small memory on the device controller for temporarily storing data.
4. **Device Driver** -> A program that connects to the *device driver* on the device.
5. **Microprocessor** -> The physical chip which runs the computer and has many components.
6. **Core** -> A physical unit on the microprocessor that handles instructions independently.
7. **Thread** -> A logical software unit that runs on a core.
8. **Instruction Register** -> It holds the address of the instruction currently being executed.
9. **Program Counter** -> Also known as Instruction Pointer, hold the address of the instruction that is to be executed next.
## Types of Computing
**Multiprogramming** -> Running multiple programs at a time by time sharing. 
**Multitasking** -> Running multiple programs at a time by using the same resource. 
**Multithreading** -> Running multiple programs simultaneously by using multiple threads.
## Storage and Memory
 A computer stores data in the form of 0s and 1s using **latches** which each represent a single bit. 8 bits can be used together to create a byte. 
 
Stick 1024 of Bytes -> KiloByte -> MegaByte -> GigaByte -> TeraByte -> PetaByte.

**Storage** --> usually refers to data that is stored permanently (*Non-Volatile*).
**Memory** --> usually refers to data that is stored temporarily (*Volatile*).

A computer has multiple types of storage/memory which creates a *Hierarchy*.
### Storage Hierarchy 
This heirarchy is based on the amount of storage vs speed and also the cost. **Caching** is the process of copying information into a faster storage system.

| Type                                                   | What it is                                                                           | Speed          | Average Size                      |
| ------------------------------------------------------ | ------------------------------------------------------------------------------------ | -------------- | --------------------------------- |
| **Primary Memory**                                     |                                                                                      |                |                                   |
| CPU Registers                                          |                                                                                      | fastest        | 32/64 bits                        |
| Cache Memory<br>- L1 Cache<br>- L2 Cache<br>- L3 Cache | Static RAM<br>- Inside a CPU Thread<br>- Shared by a CPU Core<br>- Shared by the CPU | extremely fast | <br>32+32 KB<br>1 MB<br>1 - 16 MB |
| Main Memory                                            | Dynamic RAM                                                                          | very fast      | 1 - 128 GB                        |
| **Secondary Storage**                                  |                                                                                      |                |                                   |
| Non-Volatile Storage                                   | Sata SSD, NVMe SSD                                                                   | fast           | 50 - 1000 GB                      |
| Hard Disk Drives                                       | Disks -> Tracks -> Sectors                                                           | normal         | 0.5 - 5TB                         |
| **Tertiary Storage**                                   |                                                                                      |                |                                   |
| Optical Storage                                        | CD, DVD, Blu-ray etc.                                                                | slow           | 0.5 - 100+ GB                     |
| Magnetic Tape Storage                                  | Tape                                                                                 | extremely slow | 1 - 15 TB                         |

![[OS Architecture | 1080]]

**Virtual Memory** -> Logical extension of the memory(RAM). This is done by reserving an area on the storage(Hard Drive) as VRAM. This memory is used when there are processes that are bigger than the amount of memory available.

**Principle of Locality** -> a fundamental concept in operating systems that describes how programs tend to access a relatively small portion of their address space at any given time. This principle is crucial for optimizing the performance of memory systems, including caches, virtual memory, and paging systems.

# Interrupts
*A signal that asks for attention from the OS Kernel. Operating Systems are driven by interrupts.* 

It transfers control to the **interrupt service routine** which is a code that is run when we encounter an interrupt. This is done using the **interrupt vector** which is a special table in memory that holds information about all interrupts. The OS preserves the state of the CPU.
### Software Interrupt
*It is generated when we use a System Call* like `int 21h`. 
- It can also be generated when there is an error of some kind where it demand immediate attention from the OS. It is called an **exception** and examples include `ZeroDivisionError`, `StackOverflowError`, `IndexOutOfBoundsError` etc.
### Hardware Interrupt
*It is generated by the controllers of other devices like I/O.*
- These are generated by devices to divert the control flow towards their execution or when they have completed a task. These interrupts can be maskable (ignore-able) or non-maskable (un-ignore-able).
- There are **physical pins** on the microprocessor chip itself; when a signal is applied to it then a hardware interrupt is generated.

**Timer** -> Generates an interrupt if any program has been running for too long, to prevent infinite loops.
## I/O Interface
 *Method used to transfer data between CPU, storage and I/O devices.*
 
 It is essential component is a computer system which allows the communication between various devices and the CPU.
### I/O Subsystem
Manages input/output operations between devices and programs.
- **Buffering** -> Temporary storage of data during transfer.
- **Caching** -> Fast storage of frequently accessed data.
- **Spooling** -> Overlapping output of one job with input of another.
### Transfer Techniques
#### Programmed I/O
*It uses the I/O instructions written in the computer program.* 

The instructions in the program start every data item transfer; where it is between memory and CPU register. This requires continuous attention from the CPU.
- **Advantages** -> Simple to implement and requires very little hardware support.
- **Disadvantages** -> Processor has to wait for a long time for either sending or receiving of data which causes the performance of the entire system to be severely degraded.
#### Interrupt-Driven I/O
*It uses hardware-generated interrupts.*

As soon as the device is ready to send/recieve a signal; an interrupt is generated which gets the attention of the CPU. This doesn't require continuous attention from the CPU.
- **Advantages** -> It is faster and more efficient and It also requires very little hardware support.
- **Disadvantages** -> Complicated to implement and it is tough to make it work.
#### Direct Memory Access
*Used to let devices to directly communicate with the memory without the involvement of the CPU.*

It is a device that removes the intervention of the CPU from the communication between devices and memory which can get limited by CPU's speed. A single interrupt is generated by block instead of per byte.

# System Calls
*Programming Interfaces for services provided by the OS. These are calls to the OS for performing a certain action*

They are usually written in high-level languages like C, C++ or Rust. There are two ways to access System Calls.

1. Direct Access by invoking the System Call
2. Using an API to access System Call

Directly invoking the system call is the faster method but there are many problems with it. System Calls are different between operating systems. This means that a program which accesses a system call directly has to make efforts so that it can become **portable**. You also need many more parameters for using syscalls.

Its better to instead use an API to access the System Call Interface instead. APIs are functions which can be used to indirectly access something else (without having to deal with the low-level stuff). Calling an API calls the equivalent System Call for each OS making the program **portable**.

`WIn32` API -> Windows
`POSIX` API -> UNIX-based
`Java` API -> Java Virtual Machine

## Parameter Passing
There are 3 ways to pass parameter for system calls
1. By passing the values in the registers. (Simplest)
2. By storing them in a location and passing the location reference.
3. By pushing/popping them in the stack.
## Types of System Calls
System Calls can be used for different tasks:
- Process control -> create, terminate, end, abort, load, execute etc.
- File management -> create, delete, open, close, read, write, reposition etc.
- Device management -> request, release, read, write, reposition etc.
- Information maintenance -> get/set time, date, system data etc.
- Communication -> create/delete connection, send/receive messages etc.
- Security -> get/set permissions, control access etc.

# Process
A *program* is a set of instructions that is not under execution. (Passive Entity)
A *process* is a program that is running/under execution. (Active Entity)
## Process Sections
A process in a computer system is an instance of a running program. Each process is allocated its own memory space which is divided into several sections, each with a specific purpose. The main sections of a process memory layout typically include:

1. **Text (Code) Section** -> contains the executable instructions of the program. It is usually read-only to prevent accidental or malicious modification of the instructions.
2. **Data Section** -> contains global and static variables.
3. **Heap** -> a region of memory used for dynamic memory allocation. When a program requests memory at runtime (e.g., via `malloc` in C or `new` in C++), it is allocated from the heap.
 4. **Stack** -> a region of memory that stores temporary variables created by each function (including main). This includes function parameters, return addresses, and local variables.
5. **Program Counter** (PC) / Instruction Pointer (IP) -> a special register in the CPU that keeps track of the next instruction to be executed in the text section.

Here's a typical layout of a process's memory:
![[Process Memory.excalidraw|50%]]

## Process Scheduling
A key function of an operating system that manages the execution of processes by deciding which process to run at any given time on the CPU. The primary objective of process scheduling is to ensure efficient and fair use of the CPU, maximizing system performance and responsiveness.
### Process States
Every process can have one of these 5 states:
   - **New**: The process is being created.
   - **Ready**: The process is waiting to be assigned to a CPU.
   - **Running**: The process is currently being executed on the CPU.
   - **Waiting**: The process is waiting for some event (such as I/O completion) to occur.
   - **Terminated**: The process has finished execution.
### Scheduler Types
   - **Long-term scheduler (job scheduler)**: Determines which processes are admitted to the system for processing. It controls the degree of multiprogramming (the number of processes in memory).
   - **Short-term scheduler (CPU scheduler)**: Selects which of the ready, in-memory processes are to be executed next by the CPU. It makes frequent decisions and must be fast.
   - **Medium-term scheduler**: Temporarily removes processes from main memory and places them in secondary storage (swapping). It is used to improve the process mix.
### Scheduling Criteria
   - **CPU Utilization**: Keep the CPU as busy as possible.
   - **Throughput**: Number of processes completed per time unit.
   - **Turnaround Time**: Total time taken to execute a process from submission to completion.
   - **Waiting Time**: Total time a process spends waiting in the ready queue.
   - **Response Time**: Time from submission of a request until the first response is produced.

### Scheduling Algorithms

1. **First-Come, First-Served (FCFS)**:
   - Processes are executed in the order they arrive in the ready queue.
   - Simple but can lead to the "convoy effect," where short processes wait for long processes.

2. **Shortest Job First (SJF)**:
   - Selects the process with the smallest execution time.
   - Minimizes average waiting time but requires accurate prediction of process lengths.

3. **Priority Scheduling**:
   - Each process is assigned a priority, and the CPU is allocated to the process with the highest priority.
   - Can lead to starvation if low-priority processes are continually overlooked.

4. **Round Robin (RR)**:
   - Each process is assigned a fixed time slice (quantum) and is cycled through the ready queue.
   - Ensures fair CPU allocation but can have high overhead with very small time slices.

#### Scheduling Queues
- **Ready Queue** -> Holds processes that are ready to run but are waiting for CPU time. Managed by the short-term scheduler.
- **Wait Queue** -> Holds processes that are waiting for some event or resource to become available. Managed by the operating system's event handling mechanisms.

==--> See OS Labs PDF==

## Process Switching
*Process switching is the act of changing one process from another by saving all of the state of the currently executing process.*

When we do this to execute a different process, it is called **Context Switching**.

- **Pre-emptive Scheduling** -> When a CPU jumps from one process to another before completing it.
- **Non-pre-emptive Scheduling** -> When a CPU never jumps from one process to another before completing it.

## Process Communication
Processes can usually not communicate with each other. We use special models to do this:
1. **Shared Memory Model** -> Uses a shared memory region for communication. Typically used for communication between processes on the same machine. It is faster and good for exchanging large amounts of data and it requires code to be written.

2. **Message Passing Model** -> Uses a message passing facility for communication. Typically used in distributed environments where processes reside on remote machines. It is slower and used for small amounts of data and doesn't require code.

OS is heavily involved in both models but Shared Memory requires only a single syscall to be generated then the reading-writing doesn't require any syscalls. Message Passing requires a syscall to be generated for every single message being sent.

#### Unbounded vs Bounded Buffer
**Unbounded Buffer** -> No limit on the buffer's size.
**Bounded Buffer** -> There is a limit to the buffer's size.
#### Direct vs Indirect Communication
**Direct Communication** -> when each process explicitly specifies the recipient or the sender. This requires the sender knowing the reciever's name.
**Indirect Communication** -> when processes exchange messages through a mailbox. This is done by "subscribing" to mailbox whom "publish" the sent mail to everyone else.

# Thread
*A lightweight process that runs concurrently with others in the same program, sharing memory and resources, with its own program counter, stack, and local variables.*

**Purpose ->** Threads enable **concurrent execution**, allowing programs to perform multiple tasks simultaneously and improve responsiveness.

**Thread creation** is lightweight as compared to **process creation**. 
## Benefits of Threads

- **Responsiveness** -> Threads allow for continued execution even if part of the program is blocked, enhancing responsiveness, especially in user interfaces.
- **Resource Sharing** -> Threads share the same memory space and resources within a process, making it easier to share data and collaborate between different parts of the program.
- **Efficiency** -> Thread creation and context switching are generally more lightweight and efficient compared to creating separate processes, reducing overhead.
- **Scalability** ->Threads can take advantage of multicore architectures, allowing programs to run multiple tasks in parallel and improve overall performance.
## Multicore Programming

Making use of multiple CPU cores in modern processors for simultaneous task execution. There are a few drawbacks including: Dividing activities, Balance, Data splitting, Data dependency, Testing and debugging.

**Parallelism** -> Refers to the simultaneous execution of multiple tasks or processes on multiple processors or cores.
**Concurrency** -> Supports multiple tasks making progress (running) simultaneously.
- In **single-core** systems -> **concurrency** is achieved through the `scheduler`, which rapidly switches between processes.
- In **multicore** systems -> **concurrency** can lead to actual parallelism, as each core can execute separate threads simultaneously.

**Multithreaded programming** enables more efficient utilization of multiple computing cores and improved concurrency, with parallel execution possible on multicore architectures.

<center>Multithreaded Server Architecture</center>

![[WhatsApp Image 2024-06-04 at 19.17.38_86f4b16e.jpg]]

### Concurrency vs Parallelism

- **Concurrency**: 
    - Supports multiple tasks making progress.
    - Allows tasks to proceed in an overlapping manner, even if they are not executing simultaneously.
    - Achieved through techniques like multitasking, where tasks are interleaved over time.
    - Commonly seen in single-core systems, where the CPU scheduler rapidly switches between processes to give the illusion of simultaneous execution.
- **Parallelism**:
    - Involves actual simultaneous execution of multiple tasks.
    - Tasks execute concurrently on separate processing units, such as multiple CPU cores.
    - Enables tasks to execute simultaneously, enhancing performance and throughput.
    - Commonly observed in multicore systems, where each core can execute its own set of instructions concurrently with others.
## Types of Parallelism 

1. ==Data Parallelism==
Involves distributing subsets of the same data across multiple computing **cores** and performing the **same operation** on each core. 
- **For example ->** in summing the contents of an array, different cores can sum different segments of the array concurrently.

2. ==Task Parallelism==
Involves distributing tasks (**threads**) across multiple computing cores, where each thread performs a **unique operation.** Tasks may operate on the same or different data. 
- **For instance ->** in statistical operations on an array, each core may execute a different statistical operation on the same array.
## User threads and Kernel Threads

- **User Threads** -> Managed by a user-level threads library and **Fast** creation and context switching.
	- **Examples ->** POSIX Pthreads, Windows threads, and Java threads.
- **Kernel Threads** -> Supported and managed directly by the operating system kernel and  **Slower** due to kernel involvement.
	- **Examples ->** Windows, Linux, macOS, iOS, and Android.
- Relationship between User Threads and Kernel Threads:
	- **User threads** are supported above the kernel and managed without kernel support.
	- **Kernel threads** are directly supported and managed by the operating system.
## Thread Libraries
*These are APIs provided to programmers for creating and managing threads within a program. Implemented either entirely in user space or as a kernel-level library supported by the operating system.*

1. **Pthreads** -> May be provided as user-level or kernel-level.
- A POSIX standard (IEEE 1003.1c) API for thread creation and synchronization.
- Common in UNIX operating systems (**Linux** & **macOS**).

2. **Windows Threads** -> Provided by the Windows operating system.
- API for thread creation and synchronization.
- Allows developers to create and manage threads in Windows-based applications.

3. **Java Threads** -> Managed by the Java Virtual Machine (JVM).
- Implemented using the underlying operating system's threads model.
- Creation methods -> Extending the Thread class OR Implementing the Runnable interface.
- **Standard practice ->** Implementing the Runnable interface.
## Implicit Threading
**Automatic creation** and **management** of threads by `compilers` and `runtime libraries`. Reduces complexity for programmers compared to explicit thread management.

 There are 5 methods of Implicit Threading
	1. Thread Pools
	2. Fork-Join
	3. OpenMP
	4. Grand Central Dispatch
	5. Intel Threading Building Blocks.
### Thread Pools
A set of threads that are reused for the execution of tasks, avoiding the overhead of creating and destroying threads. They have faster responses, efficient resource management and efficient task scheduling.
### Open MP
an API that supports parallel programming on multi-platform shared memory systems, providing a simple and portable way to distribute tasks across threads.

# Process Synchronization
*Process synchronization refers to the coordination of processes or threads to ensure that they execute in a correct and predictable manner when accessing shared resources.*

When multiple processes are executed; They can be in "serial mode" or "parallel mode". These processes can be **cooperative** (one process affects another) or **independent** (one process doesn't affect another). Cooperative Processes have shared resources between them (this can be memory, I/O or code).

## Mutual Exclusion
Mutual exclusion is a fundamental concept in concurrent programming and operating systems, aimed at preventing multiple processes or threads from simultaneously accessing a shared resource or critical section of code. This is essential to avoid race conditions, data corruption, and ensure consistency and correctness in multi-threaded or multi-process applications.

The Key Aspects of Mutual Exclusion are Critical Section, Locks and Atomic Operations.
### Code Segments of a Process
Processes have 4 code segments: 
- **Entry Section** -> The code segment before its critical section. It is responsible for asking access to the critical section.
- **Critical Section** -> The code segment where all the shared resources/variables (global variables) are. When one process is in its critical section, no other can enter their own critical section.
- **Exit Section** -> The code segment after its critical section. It is responsible for releasing the shared resources and signalling other processes that it is free.
- **Remainder Section** -> The code segment that does not access any shared variables and makes up the rest of the process.

```c
while (true) {
	//Entry Section
	
	//Critical Section
	
	//Exit Section
	
	//Remainder Section
}
```

### Atomic Variables
<small>also known as atomic operations or atomic types</small>

They are variables/operations in concurrent programming that are guaranteed to be executed as a single, indivisible step. This means that no other thread can observe the operation in an intermediate state. 

Atomic variables are crucial for ensuring data integrity and consistency in a multi-threaded environment without the need for complex locking mechanisms.

## Synchronization/Concurrency Problems

1. **Race Conditions** -> Occur when multiple processes or threads access shared resources concurrently, and the outcome depends on the timing of their execution.
2. **Deadlock** -> Situations where two or more processes are unable to proceed because each is waiting for the other to release a resource.
3. **Livelock** -> Similar to deadlocks, but the states of the processes involved continuously change with respect to one another, none progressing.
4. **Starvation** -> A process is perpetually denied necessary resources to proceed with its work.
### Examples
1. Two threads incrementing a shared counter simultaneously may lead to incorrect results if not properly synchronized.
2. Process A holds Resource 1 and waits for Resource 2, while Process B holds Resource 2 and waits for Resource 1.
3. Two processes repeatedly respond to each other’s actions, but neither makes progress.
4. A low-priority thread never gets CPU time because higher-priority threads keep preempting it.

## Producer-Consumer Problem
*A scenario that occurs when a producer adds items to buffer an a consumer takes items from the same buffer, concurrently.*

In this scenario any of the synchronization problems can occur (Race Conditions, Deadlocks, Livelocks, Starvation) if not properly controlled. These can also happen:
- Buffer Overflow -> If producer produces more/faster than consumer consumes.
- Buffer Underflow -> If producer produces less/slower than consumer consumes.
#### Example Code
Suppose you have two processes: A **Producer** which produces items and a **Consumer** which consumes those items. 
- There is a **Buffer** of fixed size. 
- The producer shouldn't produce more than the capacity of the buffer.
- The consumer shouldn't consume when the buffer is empty.
- Both processes run concurrently.

```c
int count = 0;

void producer(void) {
	int item_p;
	while (true) {	
		produce_item(item_p);
		
		while (count == BUFFER_SIZE); //If the buffer is full don't do anything.
		 
		buffer[in] = item_p; 
		in = (in + 1) % BUFFER_SIZE; 
		count++; 
	}
}

void consumer(void) {
	int item_c;
	while (true) {
		while (count == 0); //If the buffer is empty don't do anything.
		
		item_c = buffer[out]; 
		out = (out + 1) % BUFFER_SIZE; 	
        count--; 
        
        consume_item(item_c);
	}
}
```

## Control Mechanisms
These are synchronization mechanisms used to control access to shared resources in concurrent programming.

1. **Mutex Locks** -> A mutex (mutual-exclusive-object) is a synchronization "primitive" that ensures that only one thread can access a resource at a time. It is essentially a lock that provides mutual exclusion. They are binary in nature and give ownership to the locker.
2. **Semaphores** -> A semaphore is a more general synchronization primitive that can control access to a resource by multiple threads.They are integer variables which can allow multiple threads.
	1. **Counting Semaphore** -> A semaphore has an associated counter that can be incremented or decremented. The counter represents the number of available units of the resource.
	2. **Binary Semaphore** -> A binary semaphore is similar to a mutex but does not have the ownership restriction.

## Labs

Operating Systems Labs - Finals Notes
# 1. Command Prompt
*Command Prompt, cmd.exe, is a Windows program that emulates the DOS's abilities.*

- For file paths, use `\` to separate them (for drive names also use `:`)
- For parameters, use `/` 

This command combines the text of one, two and three .txt files and copies it into the New.txt that is inside the C -> New Folder. `/d` makes it decrypt the files if they're encrypted.
```shell
copy one.txt + two.txt + three.txt C:\New Folder\New.txt /d
```

| **Commands**                                                                         | What it is used for                                                                                                                                                                          |
| ------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `dir`<br>`tree \`                                                                    | Shows a list of all files and folders in the current folder.<br>Shows the folder structure of the current folder.                                                                            |
| `dir /a:`                                                                            | Shows a list of all files and folders in the current folder, <br>including hidden or system files.                                                                                           |
| `attrib (file)`<br>`attrib +r (file)`<br>`attrib -r (file)`<br>`attrib -r (file) /s` | Shows all attributes of a file.<br>Adds the "read-only" attribute to a file.<br>Removes the "read-only" attribute from a file.<br>Removes the "read-only" attribute from all subfolders.<br> |
| `date /t`<br>`time /t`                                                               | Shows the system date.<br>Shows the system time.                                                                                                                                             |
| `date (mm-dd-yy)`<br>`time (HH:MM:SS)`                                               | Sets the given date as system date.<br>Sets the given time as system time.                                                                                                                   |
| `format (drive):`                                                                    | Used to format a drive using default size.<br>                                                                                                                                               |
| `prompt (text)`                                                                      | To change the command prompt.                                                                                                                                                                |
| `color (number)(number)`                                                             | To change the command prompt bgcolor and fgcolor.                                                                                                                                            |
| `copy (file)(file)`<br>`copy (file)(folder)`<br>`xcopy (folder)(folder)`             | Copies the file contents to another file.<br>Copies the file to the specified folder.<br>Copies the folder to the specified folder.                                                          |
| `ren (file)(name)`<br>`ren (file)(file)`                                             | Renames the specified file into the specified name.<br>Renames all specified files into the specified name.                                                                                  |
| `md (folder)`                                                                        | Creates a folder with the specified name.                                                                                                                                                    |
| `cd`<br>`cd (folder)`<br>`cd \`                                                      | Shows the name of the current folder. **Same as `chdir`**<br>Changes to the specified folder.<br>Changes to the parent folder of current folder.                                             |
| `rd (folder)`<br>`rd /s (folder)`                                                    | Deletes the specified empty folder. **Same as `rmdir`**<br>Deletes the specified folder and its subfolders.                                                                                  |
| `del (file)`<br>`undelete`                                                           | Deletes the specified file. **Same as `erase`**<br>Undos last delete action.                                                                                                                 |
| `del (path)\*.*`<br>`undelete (path) \all`                                           | Deletes all files in the specified path. **Same as `erase`**<br>Undos all deleted actions at the specified path.                                                                             |
| `chkdsk (drive):`                                                                    | Checks the specified drive for errors.                                                                                                                                                       |
- `(file)` -> File path + name.
- `(folder)` -> Folder path + name.
- `(path)` -> File path.
- `(name)` -> File name.
- `(drive)` -> Drive name.
- `(mm-dd-yy)` -> Date formatting.
- `(HH:MM:SS)` -> Time formatting.
- `(text)` -> Text.
- `(number)` -> Number. (Each number means a different color)

# 2. Batchscript
*A command line scripting language for batch files.*

**Batch File** -> A computer file which contains a list of instructions to perform.
These are run using the **command line interpreter** and can have the `.bat` or `.cmd` extension.

**Scripting languages** -> A programming language that supports scripts: programs written for a special run-time environment that automate the execution of tasks that could alternatively be executed one-by-one by a human operator.

This is a script for getting all tcp/ip, ping and traceroute details into a file named `results.txt`.
```shell
@echo off
ipconfig /all >> results.txt
ping google.com >> results.txt
tracert google.com >> results.txt
```

- `>>` operator is used to store a result into a file. 
- `set` is used to declare variables.
- `%` is used before and after variable name to access its value.
- We use the `/A` switch to store numeric value in the variable.

> [!QUESTION] Task
> Write a program that takes the product and difference of two number, displays it and stores it inside a file.

1. Declaring two variables and then taking their product and difference.
```shell
@echo off
set /A num1 = 20
set /A num2 = 10
set /A product = %num1% * %num2%
set /A difference = %num1% - %num2%
```

2. Displaying the product and experience on screen.
```shell
echo product is (%product%)
echo difference is (%difference%)
```

3. Storing it in a file.
```Shell
%product% >> result.txt
%difference% >> result.txt
```
# 3. Powershell
*A command line scripting language that is designed for sysadmin and is very powerful.*

**To use powershell**: Press Win key -> Search for Powershell ISE -> Create a new file.

<table style="border: 1px solid red; padding: 5px;" >
<tr>
<td><b>Comparison Operators</b></td>
<td><b>Logical Operators</b></td>
</tr>
<tr>
<td>
eq -> equals to <br>
lt -> less than <br>
gt -> greater than <br>
ne -> not equals to <br>
le -> less than or equal to <br>
ge -> greater than or equal to
</td>
<td>
AND -> logical and <br>
OR -> logical or <br>
NOT -> logical not <br>
</td>
</tr>
</table>

- `$` is used to declare variable names.
- `write-host()` function is used to give output to display.
- `read-host()` function is used to take input to display.

> [!QUESTION] Task
> •	Write Shell Script which checks a number that whether it is even or odd and prints the message  on screen
•	Write Shell Script which checks a number that whether it is positive or negative and prints the message on screen
•	Write Shell Script which compares 2 numbers and prints the greater

1. To declare variables
```powershell
$x = 1
$y = -1
```

2. Odd-Even conditional
```powershell
if($x % 2 -eq 0){Write-Host("The number is even.")}
else{Write-Host("The number is odd.")}
```

3. Positive-Negative conditional
```powershell
if($x -eq 0){Write-Host("The number is 0.")}
elseif($x -ge 0){Write-Host("The number is positive.")}
else{Write-Host("The number is negative.")}
```

4. Comparison conditional
```powershell
if($x -ge $y){Write-Host($x)}
else{Write-Host($y)}
```

# 4-5. Scheduling Algorithms
Aim is to assign processes to be executed by the processor in a way that meets system objectives, such as response time, throughput, and processor efficiency. It is broken down into three separate functions: long term scheduling, medium term scheduling and short term scheduling respectively.

- **First Come First Serve Scheduling Algorithm** (FCFS) -> It selects the processes from the ready-queue in the order of their arrival.
- **Shortest Job First Scheduling Algorithm** (SJF) -> It selects the processes from the ready-queue in order of their size.
- **Round Robin Scheduling Algorithm** (RR) -> It selects the processes from the ready-queue in FCFS way but only executes small chunks at a time (based on time quantum).
- **Priority Queue Scheduling Algorithm** -> It selects the processes from the ready-queue in order of their priorities. 

> [!QUESTION] Task
> Using the instructions for FCFS and SJF algorithm -> Compute **waiting-time**, **avg-waiting-time**, **turn-around-time** and **avg-turn-around-time** and Draw it.
## Python Code
<small>This code can be written in any language (C, C++, Java) and Sir has written it in C. For me, Python is the easiest and hence I used it for the code.</small>
### FCFS Algorithm
```python
#Declaration and Initialization
p_id, bt, wt, tat = [], [], [], []

#Taking number of processes as input.
P = int(input("Enter the number of processes: "))

#Appending processes and burst times. 
for i in range(P):
    p_id.append(i+1)
    bt.append(int(input(f"Enter {i+1}th burst time: ")))

#Initializing waiting and turnaround times.
wt.append(0)
tat.append(bt[0])

#Appending waiting times.
for i in range(P-1):
    wt.append(wt[i] + bt[i])

#Appending turnaround times.
for i in range(P-1):
    tat.append(tat[i] + bt[i+1])

#Calculating the Average waiting and turnaround times.
avgwt = sum(wt)/P
avgtat = sum(tat)/P

#For printing output
print("--------------------------------------------")
print("\nPID  |   BT  |   WT  |   TAT")
for i in range(P):
    print(p_id[i],"\t", bt[i], "\t", wt[i], "\t", tat[i])
print("--------------------------------------------")

print(f"Average WaitingTime: {avgwt} seconds.")
print(f"Average TurnAroundTime: {avgtat} seconds.")
```

### SJF Algorithm
Exactly the same code as above just add this after Appending Processes and Burst Time.

```python
# Sorting processes based on burst time
sorted_indices = sorted(range(P), key=lambda x: bt[x])
p_id = [p_id[i] for i in sorted_indices]
bt = [bt[i] for i in sorted_indices]
```

## Gantt. Chart
**Q. Suppose we have five processes like this table, draw the gantt. chart for each Scheduling Algorithm if the time quantum is 1.**

| Process Number | Burst Time | Priority |
| -------------- | ---------- | -------- |
| $P_1$          | 10         | 3        |
| $P_2$          | 1          | 1        |
| $P_3$          | 2          | 3        |
| $P_4$          | 1          | 4        |
| $P_5$          | 5          | 2        |

![[Scheduling.excalidraw|100%]]

# 6. System Calls

**System Calls** -> When a program in user mode requires access to RAM or a hardware resource, it must ask the kernel to provide access to that resource. This is done via something called a system call. 

## Process Creation (Windows)

```c
// Header Files
#include <windows.h> // For Windows API functions.
#include <stdio.h> // For Standard I/O functions.
#include <tchar.h> // For handling Unicode/ASCII characters.

// Main Function (_tmain supports Unicode)
void _tmain(int argc, TCHAR *argv[]) 
{
    STARTUPINFO si; // Has information on how to start a process.
    PROCESS_INFORMATION pi; // Has information on the newly created process.
	
	// Initialize si and pi both to 0 memory. Set the size of si.
    ZeroMemory(&si, sizeof(si));
    si.cb = sizeof(si);
    ZeroMemory(&pi, sizeof(pi));
	
	// If the number of arguments is not 2 then just print usage info and exit.
    if(argc != 2)
    {
        printf("Usage: %s [cmdline]\n", argv[0]);
        return;
    }
	
    // Start the child process. 
    if(!CreateProcess(NULL, argv[1], NULL, NULL, FALSE, 0, NULL, NULL, &si, &pi)
    ){
        printf( "CreateProcess failed (%d).\n", GetLastError() );
        return; // If the process fails then print error and exit.
    }
	
    // Wait until child process exits.
    WaitForSingleObject(pi.hProcess, INFINITE);
	
    // Close process and thread handles. 
    CloseHandle(pi.hProcess);
    CloseHandle(pi.hThread);
}
```

**CreateProcess:** This function creates the new process. It has 10 parameters and returns a bool which is false if we couldn't create a process:

1. Application Name -> `NULL` tells to use the command line.
2. Command Line -> `argv[1]` tells the command line to use.
3. Process Attributes -> `NULL` means process is un-inheritable.
4. Thread Attributes -> `NULL` means thread is un-inheritable.
5. Inherit Handles -> `FALSE` means no handle inheritance.
6. Creation Flags -> `0` means no creation flags. 
7. Environment -> `NULL` means use parent's environment.
8. Current Directory -> `NULL` means use parent's directory.
9. Startup Info -> variable `&si`.
10. ProcessInformation -> variable `&pi`.

> [!QUESTION] Task
> Create a PowerISO process using Windows System call.
```c
#include <windows.h>
#include <stdio.h>
#include <tchar.h>

void _tmain(int argc, TCHAR *argv[]) 
{
	char powerIso[] = "/path/to/poweriso";
	char args[] = "-open -wait -close -eject";
	
    STARTUPINFO si; 
    PROCESS_INFORMATION pi; 
	
    ZeroMemory(&si, sizeof(si));
    si.cb = sizeof(si);
    ZeroMemory(&pi, sizeof(pi));

    if(!CreateProcess(powerIso, args, NULL, NULL, FALSE, 0, NULL, NULL, &si, 
    &pi)) {
        printf( "CreateProcess failed (%d).\n", GetLastError());
        return; 
    }
	
    WaitForSingleObject(pi.hProcess, INFINITE);

    CloseHandle(pi.hProcess);
    CloseHandle(pi.hThread);
}
```

## Process Creating (Linux)
There are two ways to doing system calls in Linux:
1. `fork()` -> Creates a new process while duplicating the current one. The one who called fork is called the **parent process** while the created process is called **child process**. It returns a negative value if process creation failed and zero (or positive value) if process creation succeeded. In case of positive value; the value is the process ID of the child process.

2. `exec()` -> Creates a new process while replacing the current one. This basically replaces the old process that called it with a new one. There is a whole family of exec functions: `execl()`, `execle()`, `execlp()`, `execv()`, `execve()`, `execvp()`.

```c
// Header Files
#include <unistd.h> // For
#include <stdio.h> // For POSIX OS Functions.
#include <sys/types.h> // For datatypes like pid_t
#include <stdlib.h> // For exit()

int main() {
	pid_t pid;
	pid = fork();
	
	if (pid < 0) { // error occurred
		fprintf(stderr, "Fork failed!\n");
		exit(-1);
	} 
	else if (pid == 0) { // child process
		printf("Child PID = %d\n", getpid());
	} 
	else { // parent process
		printf("Parent PID = %d, Child PID = %d\n", getpid(), pid);
		printf("Parent exiting!\n");
		exit(0);
	}
}
```

> [!QUESTION] Task
> Create a Firefox process using Linux exec( ) System call.
```c
#include <stdio.h>
#include <unistd.h>

int main() {
  char* path = "/path/to/firefox";

  // Attempt to execute Firefox
  execlp(path, NULL);

  // If execlp returns, it indicates an error
  perror("execlp failed");
  return 1;
}
```

# 7. Threads
There are two ways of creating a thread.
1. By creating a Runnable Interface -> `class Multi implements Runnable`. This approach is used when we want to execute our class as a Thread.
2. By extending the Thread Class -> `class Multi extends Thread`. This approach is more flexible in handling multiple threads.

- **Step 1** - Implement the `run()` method of the Runnable Interface or the Thread Class.
- **Step 2** - Create a Thread object using a constructor.
- **Step 3** - Call the `start()` method to execute the `run()` method.

```java
class Multi implements Runnable{
    private Thread t;
    private String tname;
    
    Multi(String name){
        this.tname= name;
    }
    
    public void run() {
        try {
	        for (int x=0; x<=4; x++) {
	            System.out.println("running " + tname);
	            Thread.sleep(1000);
	        }
        }
        catch(Exception e){
            Thread.currentThread().interrupt();
	    }
    }
    
    public void start(){
        System.out.println("Starting " +  tname );
	    if (t == null) {
		    t = new Thread (this, tname);
	        t.start();
	    }
    }
}
   
public class Multithreading {
    public static void main(String[] args) {
	    Multi th1 = new Multi("thread 1");
	    Multi th2 = new Multi("thread 2");
	    th1.start();
	    th2.start();
    }
}
```

# 8. Thread Synchronization
**Thread Synchronization** is used when we need to synchronize threads so that only one thread is able to access resources at a time.

In Java, the `synchronized` block is a keyword used to ensure that only one thread can execute a specific block of code at a time. It's used to prevent thread interference and memory consistency errors when multiple threads access shared resources.

We can add it to the `start()` method in previous code to make it synchronized.

```java
public synchronized void start(){
	System.out.println("Starting " +  tname );
	if (t == null) {
		t = new Thread (this, tname);
		t.start();
    }
}
```

There is also the `join()` method that is provided by the java.lang.Thread class, and it allows one thread to wait until another thread has completed its execution (It waits for the thread to die).