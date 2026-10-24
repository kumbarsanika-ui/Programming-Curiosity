# Stack and heap

The stack and heap are common ways a program organizes memory while it runs. They are useful mental models, though the exact implementation varies by language and runtime.

## The call stack

When a function is called, the program needs to remember where to return and what local information the function needs. A stack keeps these active function calls in order: the most recent call is handled first. When a function returns, its call record is removed.

This structure makes ordinary function calls efficient. Extremely deep or endless recursion can use too much stack space, causing a stack overflow.

## The heap

The heap is an area used for data that needs a more flexible lifetime or size than a single function call. Objects and collections are often stored there. A program can keep using such data after the function that created it has returned, as long as a reference to it remains.

## A mental picture

Think of a function call as a temporary desk: its notes are put away when the task is done. A shared project item is more like something kept in a common storeroom and used by several tasks. This analogy is imperfect, but it helps distinguish short-lived call data from longer-lived objects.

Languages differ: some require programmers to manage memory explicitly, while others use reference counting, garbage collection, or other techniques. See [Garbage collection](./garbage-collection.md).
