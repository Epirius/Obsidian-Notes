- many languages offer ways of running [[Coroutines]] concurrently with their caller
- this is perhaps not in line with the original notion of a [[Coroutines]], but the term has expanded to cover such abstractions

## in js
- a function defined as async can contain await statements
	- await e: evaluates e to a [[promise]], and waits until the promise is resolved
	- the resolved promise's value 