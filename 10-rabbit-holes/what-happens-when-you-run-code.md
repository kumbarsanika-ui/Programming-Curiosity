# What happens when you run code?

Pressing “run” starts a chain of work involving your development tools, a language runtime, the operating system, and the processor. The precise steps depend on the language and setup, but this tour shows a common shape.

## From editor to running program

1. You write source code and ask an editor, command-line tool, or build system to run it.
2. The tool checks the project and may compile source into an executable or intermediate form. It can also load dependencies.
3. The operating system creates a [process](../03-how-programs-run/process.md), gives it resources, and starts one or more threads.
4. A language runtime may load libraries, prepare code, and manage values and memory.
5. The processor executes instructions. The program may read input, access files or the network, and produce output.
6. The program exits, or keeps running while it waits for more work.

## Why it sometimes fails

A syntax error may stop a tool from preparing the program. A missing dependency may prevent it from starting. A bug can cause a run-time exception, and a permission or network problem can stop access to an external resource.

Looking at the first clear error message often reveals which stage failed. Check that the command, working directory, dependencies, and required configuration match the project's instructions.

## Follow the concepts

Learn how [code runs](../01-programming-basics/how-code-runs.md), what [compilers](../03-how-programs-run/compiler.md) and [interpreters](../03-how-programs-run/interpreter.md) do, and how the [stack and heap](../02-variables-and-memory/stack-and-heap.md) organize data.
