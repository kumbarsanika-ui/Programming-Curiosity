# Interpreter

An interpreter is software that executes a program by reading its instructions or a representation of them. It may process source code directly, or it may first translate code into an intermediate form such as bytecode.

## How it differs from ahead-of-time compilation

With ahead-of-time compilation, a compiler translates code before the program is run, often creating a separate executable. With interpretation, some work happens as the program runs. In practice, many language systems combine both methods.

For instance, a Python implementation commonly compiles source into bytecode and then runs it in a virtual machine. JavaScript engines may interpret code initially and compile frequently used parts to machine code for speed. So it is more accurate to talk about a language implementation than to label an entire language simply “interpreted” or “compiled.”

## What a runtime provides

The runtime may manage values, check certain errors, load libraries, and provide services such as memory management. It does not replace the operating system: programs still depend on the operating system for processes, files, networking, and other resources.

## Trade-offs

Interpretation can make interactive use and portability convenient, but run-time translation may have a cost. Compilation can catch certain errors earlier and produce fast machine code, but builds may take time and output can depend on the target platform. Modern implementations often narrow these differences.
