# Graphs

## Learning Objectives

Developers will be able to:

- Define graphs
- Understand the difference between undirected and directed graphs, and use cases for each
- Describe the differences between implementation with adjacency lists vs. adjacency matrices
- Understand the time complexities of operations in graphs
- Describe how DFS vs. BFS works in graphs
- Implement a graph using an adjacency list

## Setup

- Clone down this repo, cd into it, install dependencies and open it.

```
$ git clone <paste ssh url>
$ cd graphs
$ npm install
$ code .
```

- Run tests

```bash
$ npm test
```

## What are Graphs?

A graph is a collection of nodes, which store data, and edges, which represent relationships or connections between nodes.

![Graph with A, B, C, D, E nodes](https://ga-instruction.s3.amazonaws.com/assets/tech/computer-science/intro-data-structures/9-Diagram.png)

Graphs are commonly used to represent networks. They are concerned with the multiple relationships between entities, like the friend connections in a network of users, or the possible routes between locations on a map.

Facebook has [used a graph data structure](https://m.facebook.com/nt/screen/?params=%7B%22note_id%22%3A10158791578747200%7D&path=%2Fnotes%2Fnote%2F&refsrc=deprecated&_rdr) to organize its data since 2013. Items like users, check-ins, and comments would be stored as objects, also called “nodes.” The relationship between those items — “liked by” or “friend of” — are represented as “edges” that connect the objects. A graph structure is the clearest and most efficient way for Facebook to store this data, return it to users, and make it accessible to developers.

**❓ You know what’s represented by the nodes and edges in Facebook’s graph. What would the nodes and edges in Google Maps’ graph represent?**

**❓ Trees and linked lists also have nodes. How are trees and linked lists different from graphs based on what you've seen so far?**

## Undirected vs. Directed

Because graphs are not hierarchical like trees or ordered like lists, how do we show relationships between nodes on a graph?

We describe the edges in a graph as undirected (a mutual connection between nodes) or directed (pointing from one node to another). Undirected and directed edges define how we categorize graphs.

### Undirected

An undirected graph has edges that describe a mutual connection between two entities. An example of this would be a LinkedIn connection -- the relationship is mutual and the directionality of it does not matter.

### Directed

On the other hand, a directed graph has edges that point from one entity to another. An example of this might be following someone on Twitter.

The direction of these relationships matter, and thus the edge between two nodes points from one to the other.

![Directed graph](https://ga-instruction.s3.amazonaws.com/assets/tech/computer-science/graphs/directed-graph.png)

**❓ Which type of graph would we need to represent liking someone's Instagram post?**

**❓ Which type of graph would we need to represent all the available flight routes between destinations?**

## Implementing Graphs

There are two main ways that we can implement graphs in code.

### Adjacency List

An adjacency list uses a collection of arrays for each node, and is the more commonly used implementation. In this implementation, a graph is represented with a collection of arrays for each node.

In code, an adjacency list looks like the example below. Each key-value pair represents a node. The key is the value of the node, and the value is an array of edges to other nodes:

```js
const graph = {
	A: ['B', 'E'],
	B: ['A', 'C', 'D', 'E'],
	C: ['B', 'D'],
	D: ['B', 'C', 'E'],
	E: ['A', 'B', 'D'],
};
```

**❓ What would this look like drawn out in visual form?**

**❓ Is the graph represented here a directed or undirected graph?**

### Adjacency Matrix

An adjacency matrix is represented by a two-dimensional array. In an adjacency matrix, a graph is represented by a two-dimensional array (an array of arrays). Each subarray is a node, and the values in the node represent edges to other nodes. Conceptually, this is what it looks like:

In code, it looks like this, where a 1 represents an edge and a 0 represents a lack of an edge:

```js
const graph = [
	[0, 1, 0, 0, 1],
	[1, 0, 1, 1, 1],
	[0, 1, 0, 1, 0],
	[0, 1, 1, 0, 1],
	[1, 1, 0, 1, 0],
];
```

**❓ The adjacency matrix graph above is an undirected graph. There’s a secret clue in the graph that can help you figure that out — can you tell what it is?**

## Time Complexity

## Additional Resources

- Practice building a graph [visually](https://visualgo.net/en/graphds?slide=1).
- Common graph interview [questions AND solutions](https://medium.com/@codingfreak/graph-data-structure-interview-questions-and-practice-problems-22d5cd488855).
- Some graph data structure [interview question topics](https://medium.com/@codingfreak/graph-data-structure-interview-questions-and-practice-problems-22d5cd488855).
- Visualizations of [breadth-first search](https://www.cs.usfca.edu/~galles/visualization/BFS.html) and [depth-first search](https://www.cs.usfca.edu/~galles/visualization/DFS.html) in a graph structure.
- [More interview questions](https://stackabuse.com/graph-data-structure-interview-questions) about graphs that don’t necessarily deal with coding.
