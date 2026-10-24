# Variables and memory: challenge answers

Memory details depend on the programming language and its implementation. Python examples below describe the usual behavior of CPython where relevant; other implementations can differ.

## Questions 11–20: Your first line of code

### 11. What happens internally when you write `x = 10`?

The program evaluates the expression `10` and binds the name `x` to the resulting value in the current scope. In Python, integers are objects and names refer to objects; assignment is not a command to reserve a permanently named hardware location.

### 12. Where is `10` stored?

While the program runs, the value is represented in the process's memory. In CPython an integer is an object managed by the runtime. Its exact address and representation are implementation details and can vary between runs.

### 13. Where is `x` stored?

`x` is a name in a scope, such as a function's local namespace or a module's global namespace. The runtime maintains the association between that name and its value; it is not necessarily a fixed memory cell labeled `x`.

### 14. Is `x` actually the value `10`?

In Python, `x` is a name bound to an integer object whose value is 10. This distinction becomes important for mutable objects: multiple names can refer to the same object.

### 15. What happens when you write `x = 10` and then `x = 20`?

The second assignment rebinds `x` to the value 20. It does not change the integer object 10 into 20. A different name that still refers to 10 remains unaffected.

### 16. What happens to `10`?

If no name or other live reference points to the object, it becomes eligible for cleanup. In CPython reference counting often reclaims an unreferenced object promptly, but object reuse, implementation details, and other references can affect what happens and when.

### 17. What happens when you write `a = b = c = 100`?

Python evaluates the right-hand expression and assigns its result to each target name. All three names become bound to the same resulting object at that moment.

### 18. Are `a`, `b`, and `c` three copies of `100`?

Not necessarily. In Python, they can all refer to the same integer object. Integers are immutable, so sharing is safe: an operation that appears to change a number creates or obtains another value and rebinds a name rather than mutating that integer.

### 19. What happens to variables when a function finishes?

The function's local scope stops being active when it returns. Objects referenced only by that scope may then become eligible for reclamation. An object survives if another live reference exists, for example if the function returned it or stored it somewhere reachable.

### 20. Who cleans unused memory?

The language runtime and operating system have different roles. A garbage collector or reference-counting runtime can reclaim objects inside a process; the operating system manages the process's overall memory pages and resources. Languages with manual memory management put more cleanup responsibility on the programmer.

## Questions 21–30: Memory, the hidden world

### 21. What is RAM actually doing while your program runs?

RAM holds the program's currently needed instructions and data so the processor can access them quickly. The operating system gives each process a virtual address space and maps parts of it to physical memory as needed.

### 22. What is the difference between RAM and storage?

RAM is fast working memory and is normally volatile: its contents are lost when power is removed. Storage such as an SSD is intended to retain files and data across restarts, but is generally slower than RAM. Programs load needed data from storage into memory.

### 23. Where does a Python variable live?

It depends on the kind of name and runtime implementation. A local name may be held in a function's execution state, while module names live in a module namespace; the referenced object is separately managed in the process's memory. “The variable” is therefore not always one physical location.

### 24. What is a memory address?

A memory address identifies a location in an address space. Programs and operating systems use addresses to find instructions and data. Modern processes usually see virtual addresses, which the operating system and hardware translate to physical memory.

### 25. Why can’t we normally see memory addresses in Python?

Python is designed to let programmers work with objects and names without managing raw addresses. An implementation may expose identity-related information for debugging, but it is not a portable physical address and should not be relied on for program logic.

### 26. What is a stack?

A call stack tracks active function calls and their execution state. Calling a function adds a frame; returning removes it. It supports nested calls efficiently, but excessive recursion can exhaust available stack space.

### 27. What is a heap?

The heap is a common term for memory used for dynamically managed data whose lifetime does not necessarily match a single function call. Runtimes manage objects there. Stack and heap are useful concepts, but exact layouts depend on implementation.

### 28. What is garbage collection?

Garbage collection is automatic reclamation of objects that a program can no longer reach. Runtimes use techniques such as tracing, reference counting, or combinations. It reduces manual memory work, but does not automatically close every file or network resource.

### 29. Why doesn’t unused memory remain forever?

Runtimes and operating systems reclaim resources so they can be reused. However, memory reclamation is not always immediate, and a process can accidentally keep objects reachable. The operating system can reclaim a process's memory when that process exits.

### 30. What happens when your program consumes too much memory?

The operating system may reclaim cache, use virtual memory, slow the machine, or refuse further allocation. An allocation can fail; the runtime may raise an exception, or the operating system may terminate the process. The exact outcome depends on the operating system, limits, and language.

## Follow the trail

Read [variables](./variables.md), [memory](./memory.md), [stack and heap](./stack-and-heap.md), and [garbage collection](./garbage-collection.md).
