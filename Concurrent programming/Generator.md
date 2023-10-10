- calling a generator does not execute it, but instead create a new iterator
	- after a generator produces a value it will suspend its execution and wait for the next request.


- a generator works like a [[state machine]] with states:
	- suspended start
		- when a generator is created, it starts in this state, nothing is executed yet.
	- executing
		- the state when the code is being executed
		- the execution continues either from the beginning or from where the generator last suspended
		- a generator moves to this state when the matching iterators `.next()` method is called and there exist code to execute
	- suspended yield
		- during execution, when a generator reaches a yield expression, it creates a new object carrying the return value, yields it, and suspends its execution
		- this is the state in which the generator is paused and is waiting to continue its execution
	- completed
