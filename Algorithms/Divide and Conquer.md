problem P = a list
if you can solve each half of the list and combine the results, you can solve them separately and come to a solution for P

instead of solving P, solve 
P_a -> S_a
P_b -> S_b
S_a + S_b -> S

when you recursively divide, you eventually come to a constant size part of the list


examples:
- [[merge sort]]
- [[binary sort]]
- [[integer multiplication]]
- [[closest pair|closest pair of points]]
- etc


----

see [[merge sort]] for runtime analysis


### Lemma
- any function T satisfying T(n) <= 2 t(n/2) + O(n) is O(n log n)


T(n)  = (sum from j=0 to log n) 2^j c n/2^j
		= c n (sum from j=0 to log n) 2^j/2^j
		= c n (sum from j=0 to log n) (2/2)^j
		= O(c n log n)    - because of [[geometric progression]]
		=O(n log n)

----
(Sum from j=0 to N) q^j is called [[geometric progression]]


we analyze by [[unrolling]] the recursion tree
```
example (using java's BigInteger multiplication runtime):
T(n) = 5 T(n/2) + 2n
	           - height is log3(n)
	           - level j = 5^j nodes
	           - work per node = c n/3^j
	= (Sum, j=0, log3(n)) 5^j c n/3^j
	= c n (Sum, j=0, log3(n)) 5^j/3^j
	= c n (Sum, j=0, log3(n)) (5/3)^j
	= c n * Θ((5/3)^log3(n))   - from geometric progression rule
	= Θ( n * (5^log3(n)) / (3^log3(n)) )
	= Θ( n * (5^log3(n)) / n )
	= Θ( n^(log3(5)) )
	= O(n^1.465)
```

-----

```
Lemma: any function satisfying T(n) < 5 T(n/3) + O(n) is O(n^1.465)
```


-------------

### Running time of matrix multiplication
```

T(n) = 8 T(n/2) + O(n^2)
				- 8 recursive calls
				- in each call we have (n/2^j)^2
				- levels = log2(n)
				- number of nodes in level j = 8^j
				- work done per node: (n/2^j)^2
	= (Sum, j=0, log2(n)) 8^j (n/n^j)^2
	= (Sum, j=0, log2(n)) 8^j n^2/     ...
	...
```