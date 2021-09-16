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
