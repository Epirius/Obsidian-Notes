when two threads use a variable in java, each thread has its own cpu cache that it reads from and write to. so there is the possibility that the cpu cache and the main memory are out of sync. therefore thread 2 might not be able to read the latest value, because it is only updated at thread 1's cpu cache.

volatile variables force the thread to write straight to the shared main memory instead of to the cache

this will not prevent race conditions if you have multiple threads writing to the same variable. it only works when you have one writer and multiple readers.

## Volatile visibility guarantee
- visibility guarantee goes beyond the volatile variable itself
- if thread a writes to a volatile variable, and thread b subsequently reads the same variable, then all variables visible to thread a before writing the volatile variable will also be visible to thread b after it has read the variable
- so the volatile keywords can infect other variables




#os
#concurrency 