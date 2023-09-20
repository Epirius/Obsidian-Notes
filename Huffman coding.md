a normal encoding of text takes ceil(log2(len(symbols)))

### Prefix free
- we want to find a prefix free encoding (can be variable length) in which no symbols code is a prefix of another's
- we want to find a prefix free code, that minimizes the length of the encoding string


```
Input: string m 
	- E = set(m)   - the unique symbols in m
	- f = Counter(m)
```

## Algorithm
```
create a priority queue Q = {(f_s, s) : s ∈ E}
	- f_s: frequency of S
	- s: a symbol
- while |Q| >= 2:
	- V1, V2 = pop(Q), pop(Q)
	- create node V = (f_v1 + f_v2, (v1, v2))
	- push(Q, V) - push v into Q
- return pop(Q)

running time is O(n logn)
```

in every iteration the size of Q will decrease by 1