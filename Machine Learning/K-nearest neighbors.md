
inductive bias: similar objects have similar labels
possibly the simplest possible classifier
	find k points tat are most similar to the test point
	let them vote for the class label

k is a parameter chosen by the modeler
k should be an odd number to stop a tie from happening.

to small k may lead to [[Overfitting]]



## Pros and cons
### pros
- no assumptions about data
- simple
- often good accuracy
- versatile (can be used for both [[Classification]] and [[Regression]])
- with enough training points, can approximate any decision boundary ([[universal approximation theorem]])

### Cons
- high memory requirement
- prediction stage can be slow
- sensitive to irrelevant [[Features]] and the scale of the data
- curse of dimensionality

