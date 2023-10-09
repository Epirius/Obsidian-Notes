- generalization of [[subroutines]] (function) that allows:
	- suspending the execution of the subroutine
	- resuming a suspended execution
		- local variables and a program counter persist since suspension

- suspend: suspend execution, remember current point, save current frame, transfer execution back to caller
- resume: restore saved frame, continue from point of execution
- destroy: de-allocate saved frame (without resuming execution)
