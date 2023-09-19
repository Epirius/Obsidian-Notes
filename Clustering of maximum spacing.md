an application of [[minimum spanning tree]]

#### problem: can you create k [[Clustering|clusters]] so that the spacing between the clusters are maximized 

Definition of Spacing:
- given C = c1, c2, ... c_k
- the spacing of C is min distance(p, q) with p and q in different clusters
	- check all pairs of points in different clusters and find the minimum distance

```
Input: Points P, K ∈ Integers
	-k is the number of clusters to create
Output: A clustering C with max spacing
```

each edge you draw decreases the number of clusters.
so continually draw edges between the shortest points until we have k clusters, will give us a solution

### Obs:
1. A forest with n-1 edges has 1 component (trees)
2. A forest with n-2 edges has 2 components
-  A forest with n-k edges has k components

If we run [[Kruskal's algorithm]] for n-k rounds we have a forest with k components.
this algorithm outputs the clustering into k clusters, maximizing the spacing


- First construct the complete graph of all pairs. Θ(n^2)
- We can then run kruskal's

------
### Proof of correctness (confusing):
- Let C* be the result from kruskal
- let C be any other clustering
- let {p, q} ∈ C
- let p ∈C*, q ∈ C*, {p, q} not ∈ C*

- consider the edge E that kruskal added between q and p
- The spacing of C*  >= the length of E
- The spacing of C is <= the length of E