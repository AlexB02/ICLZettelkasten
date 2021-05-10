### What is a Data Race?
A data race occurs in [[Concurrent]] programs, causing the order of shared variable access to be non-determanistic.

A data race occurs when:
- When two or more [[Thread]]s attempt to access the same location [[Concurrent|Concurrently]].
- At least one thread is accessing for write.
- The threads are not using any exclusive [[Locking|Lock]]s to control access to the memory.

#C40009 