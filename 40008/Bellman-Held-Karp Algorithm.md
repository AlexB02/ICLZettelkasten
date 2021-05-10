### What is the Bellman–Held–Karp Algorithm?
A [[Dynamic Programming]] algorithm proposed in 1962 to solve the [[Traveling Salesman Problem]].

### Code
```python
choose start from nodes
for x in (nodes \ start):
	C[{}, x] = W[start, x]

for subset from (nodes \ start) where subset != {}:
	for x in nodes \ (subset U start):
		C[subset, x] = infinity
		for y in subset:
			# if the path through the new node is better, pick it
			C[subset, x] = min(C[subset \ {y}, y] + W[y, x], C[subset, x])
			
optimum = infinity
for x in (nodes \ start):
	optimum = min(C[nodes \ (start U {x}), x] + W[x, start], optimum)
return optimum
```

### HCP Code
In this method, one determines, for each set S of vertices and each vertex v in S, whether there is a path that covers exactly the vertices in S and ends at v. For each choice of S and v, a path exists for (S,v) if and only if v has a neighbor w such that a path exists for (S − v,w), which can be looked up from already-computed information in the dynamic program.
```python
choose start from nodes
for x in (nodes \ start):
	if arc(start, x):
		C[{}, x] = W[start, x]
		H[{}, x] = True
	else:
		H[{}, x] = False

for subset from (nodes \ start) where subset != {}:
	for x in (nodes \ (subset ++ start)):
		C[subset, x] = infinity
		for y in subset:
			# if the path through the new node is better, pick it
			if arc(y, x) and H[subset \ {y}, y]:
				C[subset, x] = min(C[subset \ {y}, y] + W[y, x], C[subset, x])
				H[subset, x] = True
			else:
				H[subset, x] = False
			
optimum = infinity
for x in (nodes \ {start}):
	if H[(nodes \ {start, x}), x] and H[{}, x]:
		optimum = min(C[nodes \ (start U {x}), x] + W[x, start], optimum)
return optimum
```
#unfinished #C40008 