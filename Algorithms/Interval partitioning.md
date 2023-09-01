
```
Input: I = { i1, i2, ... in }
Output: a partitioning of I into fewest pairwise compatiable (no overlapping) sets
```

```
i: interval
s: start time
f: finish time (for the interval)

Let depth(i) be max t |{i ∈ I : i.s <= t <= I.f}| ()

our algorithm will assign a label to each interval such that no two intervals with the same label overlapps

1. sort by start time.
	assign a label to the first interval
	and then delete the label.
	When a labeled interval ends, we will add back the label.
```