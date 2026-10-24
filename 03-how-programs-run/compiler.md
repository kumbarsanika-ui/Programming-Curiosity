# Compiler

A compiler translates source code into another form so it can be run. Depending on the language and toolchain, the output might be machine code for a processor, bytecode for a virtual machine, or another intermediate representation.

## Common steps

A compiler typically checks that the code follows the language's rules, analyzes its meaning, and produces output. Some compilers also optimize the result, aiming to make it faster or smaller while preserving its behavior. A build tool may coordinate compilation with libraries and other project files.

For example, a C compiler can produce a native executable for a particular operating system and processor. Java tools commonly compile source into bytecode that runs on a Java Virtual Machine (JVM).

## Compile time and run time

Compile-time errors are found during translation, such as a missing punctuation mark or a type mismatch caught by the compiler. Run-time errors occur while the program is executing, such as trying to open a file that does not exist.

Compilation does not prove that a program's logic is correct. A program can compile successfully and still produce the wrong result.

## A useful nuance

Compilation and interpretation are not strict opposites. Some systems compile code just before or during execution, and others combine compiled and interpreted steps. These approaches are explained further in [Interpreter](./interpreter.md) and [How code runs](../01-programming-basics/how-code-runs.md).
