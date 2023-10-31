- lambda p has a small-step reduction semantics with additional runtime components to track, schedule, and execute promises, and operations to create, chain, and resolve or reject promises
- syntax of lambda p
	- explicit syntax is introduces for creating a promise, resolve a promise, and rejecting a promise
	- high level operations such as then and catch are modeled using lower level primitives
	- relations between dependent promises is modeled using an explicit link operation

### syntax
- promisify(e)
	- create promise from object e
- e.resolve(e)
- e.reject(e)
- e.onResolve(e)
	- chain promise
- e.onReject(e)
	- chain promise
- e.link(e)
	- link promise
