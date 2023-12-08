# Graded Assignment 11

Q1)
Solve the following linear programming problem by graphical method. Find out the correct vertex that minimize the objective function?

Minimize Z = 20x + 50y subject to constraints:

x + 2y ≥ 10

3x + 4y ≤ 24

x ≥ 0, y ≥ 0
<br>

A1) (4,3)
__________________________________________________________________________________________________________________________
Q2) 
A plant manufacture produces two types of products A and B and sells them at a profit of Rs. 5 per item on type A and Rs. 3 per item on type B. 
Each product is processed on two machines G and H. One item of type A requires one minute of processing time on G and two minutes on H; 
One item of type B requires one minute on G and one minute on H. Machine G is available for not more than 5 hours 40 minutes, 
while machine H is available for 7 hours 20 minutes during any working day.

Find the formulation of LPP to Maximize the total profit?

Let X1 be the number of item produced of type A and X2 be the number of item produced of type B.

Maximize: 
Z=5X<sub>1</sub> + 3X<sub>2</sub>
<br>

A2)
X<sub>1</sub> + X<sub>2</sub> ≤ 340

2X<sub>1</sub> + X<sub>2</sub> ≤ 440

X<sub>1</sub> ≥ 0 ,X<sub>2</sub> ≥ 0

Let X1 be the number of products of type A and X2 be the number of products of type B.

Maximize: Z=5X<sub>1</sub> + 3X<sub>2</sub>
__________________________________________________________________________________________________________________________
Q3)
Find the max-flow in the following transport network, where a is the source and z is the destination?
<br>![pdsac](https://github.com/NebulaTris/pdsa-iitm/assets/94922914/907fb31d-a5b7-453a-b05e-a461dec49ea0)
<br>
A3) 13
__________________________________________________________________________________________________________________________
Q4)
Find the min-cut of the transport network in question 3?
<br>
A4) {(b,d), (e,z), (c,z)}
__________________________________________________________________________________________________________________________
Q5)
Which of the following set of vertices can make the graph Bipartite ?
<br>![pdsaa](https://github.com/NebulaTris/pdsa-iitm/assets/94922914/bfe0ff0e-168e-4dff-90c1-2d13b33cb0d7)
</br>
A5) {a, f, d, g} {b, e, c, h}
__________________________________________________________________________________________________________________________
Q6) Let G be a simple graph with 25 vertices and 50 edges. The size of the minimum vertex cover of G is 10. What is the size of the maximum indepen­dent set of G ?<br>
A6) 15
__________________________________________________________________________________________________________________________
Q7) Two CNF formulas are given. Choose the correct statement ?</br>
<img width="626" alt="image" src="https://github.com/NebulaTris/pdsa-iitm/assets/94922914/0610f8bc-abe8-4fe1-bcd0-46d2c4b9825c">
</br>
A7) (I) is satisfiable (II) is unsatisfiable
__________________________________________________________________________________________________________________________
Q8) In the Ford-Fulkerson algorithm to find the maximum flow, what do all edges in the residual graph having value 0 denote?</br>
A8) Edges with flow equal to maximum capacity
__________________________________________________________________________________________________________________________
Q9)Assume there are n teachers and 2n subjects. Each teacher has to teach exactly 2 subjects. Their preferences are modelled as a directed graph 
G, such that there exists an edge from a teacher node T<sub>i</sub> to a subject node S<sub>j</sub> in G, if T<sub>i</sub> prefers teaching S<sub>j</sub>. 
How can this problem be modelled as a network flow problem?
</br>
A9) It can be modelled as a network flow problem, where the source node is connected to every teacher node in G with capacity of 2, and every subject node in 
G is connected to the sink node with capacity of 1.

__________________________________________________________________________________________________________________________
Q10) Let C be a problem that belongs to the class NP. Then which one of the following is TRUE?</br>
A10)
- [x] If C is NP-Hard, then it is NP-complete.
- [x] If every problem in NP is reducible to C in polynomial time then C is NP-complete.
__________________________________________________________________________________________________________________________
