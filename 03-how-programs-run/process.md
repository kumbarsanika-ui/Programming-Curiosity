# Process

A process is a running instance of a program, together with the resources and state the operating system manages for it. Launching the same application twice can create two separate processes, each with its own execution state.

## What a process contains

A process typically has an address space for its memory, information about open files, security permissions, and one or more threads that execute instructions. The operating system schedules its threads to share processor time with other work.

Applications often use several processes. A web browser, for example, may separate tabs or services into different processes to improve isolation and reliability. The exact design depends on the application and operating system.

## Process versus program

A program is stored instructions; a process is those instructions in action. A recipe is not a meal, just as an executable file is not itself a running process.

## Starting and stopping

The operating system creates a process when asked to launch a program. A process can finish normally, report an error, or be stopped. Processes can communicate through operating-system mechanisms such as pipes, sockets, or shared memory; the choice depends on the task.

To connect this idea to concurrent work inside one process, see [Threads](./threads.md).
