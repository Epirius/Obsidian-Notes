
instead of each worker checking the sum of a count before proceeding
let each worker wait for a single value to become true

after setting arrive[i] to 1 the worker i waits for continue[i] to be set to 1

a separate coordinator thread waits for all elements in arrive to be 1 and then sets all elements in continue to 1

it is the process that is waiting for a value that is set who is responsible for resetting that variable back to 0

### problems with this solution
an extra process will be required for this solution to work
- busy-waiting synchronization is inefficient unless each process executes on its own processor, so the coordination should execute on its own process
- execution time of the coordinator is proportional to the number of worker processes

- in iterative algorithms, each worker often executes identical code
	- hence each is likely to arrive at the barrier at about the same time as long as each worker thread has its own processor
	- so all arrive flags will be set at around the same time, but the coordinator constantly checks the arrive flags
	- SOLUTION: combine the actions of the coordinator and worker so that each worker is also a coordinator

#### Idea: organize the workers into a tree
- workers can send:
  - arrival signals up the tree
  - continue signals down the tree
- a worker node:
	- first waits for its children to arrive
	- then tells its parent node that it too has arrived
- when the root node learns that its children have arrived, it knows that all other workers have arrived
- hence the root can tell its children to continue, the children in turn tells its children etc..