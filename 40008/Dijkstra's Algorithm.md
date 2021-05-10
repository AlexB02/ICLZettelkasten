### What is Dijkstra's Algorithm? 
- a [[Shortest Path Algorithm]] for a [[Weighted Graph]] G.
- similar to [[Prim's Algorithm]] by style.
- solves [[Single Pair Shortest Path Problem]]
- runs in $O(\left|V\right|^2)$

### Implementation
1. begin at `start` node
2. greedily pick next node
3. update candidate arcs
4. pick next node from the fringe by shortest distance from start
5. repeat 3 & 4 till a path is found from `start` to `finish`

### Code
```java
public static Graph calculateShortestPathFromSource(Graph graph, Node source) { 
	source.setDistance(0);
	Set<Node> settledNodes = new HashSet<>(); 
	Set<Node> unsettledNodes = new HashSet<>(); 
	unsettledNodes.add(source); 
	while (unsettledNodes.size() != 0) { 
		Node currentNode = getLowestDistanceNode(unsettledNodes);
		unsettledNodes.remove(currentNode); 
		for (Entry < Node, Integer> adjacencyPair: currentNode.getAdjacentNodes().entrySet()) { 
			Node adjacentNode = adjacencyPair.getKey(); Integer edgeWeight = adjacencyPair.getValue();
			if (!settledNodes.contains(adjacentNode)) { 
				calculateMinimumDistance(adjacentNode, edgeWeight, currentNode); unsettledNodes.add(adjacentNode); 
			} 
		}
	settledNodes.add(currentNode); 
	}
	return graph; 
}
```

### Issues with negative weights
- Does not work for negatively weighted graphs, as it assumes that the arcs are always positive
- Negative cycle is especially bad as you can loop infinitely reducing path length

### Priority Queues
Dijkstra's Algorithm can be implemented using a [[Priority Queue]].
##### Invarient:
1. If x is a tree or fringe node (other than start) then parent[x] is a tree node.
2. If x is a tree node (other than start) then distance[x] is the length of the shortest path and parent[x] is its predecessor along that path.
3. If f is a fringe node then distance[f] is the length of the shortest path where all nodes except f are tree nodes. Parent[f] is its precessor along that path.

To show invarient is:
- established before the while loop
- maintained in the while loop

We must show that (2) is maintained & the rest of the proof is omitted.


### Useful Resources
https://www.pearsonschoolsandfecolleges.co.uk/secondary/Mathematics/16plus/AdvancingMathsForAQA2ndEdition/Samples/SampleMaterial/Chp-02%20023-043.pdf

#C40008 #madecard 