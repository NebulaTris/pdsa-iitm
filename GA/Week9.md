# Graded Assignment 9

Q1)
Consider product of three matrices A, B and C having size p X q, q X r and r X s respectively. Which of the following statements is/are true?<br><br>
A1) 
- [x] Computing (AB)C and A(BC) both take eqaul time if p=q=r=s.
- [x] If (1/q + 1/s) < (1/p + 1/r) then (AB)C takes less time than A(BC)
- [x] (AB)C takes pr(q+s) steps to compute
__________________________________________________________________________________________________________________________
Q2) 
Consider four matrices M1,M2,M3 and M4 of dimension p X q, q X r, r X s, and s X t respectively, where p,q,r and s are distinct values. IN How many ways can we evaluate the product of M1,M2,M3,and M4 if each step consist of multiplying two matrices?
<br>
A2)
5

__________________________________________________________________________________________________________________________
Q3)
Consider the following function f(seq) , where seq is a list of integers.
```python
def f(seq):
    n = len(seq)
    L= [0]*(n-1)+[1]
    for i in range(n-2,-1,-1):
        if seq[i]<seq[i+1]:
           L[i]=1+L[i+1]
        else:
           L[i] = 1
    return(max(L))
```
Which of the following statements is/are true?
<br>
A3)
- [x] The function returns the length of the longest continguous increasing sequence of numbers in the list.
- [x] The function takes O(n) to return the output.
- [x] The algorithm uses the dyanmic programming paradigm.

__________________________________________________________________________________________________________________________
Q4)
Which of the following statements is/are true about the edit distance problem?
<br>
A4)
- [x] It can be solved using dynamic programming method.
- [x] The edit distance will be zero only when the two strings are equal.
- [x] The maximum edit distance between the two strings is equal to the length of the larger string.

__________________________________________________________________________________________________________________________
Q5)
What is the length of the longest common subsequence of strings ABCBDABACD and BDCABADCD?
<br>
A5)
7

__________________________________________________________________________________________________________________________
Q6)
Consider the following grid.<br>
(0,0)

|  . |   |   |   |   |
|---|---|---|---|---|
|   |   |   |   |   |
|   |   |   |   |   |
|   |   |   |   |   |
|   |   |   |   |   |
|   |   |   |   |   |
|   |   |   |   |   |
|   |   |   |   |   |
|   |   |   |   |   |
|   |   |   |   | .  |

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(5,10)
<br>
How many unique paths are available from (0,0) to (5,10) ? One condition is that you can only travel one step right or two-step down at a time.
A6)
252

__________________________________________________________________________________________________________________________
Q7)
The number n is to be created by adding the elements(one element can be used more than one time) of a list of positive integers L of length m.
```python
def nsum(n, L):
    if n == 0:
        return []
    if n < 0:
        return None
    for i in L:
       x = nsum(n-i, L)
       if x != None:
           return x+[i]
    return None
```
What will be the asymptotic complexity of the above recursive function without and with memoization respectively?
</br>
A7)
O(m<sup>n</sup>), O(mn)

__________________________________________________________________________________________________________________________
<b> Questions 8 to 10 are based on the common theme</b><br>
<p> The subset sum problem is defined as follows. Given a list L of n non-negative integers and a value k, determine if there is a subset of elements from the list L whose sum is equal to k. Consider the following solution code where T is a 2-dimensional Boolean array, with n+1 rows and k+1 columns. T[i][j], 1 <= i <= n, 1 <= j <= k is True, if and only if there is a subset of {a1,a2,....,ai} whose sum is equal to j.</p>
 
```python
def subsetSum(L,k):
    n = len(L)
    T = [[False for x in range(k+1)] for y in range(n+1)]
    for i in range(n+1):
        T[i][0] = True
    for i in range(1, n+1):
        for j in range(1,k+1):
            if L[i-1]>j:
                T[i][j] = T[i-1][j]
            else:
                T[i][j] = T[i-1][j] or T[i-1][j - L[i - 1]]
    return ____
 ```
__________________________________________________________________________________________________________________________
Q8)
In the given code, which entry of T should be returned ? If True, it implies that there is a subset of elements whose sum is equal to k.
</br>
A8)<br>
T[n][k]

__________________________________________________________________________________________________________________________
Q9)
Function subsetSum() is an example of :
</br>
A9)
A dynamic programming algorithm
__________________________________________________________________________________________________________________________
Q10)
What is the time complexity of function subsetSum() ?
</br>
A10)
O(nk)
