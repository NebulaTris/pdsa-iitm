# Graded Assignment 7

Q1)<br>
![W7GA1](https://github.com/NebulaTris/pdsa-iitm/assets/94922914/c06ceb45-7f74-476b-b291-25070718221a)<br><br>
Which of the following insertion order of data items will generate the above AVL tree?<br>
A1)
- [x] 1,2,3,4,5,6,7
- [x] 7,6,5,4,3,2,1
__________________________________________________________________________________________________________________________
Q2) <br>
![W7GA2](https://github.com/NebulaTris/pdsa-iitm/assets/94922914/44e35849-0b4a-4332-b8e6-7fc5d2a644e3)
<br>
For the above class <b> AVLTree</b> , if the leaf node has height 1, then which of the following options will compute the height of all nodes in the tree ? Consider that <b> self</b> is referencing  the root node of the tree.<br><br>
A2)<br>
![W7GA2 c](https://github.com/NebulaTris/pdsa-iitm/assets/94922914/3175ae19-b59d-483d-ab93-48c32db30f53)

__________________________________________________________________________________________________________________________
Q3)
A manager claims scheduling jobs based on the slack time to time taken ratio (D(i)−T(i)/T(i)) is optimum. His strategy is to complete the job which has the least slack to the time taken ratio. Choose the counter-example to prove the strategy is not optimum.
<br>
A3)<br>
T[1] = 9; D[1] = 15;<br>
T[2] = 4; D[2] = 9

__________________________________________________________________________________________________________________________
Q4)
In the Activity Selection Problem, each activity i has a start time Si and a finish time Fi where Si<Fi. Two or more activities can not perform simultaneously. Activity i and j are said to be non-conflicting if ____ .
<br>
A4)
 Si >= Fj or Sj >= Fi

__________________________________________________________________________________________________________________________
Q5)
In the table below, we have 8 activities with the corresponding start and finish times, It might not be possible to complete all the activities since their time frame can conflict. For example, if any activity starts at time 0 and finishes at time 4, then other activities can not start before 4. It can be started at 4 or afterwards. What is the maximum number of activities which can be performed without conflict?
<br>
| Activity | Start time | Finish time |
|----------|------------|-------------|
| A        | 1          | 3           |
| B        | 3          | 4           |
| C        | 0          | 7           |
| D        | 1          | 2           |
| E        | 5          | 6           |
| F        | 5          | 9           |
| G        | 10         | 11          |
| H        | 7          | 8           |
<br>
A5)
5

__________________________________________________________________________________________________________________________
Q6)
A machine has to rest for an hour mandatorily after every 5 hours of continuous work but the machine can take rest for an hour before completion of 5 hours and become available for next 5 hours. What will be value of lateness of the given list of jobs in an optimal sequence?
            
Lateness = ∑<sup>3</sup> id=0 L(i) </br>
L(i) = { if TimeDelivered(i)>TimeDue(i), TimeDelivered(i)-TimeDue(i)}</br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; {&nbsp;&nbsp;&nbsp;else, 0 }<br>
| Id | Time Required | Due |
|----------|------------|-------------|
| 0        | 2          | 10           |
| 1        | 1          | 2           |
| 2        | 4          | 8           |
| 3        | 3          | 7           |
<br>
A6)
3

__________________________________________________________________________________________________________________________
Q7)
Which of the following is/are true about Huffman code algorithm?
</br></br>
A7)
- [x] Huffman code algorithm generates prefix code.
- [x] It is based on a greedy approach.
- [x] It has the complexity of O(klogk)

__________________________________________________________________________________________________________________________
Q8)
<br>
![W7GA8](https://github.com/NebulaTris/pdsa-iitm/assets/94922914/129e4574-13b1-4243-8390-cee29126d505)
 </br>
We received a message <b>10010000010001110111100011010</b> encoded using Huffman coding of <b>a,b,c,d and e</b> generated by the given Huffman tree. Which of the following is the correct decoded message for the given encoded message?</br>
A8)
cbaababdecadc
__________________________________________________________________________________________________________________________
Q9)<br>
An entire message is created using characters from the set S = {A,B,C,D,E}. The table of the probability of each character is given below.
<br>
| Character   | A    | B    | C    | D    | E    | Total |
|-------------|------|------|------|------|------|-------|
| Probability | 0.22 | 0.34 | 0.17 | 0.19 | 0.08 | 1.0   |
<br>
A message of 1000 characters is encoded using Huffman coding. What will be the expected length of the encoded message in bits?<br>
A9)
2250

__________________________________________________________________________________________________________________________
Q10)
</br>![W7GA10](https://github.com/NebulaTris/pdsa-iitm/assets/94922914/63b1d455-6516-4552-bbb0-fe57008c66d0)
</br>
Consider the Huffman tree above for encoding. Which of the following is/are <b>invalid</b> encoding?
A10)
- [x] 10101011010100000010011
- [x] 11001110001000101000

