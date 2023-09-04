
### Iterative Dichotomizer 3
- if all data points have the same label
	- return a leaf with that label
- else if data points have identical feature values
	- return a leaf with the most common label
- else
	- choose a feature that maximizes the information gain (using [[entropy]])
	- add a branch for each value of the feature
	- for each branch
		- call the algorithm [[recursion|recursively]] for the data points with the particular feature value



### how to avoid [[Overfitting]]
- if there are no training points with identical feature values, ID3 will result in 100% training accuracy
- [[inductive bias]]: prefer smaller trees
- set a minimum size for a leaf or maximum depth for the tree
	- usually not enough
- early stopping
	- stop recursion once information gain is non-positive
	- problematic, cannot handle, e.g.., [[XOR]]
- pruning (post-pruning)
	- build a full tree, remove parts of it later