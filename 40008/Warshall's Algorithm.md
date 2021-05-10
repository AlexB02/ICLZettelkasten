### What is Warshall's Algorithm?
- [[All Pairs Shortest Path Problem]] solution.
- A [[Shortest Path Algorithm]] for [[Directed Weighted Graph]] with **positive** or **negative** weights but **no cycles**!
- runs in $O(\left|V\right|^3)$ from 3 nested for loops

### How does it run?
##### Description
Executing the algorithm will find the [[Transitive Closure]] of a graph G by finding linking nodes and adding in connections to the [[Adjacency Matrix]].

##### Code
```python
input A
B  = A.deepcopy() # B = B(0)
n = len(B[0]) # get number of nodes in B
for k = 1 to n:
	# B = B(k-1), as B currently represents the previous iteration of k
	for i = 0 to n:
		for j = 1 to n:
			b[i, j] = b[i, j] or (b[i, k] and b[k, j])
	# B = B(k) as B has updated to reflect this 
# B = B(n) as we have completed the loop
return B # B is the adjacency matrix for graph with transitive closure
```

### Correctness
##### Invarient
$B = B_{k-1}$ 
##### Implementation
Recast the outer loop as a while loop and show the invarient is established initially and then maintained by each iteration of the while loop.
##### While Loop Invarient Code
```python
input A
B = A.deepcopy() # Copy A to B
k = 1 # B = B(k-1)
n = len(B[0]) # get number of nodes in B
while k <= n:
	# B = B(k-1)
	for i = 1 to n:
		for j =1 to n:
			b[i, j] = b[i, j] or (b[i, k] and b[k, j])
		k = k + 1
	# k = n + 1, B = B(n)
return B
```

#C40008 #card  