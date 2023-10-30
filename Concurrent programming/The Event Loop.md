- simplified setting: a single event queue which holds only events
- in reality: at least two queues that hold events and other actions performed by the browser
	- these actions are called [[tasks]]
	- two categories of tasks: [[macrotasks]] (or just tasks) and [[microtasks]]
- Examples of macrotasks:
	- creating the main document object
	- parse html
	- executing global javascript code
	- changing the current url
	- page loading (event)
	- network events
	- timer events
- Macrotask: one discrete, self-contained unit of work
- after running a task, the browser can continue with other assignments
	- such as: re-rendering the gui

## Microtasks
- smaller tasks that update the application state and *should be executed before the browser continues with other assignments* such as re-rendering the gui
- Examples of microtasks:
	- promise callbacks
	- DOM mutation changes
- Microtasks should be executed as soon as possible
	- in any asynchronous way
	- without the cost of executing a whole new macrotask
- microtasks enable executing certain actions before the gui re-renders.


## an event loop
- the implementation of an event loop should use:
	- at least one queue for macrotasks
	- at least one queue for microtasks
- usually, implementations go beyond these minimal requirements:
	- several queues for different micro and macro tasks, to prioritize types of tasks

- fundamental principles:
	- tasks are handled one at a time
	- a task runs to completion and cant be interrupted by another task
	- A single iteration:
		- if the macrotask queue is not empty, one task is processed
		- then while there are microtasks left, all microtasks are processed
		- when there are no microtasks left, we check if we need to re-render.
Important difference between macro and micro tasks:
- in a single loop iteration, one macrotask at most is processed (others are left waiting in the queue), but all microtasks are processed