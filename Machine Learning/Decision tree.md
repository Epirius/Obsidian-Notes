a tree where every branch node is a boolean check, and each leaf node is a result.

- inner nodes are associated with a boolean test
	- usually, the test involves only one feature
	- outgoing edges correspond to possible test results
- a child is selected based on the test results
- leaf nodes make a prediction
	- classification: assign a class label to an object
	- regression: assign a numerical value
	- predictions can be also probabilistic


### Expressiveness
- decision trees can approximate any function of the input feature with arbitrary precision
- if there are no duplicates with different class labels, there is a consistent decision tree for every training set with one path to a leaf for each data point
	- can be large

### Learning
- trees are typically learned using greedy heuristics
	- start with an empty tree
	- greedily select a feature to split
	- recurs
- possible to overfit

### which features to split?
- typically one wants to divide the space into "pure" parts
- in other words, one wants to reduce uncertainty
- that is, choose the feature which gives highest information gain


### [[entropy]]
- entropy measures average information content that is obtained from a stochastic information source
- more uncertainty -> more information content
- entropy of a random variable x is 
![[Pasted image 20230904084240.png]]

- high entropy
	- lots of uncertainty
	- nearly uniform distribution
- low entropy
	- less uncertainty
	- outcomes have probabilities near 0 or 1

### conditional entropy
- amount of information needed to describe the outcome of a random variable y when the value of a random variable x is known
- or amount of uncertainty of y when the value if x is known
![[Pasted image 20230904084659.png]]

### information gain
- what happens if we split the data set based on the value of x?
- information gain is increased in information after splitting
	- equivalently, decrease in entropy after splitting


## Algorithms
- [[ID3 algorithm]]



-------

### Properties
#### pros
- fast (both learning and prediction)
- easy to interpret
- invariant to scaling
- can handle both categorical and continuous data
- implicit feature collections
#### cons
- unstable
	- due to greedy learning, small differences in training data result in totally different trees
- usually competitive accuracy only in an ensemble