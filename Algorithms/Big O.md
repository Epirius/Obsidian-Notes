Big O upper bounds the given function

big O ignores constants, and smaller terms.
Suppose that some algorithm has complexity {1.3 n^2 + 3.5 n + 8}
- this can be affected by f.eks. language, architecture instruction set etc..
- therefore we ignore constants.
ignoring constants we get: n^2 + n
1.3 n^2 + 3.5 n < 1.3 n^2 + 3.5 n^2 = c n^2
- so we can ignore the smaller n


Def (Oh) f(n) is O(g(n))
- if there exists some n0 >= 0, c >= 0
	such that for all n > n0
	f(n) <= c * g(n)
- f is asymptotically upper bound by g^n
- you may interpret f(n) is O(g(n)) as f <= g ^n


example:
```
f(n) = p n^2 + q n + r   
<= p n^2 + q n^2 + r n^2 
= (p + q + r) n^2

let c = (p + q + r)

for all n >= 1 = n0

f(n) <= c n^2
-> f(n) ∈ O(n^2)
```
