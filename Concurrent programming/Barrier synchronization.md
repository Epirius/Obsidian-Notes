- iterative algorithms that successively compute better approximations to an answer
	- manipulate an array of values
	- each iteration performs the same computation on all array elements
	- that is: multiple processes compute disjoint parts of the solution in parallel
- each iteration typically depends on the result of the previous iteration
	- a way to structure such an algorithm: implement the body of each iteration using one or more threads. when all threads have done their jobs, synchronize and loop to the next iteration.

- the delay point at the end of each iteration represents a barrier that all processes have to arrive at before any are allowed to pass
- barriers can be needed both at the ends of loops and at intermediate stages


-----

# implementations:

### Shared counter
- assume there are n worker processes that need to meet at a barrier
- when a process arrives at the barrier, it increments **count**
- when **count** is **n**, all processes can proceed
- problems with this solution:
	- count must be 0 at the start of each iteration
	- count has to be reset before any process tries to increment again
- it is possible to solve the problems by using two counters, one that counts to n and one that counts to 0, and then switch for each iteration.
