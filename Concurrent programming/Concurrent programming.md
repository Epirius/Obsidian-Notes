when a program needs to handle multiple simultaneous events.
this can be done via [[Multi-tasking]]

its about dealing with a lot of things at the same time

#promise-await
#concurrency 
#non-deterministic


## Properties of concurrent programs
- State: snapshot of values of all [[Shared-variable programming|Shared variables]]
- History: sequence of [[state|states]], or sequence of memory operations
- Property: predicate over program history
- True property: predicate that is true for all possible histories

## Some properties of interest in concurrent programming
- safety: program cannot reach a bad state
- liveness: program will eventually reach a desired state
- partial correctness: if program terminates, it does so in a desirable final state
- termination: all histories are finite
- total correctness: partial correctness + termination

## How to ensure the desired properties
- testing
	- increases confidence, but it is not a proof
	- impractical to cover all states
- operational reasoning
	- analyse all possible histories of programs
- formal analysis
	- produce a proof
	- Hoare-triples