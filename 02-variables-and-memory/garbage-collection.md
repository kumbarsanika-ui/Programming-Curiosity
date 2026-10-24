# Garbage collection

Garbage collection is automatic memory management. A runtime identifies objects that a program can no longer reach and reclaims the memory they occupy so it can be reused.

## Reachability

Suppose a variable refers to a list, and the list refers to several objects. Those objects are reachable while the program can follow references to them from active variables or other live data. If every path to an object disappears, the runtime may treat it as garbage.

The exact rules vary. Some languages use tracing collectors that periodically find reachable objects; others use reference counts, sometimes combined with additional techniques. Collection timing is generally controlled by the runtime, not by a guarantee that memory is reclaimed at a specific instant.

## What garbage collection helps with

It reduces the need for programmers to manually free every object and can prevent many memory-management mistakes. It does not prevent every memory problem. A program can accidentally keep references to data it no longer needs, causing memory use to grow. This is often called a memory leak, even though a collector is present.

Garbage collection can also take processing time. Runtime systems work to limit pauses and overhead, but the trade-off depends on the application.

## Not the same as closing resources

Memory cleanup is different from closing a file, releasing a network connection, or ending a database transaction. Those resources should be managed explicitly using the language's recommended patterns, such as context managers or `try/finally` blocks.
