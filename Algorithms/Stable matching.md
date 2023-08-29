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
the runtime is linear in the size of the input
input size: O(|h| + |s| + |h|^2 + |s|^2)

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
proof (by contradiction):
	- Assuming that M is not perfect, 
	-> then there exists a h or s not in M.
	- |H| = |S|, so some h not in M if and only if some s not in M.
	-> There are h AND s not in m.
	-> s was not proposed to. (Observation 2)
	- The algorithm terminated with h unmatched,
	-> hence h proposed to all students (Observation 3)
	contradiction!
	=> M is perfect

claim: M has no unstable pair.
Proof (by contradiction):
	- Assume M has an unstable pair
	- let (h,s) be unstable, ie. (h,s) is not in M. (s > h > s') (h > s > h')
	- either:
		1. h never proposed to s
		2. h proposed to s, who rejected
		3. h was matched with s, but got unmatched
	-----
		1. by observation 1. h proposed to s before s'
		2. if s rejected, then s was matched with some hospital h'' with (h'' > s > h)
		- by observation 2, h' > h'' and h > h'. CONTRADICTION!
		3. Very similar to case 2 (ran out of time)
	-> none of these are true. CONTRADICTION!
	-> the assumption that M has an unstable pair is false
	=> M is stable

THEREFORE: G-S outputs a perfect stable matching in time O(n^2)
COROLLERY: every input has a stable perfect matching
```

-----
### Lemma: The G-S algorithm always outputs the same matching.
definition: 
- let h ∈ H, we say that s is a valid partner of h if there exists a stable matching (h,s) ∈ M
- the best valid partner of h is the valid partner that h prefers most. since this is unique, we denote by best(h)=s the best valid partner.

let M* = { (h, best(h)) for h ∈ H}


Lemma: G-S will always output M*
#### Proof (by contradiction):
- suppose that some execution E of G-S outputs a matching with some (h^, s^) where s^ != best(h^)
- Observation: some hospital is rejected by a valid partner
	- s^ is not h^ preferd candidate.
	- h^ proposed to best(h^) before s^
- let h be **the first** hospital to be rejected by a valid partner in E, let s be the reject-er.
- s rejects h because s is matched with h'.  (h' > s > h)
- since s is a valid partner of h, there exists some stable matching M' with (h, s).
	- M' :
		- (h, s)
		- (h', s')
	- s > h' > s'
- contradiction: M' is a stable matching, but h' prefers s over s' and s prefers h' over h.
	- there is an unstable pair (h', s), therefore the assumption leads to a contradiction, so the lemma must be true.


Every hospital is matched with its best valid student, but every student is matched with its worst valid hospital
- M* = { (worst(s), s) for s ∈ S }

-----
## Exercises
### 1
> True or false? In every instance of the Stable Matching Problem, there is a stable matching containing a pair (m, w) such that m is ranked first on the preference list of w and w is ranked first on the preference list of m.

```
h1 -> s1 s2 s3
h2 -> s2 s3 s1
h3 -> s3 s1 s2

s1 -> h2 h3 h1
s2 -> h3 h1 h2
s3 -> h1 h2 h3

h1 - s1
h2 - s2
h3 - s3

No there does not need to be a stable matching pair where both have the other as their first choice.
If both hospitals and students have a preference ring where h'n perfers s'n and each s'n perfers h'n+1 then each hospital will get its first choice of student and none of the students will get its perferd choice.

```

### 2
> True or false? Consider an instance of the Stable Matching Problem in which there exists a man m and a woman w such that m is ranked first on the preference list of w and w is ranked first on the preference list of m. Then in every stable matching S for this instance, the pair (m, w) belongs to S.

```
Yes if both h1 and s1 perfer each other first then they will end up as a pair because h1 will always propose to s1 first, and s1 will switch to h1 if they already have a match with h'n.
```