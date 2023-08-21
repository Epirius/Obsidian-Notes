in concurrent programming, the idea of lock-free is that no thread can block another thread from executing tasks.
it does not guarantee that another task will progress on its task, only that it will not be blocked.

specifically it refers to not using locks / mutex.

#concurrency
