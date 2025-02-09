# Linux Internals

## Questions Check
- What is the Linux kernel ?  is it `monolithic` or `microkernel` ? What is the difference between the two ?
- What is `struct task_struct` ? Whats the difference between `process` and `thread` ?  What is the difference between `fork` and `exec` ?
- What is **Page Table Entry (PTE)** ? What is the difference between `virtual address` and `physical address` ?
- What is **inode** ? What is the difference between `inode` and `file descriptor` ?
- What is **spinlock** ? What is the difference between `spinlock` and `mutex` ? 
- What is **file system superblock** ? What is the difference between `block device` and `character device` ?
- What is **device driver** ? What is the difference between `device driver` and `kernel module` ?
- What is **system call** ? What is the difference between `user space` and `kernel space` ?
- What is **ioctl** ? What is the difference between `ioctl` and `read/write` ?
- What is **interrupt** ? What is the difference between `hardware interrupt` and `software interrupt` ?
- What is **kmalloc** ? What is the difference between `kmalloc` and `vmalloc` ?

## References
- Linux Kernel Documentation: https://www.kernel.org/doc/html/latest/
- Linux Kernel Teaching:https://linux-kernel-labs.github.io/refs/heads/master/index.html
- Linux Performance tools: https://www.brendangregg.com/linuxperf.html

## Linux Kernel

### Linux Kernel Architecture
The Linux kernel is a monolithic kernel, which means that it includes all the necessary components to manage hardware
and system resources in a single executable file. The kernel is responsible for managing system resources, including
memory, processes, and devices.


### Linux Kernel Modules
Kernel modules are pieces of code that can be loaded and unloaded into the kernel at runtime. They allow for dynamic
configuration of the kernel and can be used to add new functionality or support for new hardware without having to
recompile the entire kernel. Kernel modules are typically written in C and can be loaded and unloaded using the `insmod`
and `rmmod` commands.

### Linux Kernel Data Structures
The Linux kernel uses a variety of data structures to manage system resources. Some of the most important data structures
include:
- Process Control Block (PCB): A data structure that contains information about a process, including its state, priority, and memory usage.
- File Descriptor Table: A data structure that maps file descriptors to open files.
- Inode: A data structure that contains information about a file, including its location on disk and its permissions.
- Page Table: A data structure that maps virtual memory addresses to physical memory addresses.
- Task Structure: A data structure that contains information about a process, including its state, priority, and memory usage.
- File System Superblock: A data structure that contains information about a file system, including its size, block size, and location on disk.
- Memory Descriptor Table: A data structure that contains information about a process's memory usage, including its virtual memory map and page tables.
- Socket Buffer: A data structure that is used to manage network packets in the Linux kernel.
- Tasklet: A lightweight mechanism for handling interrupts in the Linux kernel.

### Linux Kernel System Calls
System calls are the primary interface between user space and kernel space in Linux. They allow user-space programs to
request services from the kernel, such as file I/O, process management, and network communication. Some of the most
common system calls in Linux include:
- `open()`: Opens a file and returns a file descriptor.
- `read()`: Reads data from a file descriptor.
- `write()`: Writes data to a file descriptor.
- `close()`: Closes a file descriptor.
- `fork()`: Creates a new process.
- `exec()`: Replaces the current process with a new process.
- `wait()`: Waits for a child process to terminate.
- `kill()`: Sends a signal to a process.
- `socket()`: Creates a new socket.

### Linux Kernel Scheduling
The Linux kernel uses a preemptive, priority-based scheduling algorithm to manage processes. Each process is assigned a
priority, and the kernel selects the highest-priority process to run next. The kernel also supports real-time scheduling
policies, which allow processes to be scheduled with higher priority than normal processes.

### Linux Kernel Memory Management
The Linux kernel uses a virtual memory system to manage memory. Each process is given its own virtual address space,
which is mapped to physical memory by the kernel. The kernel uses a page table to keep track of the mapping between virtual
and physical memory. The kernel also uses a variety of algorithms to manage memory, including paging, swapping, and
caching.

