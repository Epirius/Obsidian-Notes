
### Iterative Dichotomizer 3
- if all data points have the same label
	- return a leaf with that label
- else if data points have identical feature values
	- return a leaf with the most common label
- else
	- choose a feature that maximizes the information gain
	- add a branch for each value of the feature
	- for each branch
		- call the algorithm recursively for the data points with the particular feature value

