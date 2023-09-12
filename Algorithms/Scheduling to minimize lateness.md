#greedy

```
t: timespan
d: deadline
s(): start time

input: interval I = (t_i, d_i)

if I = (2 hours, 15:00) and I is assigned at s(I) = 14:00, the job can not be done

the lateness of i:
- if I_i is schedualed at time s(I_i)
	- then f(I_i) = s(I_i) + t_i
- Lateness l_i = Max(o, f(I_i - d))

Task:
- we want to schedual intervals to minimize lateness L
- L = Max l_i
	- aka the person with the most late time.
```



### Lateness Scheduling
```
input: I = { I1, I2, I3 ... In }
output: a schedual that minimizes the maximum lateness 
	- (the lateness of the person with the maximum lateness, not the sum of all lateness which is NP hard)
```

```
Idle-freeness:
- when we do schedualing, there is no point in leaving gaps. it is always better to scheduale a later task as soon as the previous task ends
- tasks are scheduled back to back.
```

#### Attempt 1 (bad)
```
Schedule the shortest job first
- suppose:
	- t1 = (t = 1,  d = 100)
	- t2 = (t = 10, d = 10)
- this algorithm will fail because t1 is scheduled first.
```

#### Attempt 2 (bad)
```
Minimize slack
- sort by d_i - t_i
- this will fix the situation from attempt 1

- suppose:
	- t1 = (t = 1, d = 2)    -slack 1
	- t2 = (t = 10, d = 10)  -slack 0

- if we start with t2, the lateness is 9
- if we start with t1, the lateness is 1
```

#### Attempt 3 (good)
```
Earliest deadline first
- sort by d_i


```