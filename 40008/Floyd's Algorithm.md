### What is Floyd's Algorithm?
- solves [[All Pairs Shortest Path Problem]]
- a modification of [[Warshall's Algorithm]]
- runs in $O(\left|V\right|^3)$

### How does it work?
Let G be a 	[[Directed Weighted Graph]] with nodes {1, ... , n} and [[Adjacency Matrix]] A.

Let $B_k[i, j]$ be the length of the shortest path from i to j which uses *intermediate nodes <= k*. 
If there is no path, set to $\infty$. So:

if A[i, j]
$$B_0[i, j] = A[i, j]$$
ELSE
$$B_0[i, j] = \infty$$
and $B_n[i, j]$ will be the length of the shortest path from i to j.
##### Code
```python
input dist # a square matrix of minimum distances initialized to ∞ (infinity)
n = len(dist[0]) # Get the number of nodes in the graph

for each edge (u, v)
    dist[u][v] = w(u, v)  # The weight of the edge (u, v)
	
for each vertex v
    dist[v][v] = 0
	
for k from 1 to n
    for i from 1 to n
        for j from 1 to n
			dist[i, j] = min(dist[i][j], dist[i][k] + dist[k][j])
```

### Widest Path
The algorithm can be adapted to incorporate the [[Schulze Voting System]] to solve the [[Widest Path Problem]] in $O(\left|V\right|^3)$

#unfinished #C40008 