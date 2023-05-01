---
title: "Operating System (Part - 3) Kernel"
seoTitle: "kernel"
datePublished: Mon May 01 2023 09:47:52 GMT+0000 (Coordinated Universal Time)
cuid: clh4nqdhw000808l3hpoq76hw
slug: operating-system-part-3-kernel
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/z508Zk08HNU/upload/e95ed9939845810b6a7df1398f43d82d.jpeg
tags: kernel, monolith, ipc

---

In the Operating system (Part - 1) in brief we discussed the different components of the os, from that kernel is one of the most important components of the os.

Let's understand the kernel, its function and its types -

**What is a Kernel?**

The kernel is the core component of an operating system. It is responsible for managing the system's resources, including the CPU, memory, and input/output devices such as disk drives, printers, and network interfaces. The kernel also provides a layer of abstraction between the hardware and software layers of the system, allowing applications to interact with the hardware without having to manage it directly.

The kernel typically provides a set of services, including process management, memory management, device drivers, and file system management. It is loaded into memory when the operating system boots up and remains in memory until the system is shut down.

Overall, the kernel plays a crucial role in ensuring the stability, security, and efficiency of an operating system by providing a common interface for applications to interact with the underlying hardware.

**GUI** and **CLI** applications run in the user space, which is where application software runs in an operating system.

The **user space** is distinct from the kernel space, which is where the operating system kernel and its associated services run. GUI and CLI applications do not have privileged access to the underlying hardware and interact with the kernel through system calls, which are requests for services or resources provided by the kernel.

GUI applications (such as web browsers, media players, and office software) typically provide a graphical user interface for interacting with the user and accessing system resources. CLI applications (such as command-line utilities and scripting languages) typically provide a command-line interface for interacting with the user and automating system tasks. Both types of applications rely on the kernel for managing system resources and providing services such as file I/O, networking, and process management.

The shell is a command-line interface (CLI) that allows users to interact with the operating system by typing commands, rather than using a graphical user interface (GUI).

**Let's now see the function of the kernel**:-

<table><tbody><tr><td colspan="1" rowspan="1"><p><strong>Function</strong></p></td><td colspan="1" rowspan="1"><p><strong>Description</strong></p></td></tr><tr><td colspan="1" rowspan="1"><p>Process management</p></td><td colspan="1" rowspan="1"><p>Scheduling processes and threads on the CPUs, creating &amp; deleting both user and system processes, suspending and resuming processes, providing mechanisms for process synchronization or process communication.</p></td></tr><tr><td colspan="1" rowspan="1"><p>Memory management</p></td><td colspan="1" rowspan="1"><p>Allocating and deallocating memory space as per need, keeping track of which part of memory is currently being used and by which process.</p></td></tr><tr><td colspan="1" rowspan="1"><p>File management</p></td><td colspan="1" rowspan="1"><p>Creating and deleting files, creating and deleting directories to organize files, mapping files into secondary storage, and backup support onto a stable storage media.</p></td></tr><tr><td colspan="1" rowspan="1"><p>I/O management</p></td><td colspan="1" rowspan="1"><p>Manage and control I/O operations and I/O devices, buffering (data copy between two devices), caching and spooling.<br>- Spooling Managing output to devices that operate at different speeds<br>- Buffering Temporary storage of data to improve I/O performance within a single job<br>- Caching Temporary storage of frequently accessed data to improve performance, such as memory caching and web caching</p></td></tr></tbody></table>

**Now let's see the different types of kernels and their advantages, disadvantages and some os which are having those types of kernel**

| Kernel Type | Description | Advantages | Disadvantages | Examples |
| --- | --- | --- | --- | --- |
| Monolithic | All functions are in the kernel itself. | High performance, fast communication. | Bulky in size, and less reliable. | Linux, Unix, MS-DOS |
| Micro | Only major functions are in the kernel. File and IO management are in user space. | More reliable, more stable. | Performance is slow, and overhead switching between user mode and kernel mode. | L4 Linux, Symbian OS, MINIX |
| Hybrid | The combined approach of monolithic and microkernels. | Speed and design of monolithic kernel, modularity and stability of microkernel. | None identified. | MacOS, Windows NT/7/10 |
| Nano/Exo | Extremely small size, with only essential features. | High reliability, high security. | Limited functionality, and lack of compatibility with some hardware. | EKA2 (Symbian OS), Fiasco.OC, uC/Kernel |

**One of the most asked questions in an interview is**

**How will communication happen between the user mode and kernel mode?**

Communication between user mode and kernel mode is typically achieved through inter-process communication (IPC). IPC enables two processes running independently with separate memory spaces to communicate with each other.

There are two primary methods of IPC:

1. Shared memory: In this method, a shared memory region is created that can be accessed by both the user process and the kernel. Both the user process and kernel can read and write to this memory region, enabling communication between them.
    
2. Message passing: In this method, messages are sent between the user process and kernel through a message-passing mechanism. The user process sends a message to the kernel, which then processes the message and sends a response back to the user process. This is a slower method than shared memory, but it is more secure as it prevents direct access to the kernel's memory.