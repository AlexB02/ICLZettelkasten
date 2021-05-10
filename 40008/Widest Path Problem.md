### What is the Widest Path Problem?
#madecard
Given a [[Directed Weighted Graph]] (G, W) for each pair of nodes i, j find the greatest of the [[Bandwidth]]s of the paths from i to j. If there is no path from i to j return 0 for this pair of nodes.

### Code
```python
input bandwidth # a square matrix of bandwidths initialized to 0

for each arc (u, v)
    bandwidth[u][v] = W(u, v)  # The bandwidth of the edge (u, v)
	
for k from 1 to n
    for i from 1 to n
        for j from 1 to n
			bandwidth[i][j] = max(bandwidth[i][j], bandwidth[i][k], bandwidth[k][j])
```

#C40008 