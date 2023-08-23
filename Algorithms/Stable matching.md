a stable matching algorithm is an [[Algorithm]] that match to sets, where each item in each set has a preference list for who they want to match with in the opposite set.

for example a set of men and a set of women who each has a preference for who they want to match with of the opposite sex.


a stable matching algorithm would match all items in the sets in such a way as to maximize preference.

an [[unstable matching]] algorithm would be an algorithm where if one item finds a better match, this would result in lots of other matches braking up because each of the items in the other matches might find a better match.






------
def:

A matching of H (hospital), S (student) is a set M of pairs: M = {(h,s), {h',s'}, (h'', s'') ... }. such that each h ∈ H and s ∈ S appears in at most one pair.
A matching M is perfect if |M| = |H| = |S|

A perfect relation for a student S is an ordering where h > s > h'

given a perfect matching M with (h, s) ∈ M and (h', s') ∈ M, if s' > h > s & h > s' > h', then (h, s') is an unstable pair.

-----


-----
Stable Matching 

Input: Sets S, H, with preference relations for all s and h
Output: A stable, perfect matching M.

-----


### Brute force implementation
```
runtime: n! * n^2

fix one of the sets and try all combinations of pairs to the other set (n!)
and then check for stability (n^2)
```


### Gale-Shapley algorithm
```
runtime: n^2

Initially nobody is matched.
while some h ∈ H is unmatched and h has not proposed to all s ∈ S 
	h proposes to its highest ranked s that h has not yet proposed to.
	
	if s is unmatched:
		add (h,s) to M
	else if s is matched with h' and h > s > h'
		then replace (h',s) with (h,s)
	else 
		s rejects h.

```

we have to show:
1. Algorithm terminates
2. Outputs a perfect matching
3. The matching is stable

Observations:
1. Hospitals propose in descending order.
2. Once a student is matched, it does not get unmatched.
3. If a hospital is unmatched when the algo terminates, the hospital proposed to all students.


```
Proposition: G-S terminates after at most n^2 iterations

Proof: 
	let p(t) be the number of propositions (n,s) after iteration t.
	note that p(t+1) > p(t).
	there are only n^2 many pairs (h * s). 
		hence p() only increases at most n^2 times

claim: G-S outputs a matching
	a hospital proposes only if it is unmatched.
	hence h has <= 1 students.
	in each iteration a student only keeps its best hospital.
	hence s is only assigned <= 1 hospital
	-> M is a matching

claim: The matching is perfect
proof (proof by contradiction):
	Assuming that M is not perfect, 
	then there exists a h or s not in M.
	|H| = |S|, so some h not in M if and only if some s not in M.
	There are h and s not in m.
	s was not proposed to. (Observation 2)
	The algorithm terminated with h unmatched,
	hence h proposed to all students (Observation 3)
	h proposed to s.
	h did not propose to s.
	contradiction
```