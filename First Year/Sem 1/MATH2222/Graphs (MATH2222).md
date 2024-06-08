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

---
TODO: Catchup!

---

>[!theorem]
>*Hall's theorem* states that there is a matching of $X$ into $Y$ if and only if, for all subsets $T\subset X$,
>$$\begin{align*}|T|&\le |N(T)|,\end{align*}$$
>where $N(T)\subset Y$ is the set of neighbours of vertices in $T$.
>
>>[!proof]
>>First direction: clear (TODO in catchup).
>>
>>Now for the converse, suppose that for all $T\subset X$, $|T|\le |N(T)|$. We must show that there is a matching of $X$ into $Y$.
>>Consider two cases. In the first case, we have that for all proper subsets $T\subset X$, $|T| < |N(T)|$. In the second case, we have that for some proper subset $T\subset X$, $|T| = |N(T)|$. We will construct a matching in each case.
>>
>>**Case 1.**
>>Let $x_{1}\in X$. We know by assumption, if we let $T=\left\{x_{1}\right\}$, that $x_{1}$ has some connected $y_{1}$. Now let $X' = X-\left\{x_{1}\right\},\ Y' = Y-\left\{y_{1}\right\}$. Now let $G'$ be the subgraph of $G$ with vertices $X'\sqcup Y'$, and all edges of $G$ that have endpoints in $X'\sqcup Y'$.
>>We want a matching of $X'$ into $Y'$, noting that $|X'|<|X|$. Note that $G'$ satisfies the assumption of Hall's theorem, i.e., for all subsets of $T'\subset X'$, $|T'|\le |N'(T)|$.
>>Therefore, the bipartite graph of $G'$ has a matching of $X'$ into $Y'$. Together with the edge $e=x_{1}y_{1}$, this gives a matching of $G$.
>>
>>**Case 2.**
>>Assume there is some $T\subset X$ such that $|T|=|N(T)|$. We know that for any $S\subset T$, $|S|\le |N(S)|$. So, by induction hypothesis we have a matching for this. Now let $G'$ be the graph given by removing $T$ and its neighbours from $G$, i.e., the remainder of the graph after matching $T$. We must show that $G'$ has a matching of $X'=X-T$ into $Y'=Y-N(T)$.
>>Let $V\subset X'$. Note that $N_{G'}(V) = N_{G}(V\cup T) - |N(T)|\ge |V\cup T| - |T| = |V|$ as $V,T$ are disjoint. So then $N_{G'}(V)\ge |V|$, so $G'$ satisfies Hall's theorem. Therefore we have a matching.
>>
>>In both cases, we have constructed a matching, which completes our proof.
>>$$\begin{align*}
\ \tag*{$\blacksquare$}
\end{align*}$$

>[!remark]
>Hall's theorem regards the question, *when is there a matching of $X$ into $Y$*?

---

>[!question]
>Suppose that you want to schedule lectures times for classes so that no student has any course conflicts. How many class times do you need?
>
>>[!remark] Consider...
>>Consider the graph $G$ where the vertices are the classes, and two classes $v,w$ have an edge if they have a student in common.
>>![[Graphs (MATH2222) 2024-05-07 13.40.42.excalidraw]]
>>We want to assign a time (represented by a colour) to each class (vertex) such that two classes (vertices) with a common student (edge) have different times (colours). How many colours do we need?


>[!def]
>A *k-colouring* of $G$ is a function $f : V(G) \longrightarrow S$, where $|S|=k$ and $S$ is the set of colours.

>[!def]
>A **k-colouring** is *proper* if $f(v)\ne f(w)$ whenever $(v-w)\in E(G)$.

>[!def]
>The *chromatic number* of $G$ is the smallest number of colours needed to properly colour $G$. I.e., the minimum $k$ such that a proper k-colouring exists for $G$. We write $\chi(G)$ to represent the chromatic number of $G$.

>[!example]
>What is $\chi(T)$ for a tree $T$?
>
>>[!check] Solution.
>>Note that $T$ is bipartite, so we may colour one bipartition white and the other black.
>
>>[!remark]
>>This goes the other way! All graph with $\chi(G)=2$ are bipartite.
>>>[!proof]
>>>Let $X$ be all the vertices with one colour, and $Y$ be the vertices with the other colour. Then we have a bipartition, and $X,Y$ are both independent. So $G$ is bipartite.

>[!example]
>What about graphs with $\chi(G)=3$?
>A graph $G$ with $\chi(G)=3$ can be partitioned into three independent sets.
>Note that any odd cycle has $\chi(G)=3$, which can be seen visually.
>
>What about graphs with $\chi(G)=10$?
>The complete graph on 10 vertices, $K_{10}$, has this chromatic numbers.
>>[!remark]
>>In general $\chi(K_{n})=n$.
>
>>[!seealso] Exercise.
>>If $G$ has $n$ vertices, but $G\ne K_n$, then $\chi(G)<n$.

>[!def]
>Instead of just considering $\chi(G)$, we may consider the following function,
>$$\begin{align*}
>\chi_{G} : \mathbb{Z}_{\ge 0} \longrightarrow \mathbb{Z}_{\ge0},\\
>\chi_{G}(l) &= \#\text{ of proper }l\text{-colorings of }G.
>\end{align*}$$
>>[!example]
>>If we take the graph $U$ with $n$ vertices and no edges, then $\chi_{U_{n}}(l)=l^{n}$.
>
>>[!example]
>>If we take the complete graph $K_{n}$ with $n$ vertices.
>>For $l<n$, we have $\chi_{K_{n}}(l)=0$. We then have $\chi_{K_{n}}(n) = n!$. Then, for $l>n$, we have $\chi_{K_{n}}(l) = l(l-1)(l-2)\cdots(l-n+1)$.
>>More generally, we can write that,
>>$$\begin{align*}
>>\chi_{K_{n}}(l) &= l(l-1)(l-2)\cdots(l-n+1)\\
>>&= \binom{l}{n}n!
>>\end{align*}$$
>
>>[!example]
>>Now take $T$ to be a tree with $n$ vertices.
>>Think about constructing $T$ by starting with a single vertex, and at each stage, adding a single new vertex connected by an edge to an old vertex.
>>We have $x$ colours for the first vertex. We have $x-1$ colours for the next vertex, and $x-1$ for the next, and so on. So then,
>>$$\begin{align*}
>>\chi_{T}(x) &= x(x-1)^{n-1}.
\end{align*}$$

>[!question]
>Given some graph $G$, how might we count the number of proper $l$-colourings of it?

>[!theorem]
>The function $\chi_{G} : l \longrightarrow \text{\# of proper }l\text{-colorings of }G$ is **always a polynomial**, called the *chromatic polynomial of $G$*.
>We can therefore evaluate this polynomial even on values such as complex numbers, negative numbers, etc. **This is cool!**
>>[!proof]
>>We can do this using the inclusion-exclusion principle.
>>For each edge $e=vw\in E(G)$, let $C_{e} = \left\{k\text{-colorings of }G\text{ that are "bad" at }e\right\}$ $= \left\{f : V(G) \longrightarrow \left\{1,2,\cdots,k\right\} \mid f(v)=f(w)\right\}$. Note that a $k$-colouring of $G$ is not proper if and only if $f\in\bigcup_{e\in E(G)}C_{e}$. So the number of proper colourings is,
>>$$\begin{align*}
>>\chi_{G}(k) &= \left|U - \bigcup_{e\in E(G)}C_{e}\right|.
>>\end{align*}$$
>>So then,
>>
>>
>> 
>> $$\begin{align*}
>> \chi_{G}(k) &= \sum\limits_{S\in E(G)}(-1)^{|S|}\left|\bigcap_{e\in S}C_{e}\right|.
>> \end{align*}$$
>> So, let $S\subset E(G)$. Now we would like to compute $\left|\bigcap_{e\in S}C_{e}\right|$.
>> We interpret this set as the set of all colourings so that all edges in $S$ are bad. To do this, we may consider the graph $G_{S}$, with $V(G_{S})=V(G)$, $E(G_{S}) = S$. If $G$ is coloured badly at all edges in $S$, then $G_{S}$ has some connected components that are all the same colour. So then, if $c(G_{S})$ is the number of connected components in $G_{S}$,
>> $$\begin{align*}
>> \left|\bigcap_{e\in S}C_{e}\right| &= k^{c(G_{S})}
>> \end{align*}$$
>> So then,
>> $$\begin{align*}
>> \chi_{G}(k) &= \sum\limits_{S\in E(G)}(-1)^{|S|}k^{c(G_{S})}.
>> \end{align*}$$
>> Therefore $\chi_{G}$ is a polynomial.

# Planar Graphs
>[!question]
>*The Utility Problem*
>Suppose that we have three houses, $A,B,C$, and three utilities $X,Y,Z$ that each house must be connected to. Can we connect all the houses to the utilities without crossing any paths?
>![[Graphs (MATH2222) 2024-05-10 16.10.31.excalidraw]]

>[!question]
>*4-colourings of maps*
>Can every map be 4-coloured?

>[!def]
>A *curve* from $u$ to $v$ in $\mathbb{R}^{2}$ is the image of a continuous function $f : [0,1] \longrightarrow \mathbb{R}^{2}$, where $f(0)=u,f(1)=v$.
>The curve is *simple* if $f$ is injective, except possibly when $u=v$.

>[!def]
>A *drawing* of a graph $G$ is another graph $H\cong G$ such that each vertex of $H$ is a point in $\mathbb{R}^{2}$ and each edge with endpoints $u,v$ is a curve from $u$ to $v$.

>[!def]
>In a drawing, two edges $e_{1},e_{2}$ *cross* if they intersect somewhere other than a vertex endpoint.

>[!def]
>A *planar graph* $G$ is a graph that has a drawing without crossings.
>Such a drawing is sometimes called a *plane graph*.

>[!def]
>A set $R\in \mathbb{R}^{2}$ is *path-connected* if, for all points $u,v$ in $R$, there is a curve from $u$ to $v$ lying entirely in $R$ (with endpoints $u,v$).

>[!theorem]
>*The Jordan Curve Theorem*
>Every simple, closed curve in $\mathbb{R}^{2}$ partitions its compliment into two path-connected regions, known as the interior and the exterior.
>
>Equivalently, every plane graph isomorphic to a circle has two faces; one is bounded and the other is unbounded.

>[!remark]
>Now, in addition to considering vertices and edges, we may also consider faces.

>[!def]
>A *face* $f$ of a plane curve $G$ is a maximal path-connected subset of $\mathbb{R}^{2}$ that does not intersect any vertex or edge in $G$.

>[!question]
>Which graphs are planar?

>[!theorem]
>*Euler's Characteristic Formula*
>If $G$ is a connected plane graph with $v$ vertices, $e$ edges and $f$ faces, then we have that,
>$$\begin{align*}
>v-e+f &= 2.
>\end{align*}$$
>
>>[!proof]
>>This will be proven by strong induction on the number of cycles in $G$.
>>**Base case.**
>>If $G$ is connected and has no cycles, then $G$ is a tree. So then $f=1$, $e=v-1$. Therefore $v-e+f = 2$.
>>**Inductive Step.**
>>Let $G$ have a cycle $C$ containing an edge $\alpha$. Since $C$ is a cycle, the Jordan curve theorem says that this edge $\alpha$ bounds two faces, $f_{1},f_{2}$.
>>Now consider the plane graph $G'=G-\alpha$. We merge $f_{1}$ and $f_{2}$ to get a new face $F=f_{1}\cup f_{2}\cup \alpha$.
>>Now, $G'$ is still connected as we removed an edge from a cycle, and $G'$ has fewer cycles than $G$. Then, by our induction hypothesis, $v'-e'+f'=2$. With $f=f'+1,e=e'+1,v=v'$, we then have that,
>>$$\begin{align*}
>>v-e+f &= v'-(e'+1)+f'+1 = 2.
\end{align*}$$

>[!remark]
>This theorem imposes constraints on the number of edges in a planar graph with $v$ vertices.

>[!theorem]
>Let $G$ be a simple planar graph with $n\ge 3$ vertices. The $G$ has at most $3n-6$ edges.
>>[!proof]
>>For $n=3$, the theorem is true by inspection (all $n=3$ graphs are planar).
>>Now suppose that $G$ is the maximal plane graph with $n\ge4$ vertices (the graph with the most edges that is still planar). It immediately follows that $G$ is connected. We would like to show that $G$ has at most $3n-6$ edges.
>>By Euler's Characteristic Formula, $v-e+f=2$. Since $G$ is simple, each face bounds at least three edges. So if $F$ is the set of faces of $G$ and we sum,
>>$$\begin{align*}
>>\sum\limits_{f'\in F}\#\text{edges in }f'&\ge 3f.
>>\end{align*}$$
>>However, each edge bounds two faces, so the above sum is twice the number of edges.
>>$$\begin{align*}
>>2e&\ge 3f.
>>\end{align*}$$
>>Applying this in Euler's formula,
>>$$\begin{align*}
>>f &= 2+e-v\\
>>f=2+e-v&\le \frac{2}{3}e\\
>>\frac{1}{3}e &\le v-2\\
>>e &\le 3v-6.
\end{align*}$$

>[!corollary]
>$K_{5}$ is not planar.
>>[!proof]
>>$K_{5}$ has $v=5,e=10$.
>>But if $K_{5}$ were planar, we would need $10\le 3(5)-6$. This is not true, so $K_{5}$ is not planar.

>[!remark]
>In a bipartite graph, there can be no odd cycles, so then each face must have at least $4$ eges.

>[!theorem]
>Suppose that $G$ is a planar graph with no 3-cycle, and $G$ has $v$ vertices and $e$ edges. Then,
>$$\begin{align*}
>e&\le 2v-4.
>\end{align*}$$
>The proof of this is similar to the proof without the restriction of no 3-cycles.

>[!corollary]
>$K_{3,3}$ is not planar.
>>[!proof]
>>$K_{3,3}$ is bipartite and therefore has no odd cycle. So then if $K_{3,3}$ were planar, we would have $9\le 2(6)-4$. This is not true, so then $K_{3,3}$ is not planar.

>[!remark]
>If $G$ has $K_{5}$ or $K_{3,3}$ as a subgraph, then $G$ is not planar.

>[!remark]
>Subdividing and unsubdividing does not change the planarity of a graph.
>So then if $G$ contains a subgraph that is a subdivision of $K_{5}$ or $K_{3,3}$, then $G$ is not planar.

>[!theorem]
>*Kuratowski's theorem*
>$G$ is planar if and only if $G$ has no subgraph that is a 'topological' $K_{5}$ or $K_{3,3}$.
>>[!proof]
>>We have already proven one direction of this. The other direction is somewhat difficult to prove.

>[!quote]
>Graph theory is loaded with **zillions** of such statements.
>	*- Tony Licata, 2024*

# The Art Gallery Problem
>[!question]
> How can you cover all of the floorplan of an art gallery with unmoving security guards?

>[!remark]
>Any floor plan is a polygon, and any convex polygon needs only one guard.

>[!question]
>What is the minimum number of guards needed to be sure that a gallery whose floor plan is an $n$-gon is completely guarded.

**Lower bounds.**
If we find an $n$-gon in $\mathbb{R}^{2}$ that requires $k$ guards, then the answer is at least $k$.
![[Graphs (MATH2222) 2024-05-15 13.20.52.excalidraw|300]]
By the above polygon, we have that any $n$-gon gallery potentially requires at least $\lfloor\frac{n}{3}\rfloor$.

>[!theorem]
>Any $n$-gon can be guarded by $\lfloor \frac{n}{3}\rfloor$ guards.
>>[!proof]
>>It will follow from the proof that the guards can be placed at vertices.
>>
>>**Step -1**:
>>If the gallery is a triangle, we may place a guard at any vertex to guard it.
>>
>>**Step 0**:
>>We can triangulate our gallery by adding edges such that every face is a triangle except for the outer region (and the result is a plane graph).
>>To prove this, we require that there must be a chord between two non-neighbouring vertices that lies completely in the gallery. This can be proven by the sweeping flashlight analogy.
>>
>>**Step 1**:
>>The new triangulated graph $G$ can be three-coloured.
>>This can be proven inductively by considering how we originally triangulated the graph. Split the graph into half and apply inductive hypothesis to the smaller graphs, then equate the required colours at the split.
>>
>>**Step 2**:
>>Every triangle has one of each colour of the vertex, so by pigeonhole, there is some colour used on $\lfloor \frac{n}{3}\rfloor$ vertices. So put a guard on each of these vertices. Now each triangle is guarded, so the whole graph is guarded.


