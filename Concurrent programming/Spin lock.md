a spin lock is a type of [[lock]] that does nothing until the lock is false.

- Idea: there are only two interesting states:
	- some process is in its critical section
	- no process is in a critical section
- to distinguish between these two states, only one variable is needed. independent of the number of processes
- we us a boolean variable as a [[lock]]
	- this lock indicates when any process is in a critical section

to us it, we await until the lock is false, and then set it to true before entering a critical section.

```
<await (!lock) lock = ture;>
critical section;
lock = false;
```

Conditional atomic actions of the form 
```
<await(!lock) lock = true;>
``` 
are special enough so that hardware often has built in support for them

this is called [[Test and Set]]