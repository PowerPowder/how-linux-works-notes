## Chapter 1 - The Big Picture
A linux system is abstracted to 3 layers (highest to lowest):
* **User processes** - GUI, servers, shell, web browsers
* **Linux kernel** - System calls, Process management, memory management, device drivers
* **Hardware** - CPU, RAM, Disks, Network Ports

Code that runs in `kernel mode` has unrestricted access to the CPU and memory of the system.
Where as in `user mode`, processes only have access to a small subset of memory and safe CPU operations.

A `memory state` is just an arrangement of bits with a certain bit field.

The kernel divides up the system memory and distributes it among user processes, it ensures that each process doesn't exceed it's share.

The kernel manages different four systems:
* **Processor** - decides which processes are allowed to use the CPU
* **Memory** - keeps track of the memory in use, shared and unused by all processes.
* **Device drivers** - interfaces between the hardware and the processes.
* **System calls and support** - for a process to talk to the hardware, it must make a system call to the kernel.
