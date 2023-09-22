

### Running time of merge sort
```
c: some constant

T(n) = T(n/2) + T(n/2) + (c * n)
	 = 2 T(n/2) + c n
	 - Recurrence relation
```
[[Recurrence relation]]
```
for each child the work to combine is half for the parent
eg parent = c * n
	child = c * n/2
	etc..
	
at each level we half the input size
so the height of the tree is log2(n)


work done for each level:
level 0 = c n
level 1 = 2 c n/2 = c n
...
level j:
	- nodes = 2^j
	- size of instance = n / 2^j
	- total work done in level j = nodes * size of instance * work done
	- = 2^j c n/2^j 
	- = c n 

total work = number of levels * work done per level
		= log2(n) c n
		= O(n log n)

```


### Lemma
- any function T satisfying T(n) <= 2 t(n/2) + O(n) is O(n log n)


T(n)  = (sum from j=0 to log n) 2^j c n/2^j
		= c n (sum from j=0 to log n) 2^j/2^j
		= c n (sum from j=0 to log n) (2/2)^j