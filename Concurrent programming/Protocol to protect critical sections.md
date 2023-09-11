
4 properties are needed to protect a [[critical section]]:
- mutual exclusion
	- at most one [[process]] at a time is executing its critical section
	- #safety-property bad state: two processes are in their critical section
- absence of deadlock
	- if two or more processes are trying to enter their critical sections, at least one will succeed
	- #safety-property bad state: all processes are waiting to enter the critical section, but none is able to do so
- absence of unnecessary delay
	- f a process is trying to enter its critical section and the other processes are executing their non-critical sections or have terminated, the first process is not prevented from entering its critical section
	- #safety-property bad state: one process that wants to enter the critical section, can not do so, even though no other process is in the critical section
- eventual entry
	- a process that is attempting to enter its critical section will eventually succeed
	- #liveness-property