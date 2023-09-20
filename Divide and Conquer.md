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

----
