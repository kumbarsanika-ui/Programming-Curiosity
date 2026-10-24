# How code runs

Source code is not usually executed directly as written. A chain of software tools turns it into instructions the computer can run, starts those instructions, and provides access to resources such as memory, files, and the network.

## A simplified journey

1. A programmer writes source code and saves it in files.
2. A language tool checks or translates the code. A compiler may produce machine code or an intermediate form; an interpreter may execute instructions while the program runs.
3. The operating system starts the program and gives it resources.
4. The processor carries out low-level instructions, while the program reads input, changes data, and produces output.

Real systems often add steps such as downloading libraries, packaging files, or running a virtual machine. See [Compiler](../03-how-programs-run/compiler.md), [Interpreter](../03-how-programs-run/interpreter.md), and [Process](../03-how-programs-run/process.md).

## Input, work, output

A useful way to think about any program is:

**input -> processing -> output**

A calculator receives numbers and an operation, computes a result, and displays it. A web application receives a request, applies rules and perhaps queries a database, then sends a response. Some programs also keep running and respond to new inputs over time.

## Errors can happen at different stages

The source might contain a syntax error that a language tool catches before execution. A running program might encounter an invalid input or missing file. The operating system or a remote service might also fail. Clear error messages help distinguish these situations.

## The key idea

Running code involves both the language runtime and the operating system. The source describes the work; tools prepare it, and the machine and operating system provide the environment in which it happens.
