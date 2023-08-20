in concurrent programming, wait-free refers to the guarantee that a task will progress.
it is a stronger guarantee then [[Lock-Free]] which only guarantees that a thread will not be blocked by another thread.

so in wait-free, if a thread is not progressing, another thread will do some of its task before doing its own task.

#concurrency 