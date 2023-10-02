## Clustering techniques
- centroid model: a cluster is represented by a single mean vector
- distribution model: clusters are modeled with statistical distribution
- connectivity model: build clusters based on distance connectivity
- density model: a cluster is set of points connected by density regions
- ...


## K-means
- most famous and commonly used
- a cluster is represented by centroid
- goal is to put similar points in the same cluster by minimizing the within-cluster variance
- [[K-nearest neighbors]]
- Lloyd's algorithm
	- pick initial cluster centroid
	- repeat until nothing changes
		- assign each data point to a cluster whose centroid is closest to that point
		- update the centroids: the new centroid of a cluster is the mean of the data points assigned to that cluster