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

----
```
Lemma: Let f1 < f2 < f_n be the frequencies

then there exists an optimal prefix-free code, with the T' such that f1, f2 as siblings at maximum depth

```


```
fx: frequency of x
dx: depth(x)
fy: frequency of y
dy: depth(y)
abl: average bit length
T: tree

Proof suppose that f_x < f_y
and depth(x) < depth(y)

create T' with x and y swapped

ABL(T) = ... = S
ABL(T') = S - fx * dx - fy * dy + fy * dx + fx * dy
	= S - (fx - fy)(dx - dy)

since fx < fy then
fx - fy < 0
dx - dy < 0

= S - epsilon < S = ABT(T)

So T' is smaller than T
ABT(T') < ABT(T)
Hence if  if fx < fy are placed with dx < dy then T is not optimal

```
