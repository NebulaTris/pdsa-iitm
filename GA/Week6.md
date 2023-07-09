# Graded Assignment 6

Q1)
Consider a list L with k distinct numbers and a heap H with size n. What is the nearest upper bound for checking if every number in L is present in the heap H?<br><br>
A1) O(kN)
__________________________________________________________________________________________________________________________
<b>Use the below information for the Questions 2 to 7</b><br></br>

Identify the below arrays as min heap, max heap or none. Type min if it is a min heap, max if it is a max heap, none otherwise.
__________________________________________________________________________________________________________________________
Q2) 
| 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 |
|---|---|---|---|---|---|---|---|
<br>
A2)
min

__________________________________________________________________________________________________________________________
Q3)
| 67 | 65 | 43 | 54 | 6 | 2 | 1 | 19 | 5 |
|----|----|----|----|---|---|---|----|---|
<br>
A3)
max

__________________________________________________________________________________________________________________________
Q4)
| 88 | 77 | 66 | 55 | 44 | 33 | 22 | 11 |
|----|----|----|----|----|----|----|----|
<br>
A4)
max

__________________________________________________________________________________________________________________________
Q5)
| 1 | 2 | 3 | 4 | 8 | 5 | 6 | 7 |
|---|---|---|---|---|---|---|---|
<br>
A5)
min

__________________________________________________________________________________________________________________________
Q6)
| 4 | 1 | 2 | 3 | 5 | 6 | 7 | 8 |
|---|---|---|---|---|---|---|---|
<br>
A6)
none

__________________________________________________________________________________________________________________________
Q7)
Which of the following will correctly represent the max-heap, after inserting elements 1, 2, 3, 5, 7, 6 and 4 in the given order, starting with an empty heap?
</br></br>
A7)
| 7 | 5 | 6 | 1 | 3 | 2 | 4 |
|---|---|---|---|---|---|---|

__________________________________________________________________________________________________________________________
Q8)
What is the nearest worst case upper bound to search for an element in a heap and in a binary search tree, respectively? Consider that the total number of elements are 
n and the binary search tree is balanced(in the form of a complete binary tree).
 </br></br>
A8)
O(n), O(logn)
__________________________________________________________________________________________________________________________
Q9)<br>
![W6GA5](https://github.com/NebulaTris/pdsa-iitm/assets/94922914/647b3c51-146f-4a42-9255-5440957a52a7)<br><br>
Above code is an incorrect implementation of max_heap. Which of the following lines of code if replaced for the given line numbers will correct the above code?
</br><br>
A9)<br>
![W6GA5 a](https://github.com/NebulaTris/pdsa-iitm/assets/94922914/bf083f82-5b3a-4344-b2b7-b86e29fd2c8b)

__________________________________________________________________________________________________________________________
Q10)
Consider a max heap, represented as the array, | 40 | 30 | 18 | 20 | 15 | 16 | 17 | 10 | 4 |. Now consider that a value 25 is inserted into this heap. After insertion, the new heap will be
</br></br>
A10)
| 40 | 30 | 18 | 20 | 25 | 16 | 17 | 10 | 4 | 15 |
|----|----|----|----|----|----|----|----|---|----|

__________________________________________________________________________________________________________________________
Q11)
Pre-Order traversal of binary search tree is 15,10,12,11,20,18,16,19. Which one of the following is the post-order traversal of the binary search tree?
 </br></br>
A11)
11,12,10,16,19,18,20,15
__________________________________________________________________________________________________________________________
Q12)
What form of tree traversal does the function traverse(root) implement, where root is the root node of a binary search tree?
 </br>
 ![W6GA8](https://github.com/NebulaTris/pdsa-iitm/assets/94922914/c83730d4-9980-42e5-b1cc-b5c0837fc635)
 </br></br>
A12)
Post-order
__________________________________________________________________________________________________________________________
Q13)
Consider a max-heap H with n elements and ℎ height. What is the nearest upper bound to remove the maximum element from max-heap H? [MSQ]
 </br></br>
A13)
- [x] O(h)
- [x] O(logn)
__________________________________________________________________________________________________________________________
Q14)The given code implements a priority queue using a sorted list. Which of the following is the correct implementation of delete_max operation of an element from the priority queue? Note that the higher the number, the higher it's priority ?
 </br>
A14)</br>
![W6GA10 c](https://github.com/NebulaTris/pdsa-iitm/assets/94922914/a78a5520-d16c-42e7-b614-d570222ca585)

__________________________________________________________________________________________________________________________
