- most busy-waiting protocols are rather complex
	- no clear distinction between variables that are used for synchronization vs those used for doing the actual computations.
- semaphores is a disciplined way to implement signaling and scheduling
- semaphores are supported that almost all libraries that deal with concurrency

- analog from railroad traffic
	- samaphores indicates whether the track ahead is clear of occupied by another train
	- as a train proceeds, semaphores are set and cleared
	- the remain set long enough to give another train some time to stop, if necessary 
	- railroad semaphores: a mechanism to signal conditions in order to ensure mutually exclusive occupancy of critical sections of track

- semaphores in concurrent programming: provide a basic signaling mechanism and are used to implement mutual exclusion and condition synchronization

--------

- a semaphore is a special kind of shared variable
- can only be manipulated by two atomic operations
	- p
	- v
- value of a semaphore: a non-negative integer
	- default value is 0
- operation V: to signal the occurrence of an event
	- it increments the value of the semaphore
- operation P: to delay a process until an event has occurred
	- it waits until the value of a semaphore is positive and then decrements the value
		- this is where the power of semaphores is

