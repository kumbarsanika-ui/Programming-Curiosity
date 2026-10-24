# Threads

A thread is a sequence of instructions that the operating system can schedule to run. A process has at least one thread; some processes use multiple threads to make progress on more than one task.

## Concurrency and parallelism

Concurrency means multiple tasks make progress during overlapping periods. A single processor core can switch between tasks, creating the appearance of simultaneous progress. Parallelism means tasks actually run at the same time on different cores or processors.

Threads are one way to organize concurrent work. A program might use one thread to handle a user interface while another performs background work. Modern applications may also use asynchronous operations, processes, or task schedulers instead.

## Shared data needs care

Threads in the same process can often access the same memory. This is useful, but if two threads change shared data at the same time, the result may depend on timing. Such bugs are called race conditions.

Programs use techniques such as locks, message passing, and thread-safe data structures to coordinate work. Coordination can introduce its own problems, including deadlocks, where tasks wait indefinitely for one another.

## The key idea

Threads can help a program stay responsive or use multiple processor cores, but adding them also makes behavior harder to reason about. Use concurrency where it solves a real need and choose clear ways to coordinate shared state.
