# How programs run: challenge answers

## Questions 31–40: Running `python app.py`

### 31. Who receives the command?

The shell or terminal application receives the text you type. It parses the command and asks the operating system to launch the requested executable with `app.py` as an argument.

### 32. How does the operating system know where Python is?

The shell searches configured locations, often directories in the `PATH` environment variable, or uses an explicit executable path. On Windows, command lookup can also use mechanisms such as executable extensions and application aliases. The operating system then loads the selected program.

### 33. What is a process?

A process is a running program instance managed by the operating system. It has its own execution state, virtual address space, permissions, and resources such as open files. The same program can be started as multiple processes.

### 34. What is a thread?

A thread is an execution path scheduled by the operating system. A process has at least one thread; multiple threads in a process can share memory and resources. Shared access is useful but requires coordination to prevent race conditions.

### 35. Where does the Python interpreter run?

The interpreter is itself a program running as a process on the operating system. Its machine instructions execute on the processor. It reads Python code and coordinates its execution with operating-system services.

### 36. How does Python read your `.py` file?

The interpreter locates and opens the file, decodes its text, parses it according to Python's grammar, and compiles it to an internal code representation such as bytecode. It then executes that representation. Exact steps can vary by implementation and version.

### 37. Does Python directly understand your source code?

Python's language implementation understands the source by parsing and processing it; the processor does not execute Python syntax directly. The interpreter translates language constructs into operations its runtime can perform.

### 38. What is bytecode?

Bytecode is an instruction format for a virtual machine or runtime, rather than a processor's native machine code. CPython commonly compiles Python source into bytecode instructions. Bytecode is an implementation detail and is not guaranteed to be identical across Python versions or implementations.

### 39. What is the Python Virtual Machine?

The Python Virtual Machine is the execution engine that interprets CPython bytecode. It is software running inside the Python interpreter process, not a physical computer. Other Python implementations may execute programs differently.

### 40. What happens when the program crashes?

A crash may be a handled exception, an unhandled exception that ends the process, or a lower-level failure such as a segmentation fault. The runtime may print diagnostic information; the operating system reclaims process resources when it exits. Applications should log useful context and save important work safely.

## Follow the trail

Read about [compilers](./compiler.md), [interpreters](./interpreter.md), [processes](./process.md), and [threads](./threads.md). For the full trip from command to output, see [what happens when you run code](../10-rabbit-holes/what-happens-when-you-run-code.md).
