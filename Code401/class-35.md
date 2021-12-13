# Class 35

## <ins>*Graphs*

A graph is a non-linear data structure that can be looked at as a collection of `vertices` (or `nodes`) potentially connected by line segments named `edges`.

Graphs terminology :

1.  _Vertex_ - A vertex, also called a “node”, is a data object that can have zero or more adjacent vertices.
2.  _Edge_ - An edge is a connection between two nodes.
3.  _Neighbor_ - The neighbors of a node are its adjacent nodes, i.e., are connected via an edge.
4.  _Degree_ - The degree of a vertex is the number of edges connected to that vertex.

## Directed vs Undirected

### Undirected Graphs

An `Undirected Graph` is a graph where each edge is undirected or bi-directional. This means that the undirected graph does not move in any direction.

Vertices/Nodes = {a,b,c,d,e,f}

Edges = {(a,c),(a,d),(b,c),(b,f),(c,e),(d,e),(e,f)}

### Directed Graphs (Digraph)

A `Directed Graph` also called a `Digraph` is a graph where every edge is directed.

Vertices = {a,b,c,d,e,f}

Edges = {(a,c),(b,c),(b,f),(c,e),(d,a),(d,e)(e,c)(e,f)}

## Complete vs Connected vs Disconnected

There are many different types of graphs. This depends on how connected the graphs are to other node/vertices.

The three different types are completed, connected, and disconnected.

### Complete Graphs

A complete graph is when all nodes are connected to all other nodes.

### Connected

A connected graph is graph that has all of `vertices`/`nodes` have at least one edge.

### Disconnected

A disconnected graph is a graph where some vertices may not have edges.

## Acyclic vs Cyclic

In addition to undirected and directed graphs, we also have acyclic and cyclic graphs.

### Acyclic Graph

An acyclic graph is a directed graph without cycles.

A cycle is when a node can be traversed through and potentially end up back at itself.

### Cyclic Graphs

A Cyclic graph is a graph that has cycles.

A cycle is defined as a path of a positive length that starts and ends at the same vertex.

## Graph Representation

1.  Adjacency Matrix
2.  Adjacency List

### Adjacency Matrix

An Adjacency matrix is represented through a 2-dimensional array. If there are _n_ vertices, then we are looking at an _n x n_ Boolean matrix

a **sparse** graph is when there are very few connections. a **dense** graph is when there are many connections

Within an adjacency matrix, an undirected graph will always be symmetric. This is not the case for a directed graph.

### Adjacency List

An adjacency list is the most common way to represent graphs.

An adjacency list is a collection of linked lists or array that lists all of the other vertices that are connected.

Adjacency lists make it easy to view if one vertices connects to another.

## Weighted Graphs

A weighted graph is a graph with numbers assigned to its edges. These numbers are called weights. This is what a weighted graph looks like:

When representing a weighted graph in a matrix, you set the element in the 2D array to represent the actual weight between the two paths. 

If there is not a connection between the two vertices, you can put a `0`.