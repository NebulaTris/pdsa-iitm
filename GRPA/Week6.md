# GRPA 1
<img src="https://user-images.githubusercontent.com/94922914/235128688-317c7c1d-66d7-4d02-91b1-45c12c3a726c.png" width="650"/>

## Solution
```python
class min_heap:
  def __init__(self):
    self.size=0
    # The below is a list of tuples. In every tuple one value 
    # is the element from list and the second value identifies the list.
    self.arr = []

  def isempty(self):
    return True if (self.size == 0) else False
  
  # Heapify element at index i
  def heapify_down(self, i):
    n = self.size
    a = self.arr
    while (i<n):
      ss = l = 2 * i + 1
      r = 2 * i + 2  
      # ss is smaller of left and right child
      if (l<n and r<n and a[l][0] > a[r][0]):
        ss = r 
      if (ss<n and a[ss][0]<a[i][0]):
        a[i], a[ss] = a[ss], a[i]
        i = ss
      else:
        break

  def delete_min(self):
    min = self.arr[0]
    last = self.arr.pop()
    #size of heap after pop operation will reduce by 1
    self.size -= 1
    if (self.size > 0):
      self.arr[0] = last
      self.heapify_down(0)
    return min
  
  # Heapify last element in the heap 
  def heapify_up(self):
    i = self.size - 1
    while (i>0):
      parent = (i-1)//2
      if (self.arr[i][0] < self.arr[parent][0]):
        self.arr[i], self.arr[parent] = self.arr[parent], self.arr[i]
        i = parent
      else:
        break
  
  # Insert to min heap
  def insert_min_heap(self, x):
    self.arr.append(x)
    self.size += 1
    self.heapify_up()

def mergeKLists(L):
  k = len(L)
  h = min_heap()
  finalList = []
  
  # Insert first element from each k lists to heap.
  for i in range(k):
    tup = (L[i][0], i)
    h.insert_min_heap(tup)
  
  kPointers = [1 for i in range(k)] # As all 0th elements will be inseted into the heap of size k
  while (not h.isempty()):
    tup = h.delete_min()
    finalList.append(tup[0])
    listNumber = tup[1]
    if (kPointers[listNumber] < len(L[listNumber])):
      tup = (L[listNumber][kPointers[listNumber]], listNumber)
      h.insert_min_heap(tup)
      kPointers[listNumber] += 1
  
  return finalList
k = int(input())
LL=[]
for i in range(k):
    subL = [int(item) for item in input().split(" ")]
    LL.append(subL)
print(*mergeKLists(LL))
```
# GRPA 2
Write a Python function maxLessThan(root, K), that accepts the root node of the binary search tree and a number K and returns the maximum number less than or equal to K in the tree. If K is the less than every number in the tree return None . Each node in the tree is an object of class Tree , and the tree will have at least one node.</br>
<img width="650" src="https://user-images.githubusercontent.com/94922914/235130590-ed7965dc-9bfc-44f5-b6de-0c78e5896c42.png"/>
<img width="650" src="https://user-images.githubusercontent.com/94922914/235130612-1d9ebdac-42b8-4d83-b51d-62c29f9bda34.png"/>


## Solution
```python
class Tree:
  #constructor
  def __init__(self, initval=None):
    self.value = initval
    if self.value:
      self.left = Tree()
      self.right = Tree()
    else:
      self.left = self.right = None
    return
  
  #Only empty node has value None
  def isempty(self):
    return(self.value == None)
  
  #Leaf nodes have both children empty
  def isleaf(self):
    return(self.value != None and self.left.isempty() and self.right.isempty())
  
#insert element to BST
def insertToBST(root, x):
  # Tree should have atleast one element.
  temp = root
  while (not temp.isempty()):
    if (x < temp.value):
      temp = temp.left
    else:
      temp = temp.right

  temp.value = x
  temp.left = Tree()
  temp.right = Tree()
# Method 1
# Insert K in the binary search tree {O(log n)}, then do inorder traversal of the tree in a List L {O(n)}.
# Then search for K in the List L {O(n)} and print the elementleft to K. If K is found at index 0 print None. 

# Method 2 (Iterative O(log n))
def maxLessThan(root, K):
  max = root.value
  temp = root
  while (not temp.isempty()):
    if (temp.value and K<temp.value):
      temp = temp.left
    elif (temp.value and K>=temp.value):
      max = temp.value
      temp = temp.right

  if (K >= max):
    return max
  else:
    return None
L = [int(item) for item in input().split(" ")]
x = int(input())
root = Tree(L[0])
for item in L[1:]:
  insertToBST(root, item)

print(maxLessThan(root, x))
```
# GRPA 3
<img width="650" src="https://user-images.githubusercontent.com/94922914/235130999-35ef1fda-56bd-46d9-85cd-e8c78af6713c.png"/>

## Solution
```python
def heapify(A, n, i):
    largest = i  
    l = 2 * i + 1    
    r = 2 * i + 2     
    if l < n and A[largest] < A[l]:
        largest = l
    if r < n and A[largest] < A[r]:
        largest = r
    if largest != i:
        A[i], A[largest] = A[largest], A[i] 
        heapify(A, n, largest)
 
def min_max(A):
    n = len(A)
    for i in range(n//2,-1,-1):
        heapify(A,n,i)
```
