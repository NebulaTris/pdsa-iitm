# Graded Assignment 3

Q1)
Consider the Quick sort algorithm in which the partitioning procedure splits elements into two sub-arrays and each sub-array contains at least one-third of the elements. Let T(n) be the number of comparisons required to sort array of n elements
 </br></br>
A1) O(n<sup>3</sup>)
__________________________________________________________________________________________________________________________
Q2) 
Which function correctly inserts an element after x nodes in a linked list, where each node of linked list is an object of class Node and x>=0 ? In the options below,
head is the first node in the linked list and value is the value that needs to be inserted after x nodes.
The function insertAtBeginning(head, v) inserts a node at the beginning of the list with value v .</br>
![W3GTQ2](https://github.com/NebulaTris/pdsa-iitm/assets/94922914/93ada56e-9fd0-49b5-9221-5819b39b5cb5)
 </br></br>
 A2)
- [x] A(n) = O(W(n))
- [x] A(n) = Ω(B(n))
- [x] B(n) = O(W(n))
- [x] B(n) = O(A(n))
__________________________________________________________________________________________________________________________
Q3)
Which of the following code can be used as a queue?
</br></br>
A3)
O(nlogn)
__________________________________________________________________________________________________________________________
Q4)
Consider a Quicksort implementation where we first find the median then use the median as a pivot. Assume that we have a O(n) time to find the median of an unsorted list. What will be the worst-case time complexity of this modified Quicksort to sort n distinct elements?
 </br></br>
A4) **5**</br>
Selection sort swaps min element to i = 0th position element and i = 1th position with the second minimum element from the list and so on by doing up to i = 5 we get completely sorted list.
__________________________________________________________________________________________________________________________
Q5)
 </br>
![GTQ5](https://github.com/NebulaTris/pdsa-iitm/assets/94922914/121b0318-587c-42e8-b439-f1b71d94a589)
 </br>
 The above function can be used as partitioning function for sorting an array through Quicksort. What will be the state of Array after the call 'partition([13, 18, 8, 10, 21, 7, 2, 32, 6, 19], 0, 9)' return?  </br></br>
A5)
- [x] The sort is stable and it sorts in-place
- [x] After m iterations of the for-loop, the first m elements in the list are in sorted order.
__________________________________________________________________________________________________________________________
Q6)
**Linear probing** is an open addressing scheme in computer programming for resolving hash collisions in hash tables. Linear probing operates by taking the original hash index and adding successive values linearly until a free slot is found.</br>

An example sequence of linear probing is:</br>

<i>h(k)+0, h(k)+1, h(k)+2, h(k)+3 .... h(k)+m-1</i></br>

where m is a size of hash table, and h(k) is the hash function.</br>

**Hash function**</br>

Let h(k) = k mod m be a hash function that maps an element k to an integer in [0, m−1], where m is the size of the table. Let the  ith probe position for a value k be given by the function</br>

<i>h'(k,i) = (h(k) + i) mod m </i></br>

The value of i = 0, 1, . . ., m – 1. So we start from i = 0, and increase this until we get a free block in hash table.</br>

Consider inserting the keys <i>24, 36, 58, 65, 62, 79</i> into a hash table of size <i>m = 11</i> using linear probing, the primary hash function is <i>h(k) = k mod m</i>. What will be the hash table after inserting all keys in given order? Suppose initial hash table is: </br>
[None,None,None,None,None,None,None,None,None,None,None]
 </br></br>
A6)
**O(n<sup>2</sup>)**</br>
Time complexity will be O(nlogn + n<sup>2</sup> + n) since we take higher-order term and can neglect lower order term for a large value of n, Hence O(n<sup>2</sup>) is correct complexity.
__________________________________________________________________________________________________________________________
Q7)
In a quicksort algorithm, we choose the last element in the array as pivot for partitioning. For which of the following arrays will this algorithm exhibit the worst-case behavior?
 </br></br>
A7)
- [x] Maintain a sorted list with id. Whenever a new student is added, insert the student details into the respective positon in the sorted list by id.
__________________________________________________________________________________________________________________________
Q8)
In a linked list, what is the asymptotic worst-case running time for finding the size of the list?
 </br></br>
A8)
O(logn)
__________________________________________________________________________________________________________________________
Q9)
For Quicksort on an input size n, where we always select the first element as pivot, how many partitioning levels required in worst-case and best-case, respectively?
</br>
![Screenshot from 2022-01-06 12-37-22](https://github.com/NebulaTris/pdsa-iitm/assets/94922914/b3573592-7e26-4d10-99fa-6c24f32788bf)
</br></br>
A9)
I and II both are true.
__________________________________________________________________________________________________________________________
Q10)
Consider two lists L1 and L2 both containing n integers. We need to find if lists L1 and L2 are disjoint. Two lists are disjoint, if there is no integer common in both the lists. </br>

For example.</br>

1.  L1 = [5, 2, 7 , 1] and L2 = [3, 5], these two lists are not disjoint as 5 is common in both lists.</br>

2. L1 = [2, 7, 1] and L2 = [3, 5], these two lists are disjoint as there is no integer common in both.</br>

Select the most efficient solution or solutions for this in terms of asymptotic running time complexity from the below list. 
</br>
A10)</br>
<strong>f3(n),f4(n),f2(n),f1(n),f5(n)</strong></br>
f3 < f4 < f2 < f1 < f5 by putting n = 10<sup>31</sup> we can verify this.
__________________________________________________________________________________________________________________________
