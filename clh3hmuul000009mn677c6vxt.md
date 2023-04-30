---
title: "Operating System (Part - 1)"
seoTitle: "operating-system-part-1"
seoDescription: "operating-system-part-1"
datePublished: Sun Apr 30 2023 14:09:24 GMT+0000 (Coordinated Universal Time)
cuid: clh3hmuul000009mn677c6vxt
slug: operating-system-part-1
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/z508Zk08HNU/upload/b4a9a79343fef3b034cfe24d7e0ae8be.jpeg
tags: operating-system, kernel

---

**What is an Operating System?**

We know how our computer needs to have software to run, right? Well, one of the most important pieces of software it needs is called an operating system. We can refer to it as the boss of the computer - it manages all the hardware and software resources so that everything can work together smoothly.

The operating system does all sorts of things to make sure the computer runs smoothly, like managing memory and processing power, coordinating input/output operations, and controlling network connections and other devices that you plug into your computer. Basically, it's the glue that holds everything together.

Overall, an operating system is a complex software system that is made up of multiple components working together to manage and control the resources of a computer system. Some of those components are:-

1. **Kernel**: This is the core component of the OS that manages the computer's hardware resources, such as memory, CPU, and input/output operations.
    
2. **Device drivers**: These are software programs that allow the OS to communicate with and control hardware devices, such as printers, scanners, and network adapters.
    
3. **User interface**: This is the graphical interface that allows users to interact with the computer, launch applications, open files, and perform other tasks.
    
4. **File system**: This is the system that manages the organization and storage of files and directories on the computer's storage devices, such as hard drives and flash drives.
    
5. **Utilities**: These are tools and applications that perform specific functions, such as backup and recovery, system maintenance, and performance optimization.
    
6. **Security features**: These are components that protect against unauthorized access, viruses, malware, and other security threats.
    

**What will happen if there is no OS?**

* **Bulky and complex application code**: The hardware interaction code must be included in the application's code base, making it more complex and difficult to manage.
    
* **Resource exploitation by one application**: Without an operating system, one application could potentially use up all of the computer's resources, leaving no resources for other applications to use.
    
* **No memory protection**: An operating system provides memory protection, which prevents one application from accessing or modifying the memory of another application. Without an OS, applications could interfere with each other's memory space, potentially causing crashes or other errors.
    

**So some key functions of OS are**: -

1. **Access to computer hardware**: An operating system serves as an interface between the user and the computer hardware, allowing users to interact with the system and perform tasks.
    
2. **Resource management**: An OS manages computer resources, such as memory, devices, files, security, and processes, by allocating and sharing resources among multiple applications.
    
3. **Hides hardware complexity**: An operating system hides the underlying complexity of computer hardware, providing a simpler and more standardized interface for applications to interact with the hardware.
    
4. **Abstraction**: OS provides an abstraction to the underlying hardware, allowing applications to be written in a higher-level language and be independent of specific hardware configurations.
    
5. **Isolation and protection**: An OS facilitates the execution of application programs by providing isolation and protection, preventing one application from interfering with another application's memory space or accessing hardware that is being used by another application.
    

**Some of the goals of OS?**

1. **Maximum CPU utilization**: The OS should aim to keep the CPU busy as much as possible by scheduling processes efficiently and effectively.
    
2. **Less process starvation**: The OS should avoid process starvation, which occurs when a process is not given enough CPU time to execute.
    
3. **Higher-priority job execution**: The OS should prioritize processes based on their importance and ensure that high-priority jobs are executed in a timely manner.
    
4. **Fairness**: The OS should ensure that all processes get a fair share of CPU time, preventing any single process from monopolizing the CPU and slowing down other processes.
    
5. **Responsiveness**: The OS should ensure that interactive processes, such as those used by users, are given higher priority and respond quickly to user input.
    
6. **Throughput**: The OS should aim to maximize throughput, which is the number of processes that can be completed in a given amount of time.
    

**Let us see how many types of os are there along with their advantages and disadvantages, and the reason why the next OS had to be developed:**

1. **Single process operating system**:
    
    * As the name this type of OS allows only one program to run at a time.
        
        Examples of single-process operating systems include MS-DOS and early versions of Mac OS.
        
    * Advantage: It is simple and easy to use, with no overhead.
        
    * Disadvantage: It is inefficient and does not make use of the available system resources.
        
    * Reason for development: As computer technology advanced and the need for efficient resource utilization grew, single-process operating systems became obsolete.
        
2. **Batch-processing operating system**:
    
    * This type of OS allows users to submit jobs as a batch, which are then processed in sequence.
        
        Examples - IBM OS/360 and UNIVAC EXEC 8.
        
    * Advantage: It is more efficient than a single-process operating system, as it allows for the processing of multiple jobs at once.
        
    * Disadvantage: It is still inefficient as it requires users to wait for the entire batch to complete before receiving the output.
        
    * Reason for development: As the need for faster and more responsive computing grew, batch-processing operating systems became inadequate.
        
3. **Multiprogramming operating system**:
    
    * This type of operating system allows multiple programs to run simultaneously by dividing the CPU time between them.
        
        Examples - IBM OS/360 and UNIX.
        
    * Advantage: It improves system efficiency by allowing for the concurrent execution of multiple jobs.
        
    * Disadvantage: It does not provide protection between processes, making the system vulnerable to crashes and errors.
        
    * Reason for development: As the need for better resource management and protection grew, multiprogramming operating systems were developed.
        
4. **Multitasking operating system**:
    
    * This type of operating system can run multiple tasks or processes concurrently.
        
        Examples of multitasking operating systems include Windows, Linux, and Mac OS X.
        
    * Advantage: It provides better responsiveness and interactivity by allowing users to switch between tasks seamlessly.
        
    * Disadvantage: It can be complex to implement and manage, requiring careful resource allocation and scheduling.
        
    * Reason for development: As the need for more responsive and interactive computing grew, multitasking operating systems were developed.
        
5. **Multi-processing operating system**:
    
    * This type of operating system can run multiple processes on multiple processors or cores.
        
        Examples - Windows NT, UNIX.
        
    * Advantage: It provides increased processing power and faster execution of tasks.
        
    * Disadvantage: It can be difficult to program and manage, requiring careful coordination and synchronization between processors.
        
    * Reason for development: As the need for more processing power and faster execution of tasks grew, multi-processing operating systems were developed.
        
6. **Distributed system**:
    
    * This type of OS allows multiple computers to work together as a single system, with tasks and resources distributed across the network.
        
        Examples - Google's GFS, Hadoop, and Apache Spark.
        
    * Advantage: It provides improved scalability and reliability, as tasks can be distributed across multiple systems.
        
    * Disadvantage: It can be complex to manage and coordinate, requiring careful communication and synchronization between nodes.
        
    * Reason for development: As the need for more scalable and reliable computing grew, distributed systems were developed.
        
7. **Real-time OS**:
    
    * This type of OS is designed for applications that require precise timing and response, such as in robotics and aerospace.
        
        Examples - QNX, VxWorks.
        
    * Advantage: It provides precise control over system timing and response, ensuring that critical tasks are executed on time.
        
    * Disadvantage: It can be limited in functionality and may not be suitable for general-purpose computing.
        
    * Reason for development: As the need for precise timing and control in specialized applications grew, real-time operating systems were developed.
        

**In the end, let's see some real-world examples where these os are used**

1. **Single process operating system**: This type of OS is used in devices that have a single dedicated function, such as calculators, digital watches, and microwave ovens.
    
2. **Batch-processing operating system**: This type of OS is used in industries where large volumes of data need to be processed in batches, such as payroll processing, bank statement processing, and billing systems.
    
3. **Multiprogramming operating system**: This type of OS is used in general-purpose computing systems where multiple programs are executed simultaneously, such as desktop computers, laptops, and servers.
    
4. **Multitasking operating system**: This type of OS is used in devices that require multiple applications to be executed simultaneously, such as smartphones, tablets, and personal computers.
    
5. **Multi-processing operating system**: This type of OS is used in systems that have multiple processors, such as high-end servers, supercomputers, and scientific research applications.
    
6. **Distributed system**: This type of OS is used in systems that have multiple interconnected computers that work together to achieve a common goal, such as cloud computing, distributed databases, and peer-to-peer networks.
    
7. **Real-time OS**: This type of OS is used in systems that require immediate response and precise timing, such as aerospace, defense, and industrial control systems. Examples include VxWorks, QNX, and RTLinux.
    

*tune in for the next part.*......