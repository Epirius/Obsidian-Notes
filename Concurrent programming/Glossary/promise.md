a value that i don't have right now, but will have in the future

a promise can be in one of three states:
	- pending: promise has no value yet
	- fulfilled: the asynchronous operation has completed, and the promise has a value which will not change
	- rejected: the operation failed, and the promise will never be fulfilled

code inside .then() is ran when the promise is fulfilled or rejected

### Promises/A+
an open standard for implementing promises
Terms:
- promise
	- an object or function with a then method
- Then-able
	- an object or function that defines a then method
- value
	- any legal javascript value
- exception
	- exception value
- reason
	- 