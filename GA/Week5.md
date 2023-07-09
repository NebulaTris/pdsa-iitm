# Graded Assignment 5

Q1)
**Transitive closure(v)** - If there is at least one path between vertex **i** to **j** or **i == j** then **v[i][j] = 1** otherwise **0**. What is the transitive closure for the given graph?
<br>![W5GA1](https://github.com/NebulaTris/pdsa-iitm/assets/94922914/3379f7cd-b8f0-40d2-aeac-a2b32633962f)
<br>
A1) <br>
| 1 | 1 | 1 | 1 |
|---|---|---|---|
| 1 | 1 | 1 | 1 |
| 1 | 1 | 1 | 1 |
| 0 | 0 | 0 | 1 |
__________________________________________________________________________________________________________________________
Q2) How can we use the Floyd-Warshall algorithm for all-pairs shortest paths to detect whether a graph has a negative cycle?<br><br>
A2)
Check if any shortest path entry **A[i][i]** is negative.
__________________________________________________________________________________________________________________________
Q3)
Suppose we have a weighted undirected graph with a negative weight cycle. Which of the following is correct?
</br><br>
A3)
Both Kruskal's algorithm and Prim's algorithm can be used to compute the minimum-cost spanning tree.
__________________________________________________________________________________________________________________________
Q4)
We can use Breadth First Search (BFS) instead of Dijkstra's algorithm to find out the shortest path from the given source node to every other node only ______.
<br><br>
A4)
When all the edge weights are equal.
__________________________________________________________________________________________________________________________
Q5)
Which of the following statement is/are true?
</br></br>
A5)
- [x] Dijkstra’s algorithm doesn’t work for graphs with negative weights
- [x] Floyd Warshall algorithm can detect negative weight cycle.
- [x] Floyd Warshall algorithm works with negative weights but without negative cycle.
__________________________________________________________________________________________________________________________
Q6)
Suppose we run Prim's algorithm and Kruskal's algorithm on a graph G and these two algorithms produce minimum-cost spanning trees <i>T<sub>P</sub></i> and <i>T<sub>K</sub></i>, respectively.
 </br>
> (I) <i>T<sub>P</sub></i> may be different from <i>T<sub>K</sub></i> if some pair of edges in G have the same weight.</br>
> (II) <i>T<sub>P</sub></i> is always the same as <i>T<sub>K</sub></i> if all edges in G have distinct weights.
 </br>
 Which of the following is true? </br></br>
A6)
Both (I) and (II) are correct.

__________________________________________________________________________________________________________________________
Q7)
Consider the graph shown below. 
 </br>
 ![W5GAQ7](https://github.com/NebulaTris/pdsa-iitm/assets/94922914/1ac13392-d47c-4be3-88a7-69a059f0ccf3)
 </br>
 Which one of the following can be the sequence of edges added, in that order, to create a minimum spanning tree using Kruskal’s algorithm?</br><br>
A7)
- [x] (a,b) (d,f) (b,f) (d,c) (d,e)
- [x] (a,b) (d,f) (d,c) (b,f) (d,e)
- [x] (d,f) (a,b) (d,c) (b,f) (d,e)
- [x] (d,f) (a,b) (b,f) (d,c) (d,e)
__________________________________________________________________________________________________________________________
Q8)
Consider the given weighted adjacency matrix <i>w</i> for a complete undirected graph with vertex set <b> {0, 1, 2, 3, 4} </b>. Where <i> w[i][j], i ≠ j </i> in the matrix is the weight og the edge (i,j).</br>
![W5GAQ8](https://github.com/NebulaTris/pdsa-iitm/assets/94922914/89380c1f-a034-409d-a843-a8f50d62c6a0)
 </br>
What is the weight of the minimum spanning tree for the given graph? </br>
A8)
**7**
__________________________________________________________________________________________________________________________
Q9)
Which of the following statement(s) is/are true about the spanning tree of a connected graph? </br></br>
A9)
- [x] A spanning tree is a connected acyclic graph.
- [x] A spanning tree for an n vertex graph has exactly n-1 edges.
- [x] Adding an edge to a spanning tree must create a cycle.
- [x] In a spanning tree, every pair of nodes is connected by a unique path
__________________________________________________________________________________________________________________________
Q10)
Consider the following weighted adjacency list **WList** for a directed and connected graph. What will be the path weight of the shortest path from 1 to 3?
</br>
![W5GAQ10](https://github.com/NebulaTris/pdsa-iitm/assets/94922914/bf0746d6-88f2-468a-a3cf-81a09488fed6)
</br>
A10)
**5**
__________________________________________________________________________________________________________________________
