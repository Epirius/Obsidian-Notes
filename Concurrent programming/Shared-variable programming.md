- shared variables can be thought of as global variables
- shared variables are a means of communication between processes
- synchronization
	- mutual exclusion: two processes need to take turn when accessing shared objects
	- condition synchronization: one process needs to wait for another process

## Shared memory concurrency

important because:
- matches common hardware
- supported by mainstream languages
- even one-core machine

basic properties:
- each tread executes its own sequence of operations
- system decides which thread gets a turn to execute, for how long, and on which core
	- programmer may block threads, but not force them to execute.