in concurrent programming, wait-free refers to the guarantee that a task in any given thread will progress.
it is a stronger guarantee then [[Lock-Free]] which only guarantees that a thread will not be blocked by another thread.

so in wait-free, if a thread is not progressing, another thread will eventually pause its own operation and come and help the stalled thread.

#concurrency 