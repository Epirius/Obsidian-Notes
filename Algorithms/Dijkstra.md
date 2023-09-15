
### Single source shortest path
```
input: a graph G = (V, E) with positive numbered weights
output: a mapping d: V -> N giving the distance from s
	- aka a mapping for each vertex that gives the distance from vertex s

```

```
suppose |V| = n,  |E| = m

for v in V:
	...
	for u in Neighbor(v):
		...

runtime: O(n^2)
```

```
let G = (V,E)
then the sum of deg(v) = 2m
	- deg counts edges for a given node

so the runtime above is actually o(n + m)
```
