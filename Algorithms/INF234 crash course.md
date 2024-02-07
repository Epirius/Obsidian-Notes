Big o
- f(n) = O(g(n)) if f(n) < cg(n)
- a n^2 function is O(n^2)

Big theta
- f(n) = theta(g(n)) 


Recurrence relations !!!!!
- master theorem

graphs
dfs bfs mst and dijkstra

(x,. y) is a :
- forward edge:
	- pre(x) < pre(y)
	- post(y) < post(x)
- backward edge:
	- pre(x) > pre(y)
	- post(y) > post(x)

minimum spanning tree
- kruskals
	- picks the minimum edge, as long as it doesn't cause a cycle
- prims
	- starts with a node, and only pick edges that we are connected to so far, and we pick the minimum edge that does not cause a cycle

dynamic programming !!!!!!!!
- longest common subsequence
- knapsack !!!!!