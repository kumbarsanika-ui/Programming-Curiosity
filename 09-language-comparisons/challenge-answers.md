# Language comparisons: challenge answers

## Questions 91–100: Comparing languages

### 91. Why is Python popular for AI?

Python has readable syntax and a large ecosystem for data processing, scientific computing, and machine learning. Many demanding numerical operations run in optimized native libraries, so performance is not determined by Python code alone. Popularity also attracts tools, documentation, and community support.

### 92. Why is JavaScript used in browsers?

Browsers include JavaScript engines and browser APIs that let scripts respond to user actions, update pages, and communicate with web services. This built-in support made JavaScript the standard scripting language of the web platform.

### 93. Why is Node.js able to run JavaScript on servers?

Node.js packages a JavaScript engine with server-side APIs for files, networking, and other operations. It uses an event-driven runtime well suited to many I/O-heavy services. It is a separate environment from the browser, even though both can execute JavaScript.

### 94. Why is Java still heavily used in enterprise applications?

Java offers a mature ecosystem, stable runtimes, strong tooling, broad library support, and a large pool of experienced developers. The JVM supports long-lived services and many frameworks. Existing systems and organizational investment also influence language choice.

### 95. Why is C still important?

C provides relatively direct control over memory and hardware while remaining portable across many systems. It is widely used in operating systems, embedded software, runtimes, and libraries. Its power comes with responsibility: programmers must carefully manage memory and avoid undefined behavior.

### 96. Why is Rust becoming popular?

Rust aims to provide low-level performance while preventing many memory-safety errors through compile-time ownership and borrowing rules, without relying on a garbage collector. It can be challenging to learn, and adoption depends on ecosystem fit, team skills, and project requirements.

### 97. Is Python actually slower than Java?

For many CPU-bound pure-language tasks, CPython is slower than optimized Java running on a mature JVM. But performance depends on workload, implementation, libraries, I/O, and optimization. Python can call fast native libraries, and a poorly designed Java program can still be slow. Measure the real application.

### 98. Does a “faster language” always mean a “better language”?

No. Runtime speed is one factor among development time, correctness, security, maintainability, available libraries, hiring, and operating costs. Choose a language that satisfies the project's measurable needs; optimize bottlenecks only after measuring them.

### 99. Can Python call code written in C?

Yes. Python can use C extensions, foreign-function interfaces, or libraries that expose a C-compatible interface. This is common for performance-sensitive libraries. The boundary requires compatible data representations and careful handling of memory, errors, and platform differences.

### 100. Can different programming languages communicate with each other?

Yes. Programs can communicate through shared protocols and formats such as HTTP with JSON, message queues, files, databases, or language interoperability interfaces. A network protocol does not require both programs to use the same language; each side implements the same contract.

## Follow the trail

Compare [Python](./python.md), [JavaScript](./javascript.md), and [Java](./java.md), then read the [side-by-side comparison](./python-vs-javascript-vs-java.md).
