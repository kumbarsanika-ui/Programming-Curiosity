# Memory

Computer memory is working space that stores information a program needs while it runs. It holds values, instructions, and temporary results. Memory is much faster to access than long-term storage such as an SSD, but it is usually limited and its contents do not normally survive a power-off.

## Bits, bytes, and addresses

At the lowest level, memory stores bits: zeros and ones. A group of eight bits is a byte. Programs use many bytes to represent numbers, text, images, and other data. An address identifies a location in memory so the computer can find stored information.

The details of representation are usually handled by the programming language and operating system. A programmer normally works with values and data structures rather than manually locating each byte.

## Memory while a program runs

When a program is running, the operating system gives it an address space and resources. The program's runtime organizes its data; commonly this includes a call stack for active function calls and a heap for data whose lifetime or size is more flexible. The exact arrangement depends on the language and platform. Read [Stack and heap](./stack-and-heap.md).

## Memory is not permanent storage

If an application needs information to remain after it closes, it usually writes it to a file or database. That stored information can later be loaded back into memory. For example, a game may keep the current score in memory during play and save a checkpoint to disk.

## The key idea

Memory is the program's temporary working space. Understanding where values live and how long they are needed helps explain performance, bugs, and automatic cleanup.
