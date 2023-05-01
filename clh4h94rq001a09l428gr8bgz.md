---
title: "Operating system (part - 2) 
Multi-Tasking vs Multi-Threading"
seoTitle: "multi-tasking-vs-multi-threading"
datePublished: Mon May 01 2023 06:46:29 GMT+0000 (Coordinated Universal Time)
cuid: clh4h94rq001a09l428gr8bgz
slug: operating-system-part-2-multi-tasking-vs-multi-threading
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/z508Zk08HNU/upload/e95ed9939845810b6a7df1398f43d82d.jpeg
tags: operating-system, multithreading, process, multitasking, program

---

In the Operating system (Part - 1) we learned about

* **"what is an operating system"**
    
* **What will happen if there is no OS?**
    
* **some key functions of OS**
    
* **Some of the goals of OS**
    
* **types of os**
    
* **some real-world examples where these os are used**
    

In part - 2 we will learn what is Multi-Tasking and Multi-Threading and will compare the two.

So let's get started

Before learning about these concepts we should know what is a "Program" and "Process".

**What is a Program?**

A program is a set of instructions that are written in a programming language and compiled into an executable file that can be run on a computer. Once the program is compiled, it is stored on the computer's disk as an executable file, which can be executed by the computer's operating system. When a user wants to run the program, they can simply double-click on the executable file and the operating system will load the program into memory and execute its instructions. The program will then perform its specified job or operation on the computer.

**What is Process?**

When a program is executed, it becomes a process in the computer's operating system. A process is loaded into the computer's primary memory, also known as RAM (Random Access Memory), where its instructions are read and executed by the processor. As the program runs, it may read and write data from/to the memory, and the processor may allocate and deallocate memory dynamically as needed. The operating system manages the execution of processes, allocating system resources such as memory, CPU time, and input/output operations to each process as needed. Once a process completes its execution or is terminated, the memory it was occupying is released and made available for other processes to use.

**What is a Thread?**

* A thread is a separate, independent sequence of instructions within a process that can be executed concurrently with other threads within the same process. Threads are often referred to as "lightweight" processes because they share the same memory space as the process they belong to and require less overhead to create and manage than a separate process.
    
* Threads are used to achieve parallelism within a process by dividing its tasks into independent paths of execution. By doing so, multiple threads can execute different parts of the process simultaneously, making it possible to take advantage of multi-core processors and improve overall performance.
    
* Examples of applications that use threads include web browsers (where multiple tabs can be loaded and rendered concurrently), text editors (where spellchecking, formatting, and saving can be done concurrently by multiple threads), and multimedia software (where video and audio processing can be done concurrently).
    

Now let's see the difference between **Multitasking** and **Multithreading**

|  | Multitasking | Multithreading |
| --- | --- | --- |
| Definition | The ability of an operating system to run multiple programs or processes concurrently. | The ability of a program to run multiple threads of execution within the same process. |
| Purpose | Allows multiple users to share a single system or multiple programs to run at the same time. | Improves the performance and responsiveness of a single program by allowing it to perform multiple tasks concurrently within the same process. |
| Resource sharing | Programs or processes run in their own memory space and do not share resources by default. | Threads share memory and other resources within the process they belong to. |
| Coordination | Inter-process communication (IPC) mechanisms, such as pipes and sockets, are used to coordinate and communicate between different processes. | Intra-process communication mechanisms, such as locks and semaphores, are used to coordinate and communicate between different threads. |
| Overhead | Higher overhead due to the need for context switching between different processes. | Lower overhead since threads share the same memory space and can communicate and coordinate more easily. |
| Use cases | Useful in systems with multiple users or where multiple programs need to be run simultaneously. | Useful for improving the performance and responsiveness of a single program, such as a web server, multimedia software, or a game. |

**Thread scheduling:-**

Thread scheduling refers to the process by which the operating system decides which thread should execute next on the CPU. Thread scheduling is an important part of managing threads in a program because it determines how efficiently and fairly resources are allocated to different threads.

**Comparison between Thread Context Switching and Process Context Switching: -**

| Criteria | Thread Context Switching | Process Context Switching |
| --- | --- | --- |
| Definition | The process of switching from one thread to another within a process | The process of switching from one process to another, which may have a different memory address space |
| What is saved/restored | The state of the executing thread is saved and restored | The state of the entire process is saved and restored |
| Type of switching | Switching between threads in the same process | Switching between independent processes |
| Memory address space | Does not involve switching of memory address space | Involves switching of memory address space |
| Speed | Fast | Slow |
| Cache state | CPU cache state is preserved | CPU cache state is flushed |

In summary, Thread Context Switching involves saving and restoring the state of the executing thread within the same process, which is a fast process that doesn't involve switching of memory address space. Process Context Switching, on the other hand, involves saving and restoring the state of the entire process, including its memory address space, which is a slow process that happens when switching between independent processes. Additionally, Thread Context Switching preserves the CPU cache state, while Process Context Switching flushes the CPU cache state.

*tune in for the next part.*......