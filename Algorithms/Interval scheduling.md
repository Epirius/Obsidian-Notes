```
Input: I = { I1, I2, I3 ... }
Output: a maximum set S ∈ I of pairwise non-overlapping intervals

A set of intervals is compatiable if no two intervals overlap.

si = start time
fi = finish time
```

Algorithm 1
```
Sort intervals by their fi
iterate over list of intervals
pick those with out conflict

runtime: O(n logn)
```


### Lemma: Algorithm 1 outputs the optimal solution
```
Let A* be the output of algorithm 1
Let S be any soulution

We will show that |A*| >= |S|
```

```
s = start time
f = finish time
r = index


Proof (By induction):

Let a* = i1, i2, i3 ... ik
Let s  = i1, i2, i3 ... im

we will show k >= m
claim for all r <= k
	ir.f <= jr.f

base case: r = 1
	our algorithm picks the interval with smallest f values (due to sorting)

induction:
	assuming: i(r-1).f <= j(r-1).f
	let r > 1:
		since s is a solution, s is compatiable (no overlap)
		j(r-1).f <= jr.s
		i(r-i).f <= jr.s
	so ir.f <= jr.f


Since the algorithm halts when no more intervals are avaliable
m <= k
our algorithm is optimal.
```



#proof #proof-induction