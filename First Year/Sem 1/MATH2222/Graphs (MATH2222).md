>[!def]
>A *graph* $\Gamma$ in combinatorics is a (usually finite) set of vertices $V$ and a set of edges $E$.
>$$\Gamma = (V,E)$$
>Each edge $e\in E$ has two (potentially identical) vertices $\left\{v,w\right\}$ associated to it.
>
>Vertices are usually drawn as points, and edges as lines connecting the points.
>![[Graphs (MATH2222 2024-04-24 13.28.03.excalidraw|200]]
>Note that it does not matter how exactly the graph is drawn, as long as it shows the vertices connected by the correct edges.

>[!def]
>A *simple graph* is a graph where every pair of vertices has at most one edge, and there are no loops.
>![[Graphs (MATH2222 2024-04-24 13.30.46.excalidraw|200]]

>[!def]
>Let $\Gamma$ be a simple graph (though this also works for other graphs). Given a vertex $v$ of the graph, the degree of $v$ is the number of edges with an endpoints on $v$.
>![[Graphs (MATH2222 2024-04-24 13.33.55.excalidraw|200]]

---

>[!theorem]
>Let $\Gamma$ be a simple graph with at least 2 vertices (note this only excludes one graph - the graph with one vertex and no edges).
>Then there are two vertices $v\ne w$ with the same degree.

>[!proof]
>Suppose that we have a simple graph $\Gamma$ has $n$ vertices, $n\ge 2$. The possible degrees of the vertices are $0,1,\cdots,n-1$. The only way for $n$ vertices to have distinct degree would be for one vertex to have degree 0, one to have degree 1, etc., up to $n-1$.
>However if a vertex has degree $0$, then the remainder of the graph can have maximum degree $n-2$. So there cannot be a vertex of degree $0$ and $n-1$ simultaneously.
>Therefore, by the pigeonhole principle, there must be two vertices with the same degree.

---

>[!def]
>The complete graph $K_{n}$ is the simple graph with $n$ vertices where every vertex is connected to every other vertex.
>![[Graphs (MATH2222 2024-04-24 13.42.52.excalidraw|200]]

>[!example]
>Suppose we take a complete graph $K_{n}$ with $n$ vertices, and we colour the edges red and green. How large must $n$ be so that we are guaranteed to have a black edge or a blue edge?
>
>Here we need 2 vertices.
>
>Now, how large must $n$ be so that we are guaranteed to have a black triangle or a blue triangle?
>
>![[Graphs (MATH2222 2024-04-24 13.49.01.excalidraw|200]]
>(Side note: this is denoted in Ramsey theory as $R(3,3)=6$)

---

>[!def]
> Let $G, H$ be simple graphs. I.e., if we take $v,w\in V(G\text{ or } H)$ then $vw$ may be an edge, but if so, it is the only edge.
> We now say that a function $f : V(G) \longrightarrow V(H)$ is an *isomorphism* if and only if $vw\in E(G) \Leftrightarrow f(v)f(w)\in E(H)$.
>If there exists an isomorphism $f : G \longrightarrow H$ we say that $G$ and $H$ are *isomorphic*, and write $G\cong H$.

>[!example]
>![[Graphs (MATH2222) 2024-04-30 13.17.22.excalidraw]]
>Here we have two graphs that are not equivalent, but are isomorphic.

---

>[!theorem]
>$G\cong H$ is an equivalence relation.

>[!proof]
>Reflexive: $G\cong G$ via $id : V(G) \longrightarrow V(G)$.
>Symmetric: if $G\cong H$ via $f$, then as $f$ is bijective, then $f^{-1}$ will give $H\cong G$.
>Transitivity: if $G\cong H$ via $f$ and $H\cong I$ via $g$ then $g\circ f$ will give $G\cong I$.

---

>[!question]
>How can we tell whether two graphs $G,H$ are isomorphic?

>[!remark]
>It is often much easier to tell if two graphs are **not isomorphic**!

>[!example]
> ![[Graphs (MATH2222) 2024-04-30 13.26.33.excalidraw|400]]
> Note that in these graphs, we can quickly find the degrees of each vertex and see that they are not isopmorphic.

>[!example]
>![[Graphs (MATH2222) 2024-04-30 13.34.23.excalidraw]]

>[!remark]
>In graph theory, we should define properties that are preserved under isomorphisms.

# Connectivity
>[!def]
>A *path* is a simple graph whose vertices can be listed in order such that two vertices are adjacent if and only if they share an edge.
>Recall the following diagram, which had two paths.
>![[Graphs (MATH2222) 2024-04-30 13.17.22.excalidraw]]
>Note also that each vertex in the path is distinct; the same vertex cannot be used more than once.

>[!def]
>A *cycle* is a simple graph whose vertices can be placed on distinct points on a circle so that adjacent points share an edge. I.e., it is a path where the first and last points share an edge.

>[!def]
>The *length* of a path or cycle are given by the number of edges.

>[!remark]
>We are often interested in paths and cycles within another graph.

>[!example]
>Consider the following graph.
>![[Graphs (MATH2222) 2024-04-30 13.41.07.excalidraw]]

>[!def]
>A graph is *connected* if there is a $u,v$-path in $G$ for any two vertices $u,v\in V(G)$.
>Otherwise, we say $G$ is *not connected* or *disconnected*.
>A *connected component* of a graph $G$ is a connected subgraph that is not contained in any bigger connected subgraph.

>[!example]
>![[Graphs (MATH2222) 2024-04-30 13.43.55.excalidraw]]
>This graph is not connected, but has four connected components.

---

>[!def]
>Let $e\in E(G)$. The subgraph of $G$ obtained by deleting $e$ is denoted $G-e$.
>Let $v\in V(G)$. The subgraph of $G$ obtained by deleting $v$ and its incident edges is denoted $G-v$.

>[!example]
>![[Graphs (MATH2222) 2024-04-30 13.46.09.excalidraw]]

---

>[!theorem]
>Let $G$ be a connected graph and let $e\in E(G)$. Then $G-e$ is connected if and only if $e$ belongs to a cycle in $G$.

>[!example]
>![[Graphs (MATH2222) 2024-04-30 13.48.47.excalidraw]]

>[!proof]
>Suppose $e$ is in a cycle. We want to show that there is a $u,v$-path in $G-e$.
>Let $p$ be a path $u-x_{1}- x_{2}-\cdots-x_{k}-v$. If $e$ is not in $p$, then we are done, as removing $e$ has no effect.
>If $e$ is in $p$, then we can replace $e$ with the rest of a cycle that is contained in. Now we have a new $u,v$-path.
>
>Suppose that TODO

---

>[!def]
>A *tree* is a connected graph with no cycles.
>![[Graphs (MATH2222) 2024-05-01 13.09.18.excalidraw]]

>[!lemma]
>Suppose that $G$ is a graph where all vertices have degree $\ge2$. Then $G$ contains a cycle and is therefore not a tree. Note that this does not hold if we allow $G$ to have infinitely many vertices (e.g., an infinite path).
>
>>[!proof]
>>Since $V(G)$ is finite, $G$ contains a maximal path $p$, i.e., a path which is not contained in any larger path.
>>The endpoints of this maximal path must have degree greater than two. So each endpoint must have another edge. If this edge goes to a vertex not in the path, then we have created a longer path, which is not possible as $p$ is maximal. So the endpoints must join to vertices already in the path; there must be a cycle.

>[!corollary]
>Any tree contains a *leaf* (a *leaf* is a vertex of degree 1).

>[!lemma]
>If $T$ is a tree on $n$ vertices, and $v\in V(T)$ is a leaf, then $T-v$ is a tree on $n-1$ vertices.
>
>>[!proof]
>>It is clear that $T-v$ has no cycles as $T$ has no cycles.
>>Let $x,y$ be two vertices in $T-v$, which must also be vertices of $T$.
>>For any $x,y$ consider the path $p$ on $T$. Each vertex of $x,y$ must have degree $\ge 2$ as $p$ is a path, unless the vertex is an endpoint. $v$ has degree one, so the only way for this path to no longer be valid in $T-v$ is when either $x$ or $y$ is $v$. However $v$ is not in $T-v$, so this will never occur. So we may connect any two vertices using the same path as was used in $T$.

>[!example]
>Up to isomorphism, there is only one tree on $3$ vertices.
>On 4 vertices, there are 2.
>On 5, there are 3.

>[!theorem]
>Trees on $n$ vertices have $n-1$ edges.
>
>>[!proof]
>>We can prove this by induction on $n$.
>>In the base case, the singleton tree with $n=1$ has $n-1=0$ edges.
>>Now suppose that any tree with $n-1$ vertices has $n-2$ edges. Then let $T$ be a tree with $n$ vertices. Take some leaf, which must exist and must have degree 1. Then $T-v$ is a tree with $n-1$ vertices, and we know that this has $n-2$ edges. When removing $v$, we removed one edge, so $T$ must have had $n-1$ edges. We are now done by induction.

>[!def]
>A *spanning tree* of $G$ is a subgraph of $G$ with the same set of vertices.

>[!theorem]
>If $G$ is connected, then $G$ must contain a *spanning tree*.

---

>[!def]
>A *bipartite graph* $G$ is a graph whose vertex set can be partitioned with $V(G)=X\sqcup Y$ such that all edges of $G$ go between vertices in $X$ and vertices of $Y$. We say $(X,Y)$ is a *bipartition* of $G$. $X,Y$ are also called *independent*, as there are no edges between any two elements of either set.

>[!lemma]
>If $G$ contains an odd cycle, then $G$ is not bipartite.
>
>>[!proof]
>>For $G$ to be bipartite, there cannot be any non-bipartite subgraph. If there is an odd cycle, then we would need to map each vertex in the cycle to the two bipartitions in an alternating fashion. This is not possible on an odd cycle.

>[!lemma]
>Any tree $T$ is bipartite.
>
>>[!proof]
>>By induction on the number of vertices. Remove a leaf, then add it back.

>[!theorem]
>$G$ is bipartite **if and only if** it has no odd cycle.
>
>>[!proof]
>>One direction of this has already been prove.
>>We may assume without loss of generality that $G$ is connected, as if it is not, we may bipartition each connected component to bipartition $G$.
>>Now taking some connected graph $G$ that has no odd cycles.
>>Now choose some spanning tree $T$ that spans $G$. We know that we can bipartition $T$ into $V(E) = V(T) = X\sqcup Y$. Now observe that if we add back an edge to the spanning tree and form a cycle, if the edge connects two vertices in $X$ or in $Y$, then the cycle will be odd, which contradicts the assumption on $G$. Therefore this bipartition is a valid bipartition of all of $G$.

