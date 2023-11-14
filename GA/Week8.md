# Graded Assignment 8

Q1)
In an array A, two elements A[i] and A[j] form an inversion pair, if A[i] > A[j] for i < j.<br>
Which of the following input arrays will have maximum and minimum inversion pairs respectively?<br>

I. Array sorted in ascending order.<br>
II. Array sorted in descending order.<br>
A1) II and I
__________________________________________________________________________________________________________________________
<b>Question 2 & 3</b><br>

Consider the following strategy to solve a problem of input size n.

Divide the problem into 6 sub-problems, each of size n/6. Number of steps required to combine these 6 solutions is 2n + 12. We apply this strategy recursively till the sub-problems can not be further divided into sub-problems.
__________________________________________________________________________________________________________________________
Q2) 
What will be the nearest upper bound for the above algorithm?
<br>
A2)
O(nlogn)

__________________________________________________________________________________________________________________________
Q3)
If we divide the problem into 4 sub-problems of size n/2 and number of steps required to combine the solutions is 15 using some optimizations, what will be the nearest upper bound of this algorithm?
<br>
A3)
O(n<sup>2</sup>)

__________________________________________________________________________________________________________________________
<b>Question 4 & 5</b><br>
![W8GT4 5](https://github.com/NebulaTris/pdsa-iitm/assets/94922914/26459246-21dd-4b29-8553-7725522aeb5b)
__________________________________________________________________________________________________________________________
Q4)
Which of the following options describe the recurrence relation that will give the above recurrence tree, if the cost to combine solutions at each level is equal to 2n and the cost to compute the solution of sub-problem at leaf nodes is Θ(1)?
<br>
A4)
- [x] T(n) = T(n/3) + T(2n/3) + 2n
- [x] T(n) = T(n/3) + T(2n/3) + O(n)

__________________________________________________________________________________________________________________________
Q5)
If O(f(n)) is the upper bound for the above recurrence relation. What is the value of f(n).
<br>
A5)
nlogn
