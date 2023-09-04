- an atomic action makes an indivisible state transformation.
	- any intermediate state that might exist in the implementation of the action must not be visible to other processes


## Atomic operations
- can not be subdivided
	- no observable intermediate state
- language-dependent
	- reading a variable value is usually an atomic statement
	- writing to a variable is usually an atomic statement
	- read + write is usually not an atomic statement
		- x = y; is not atomic because you read y and write x
		- x++; is not atomic
- typically there are special atomic operations / atomic variable types
	- example: AtomicInteger in java
		- x += 1; is atomic if x is AtomicInteger
- language constructs may allow creating large atomic blocs:
	- atomic { x=y; y++; x++; }


atomic statements are expensive in terms of performance. the compiler has to do a lot of work.
so you should minimize the parts of the code that need to be atomic

-----
### Fine-grained atomic actions
- implemented directly by the hardware on which a concurrent program executes
