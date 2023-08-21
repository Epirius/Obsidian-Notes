[[Concurrent programming]] is when we have multiple logical threads of control. 

[[Parallel programming]] is when we have one logical thread but split it up to multiple hardware resources. 

concurrency gives the impression that threads are running in parallel (but it is only an impression).
In actuality you will need to suspend one thread temporarily to work on another thread before switching back.

parallel programming literally executes multiple tasks at the same time, but on different cpu cores. this is done to speed up the computing of a task.

all parallel programs are concurrent *but not all concurrent programs are parallel*.