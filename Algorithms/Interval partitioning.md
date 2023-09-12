#greedy
```
Input: I = { i1, i2, ... in }
Output: a partitioning of I into fewest pairwise compatiable (no overlapping) sets
```

```
i: interval
s: start time
f: finish time (for the interval)


Let depth(i) be max t |{i ∈ I : i.s <= t <= I.f}| ()

depth is the number of intervals that overlap at a given time

our algorithm will assign a label to each interval such that no two intervals with the same label overlapps

1. sort by start time.
	assign a label to the first interval
	and then delete the label.
	When a labeled interval ends, we will add back the label.
```


```
d: depth

obeservation
- the number of available colors at time t is d - | { I, s(I) < t < f(i) } |

claim
- there is an avaiable color at time s(i)
- suppose that k intervals started (but not finished) before s(i)
- at time s(i), we have k+1 overlapping intervals 
- since k + 1 <= d 
- -> d-k >= 1
- -> at least 1 color is avaliable
```

```
claim
- every two overlapping intervals get different colors

proof:
- suppose not.
- ie I1 and I2 get color C with s(I1) < s(I2) < f(I1)
- but at time s(I2), C is already popped and has not been pushed again, which means that C is not avaliable at time s(I2)
```
