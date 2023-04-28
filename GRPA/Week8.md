# GRPA 1
Consider a list L of n integers sorted in ascending order. Write a Python function findOccOf(L, x) to find the first and last occurrences of a number x in list L. Function should return the index of first and last occurrence of x as a tuple, for e.g. if x appears from index 3 to index 7 in list L, then return the tuple (3, 7). If x is not in list L return (None, None). The function should run in O(logn) time.</br>

## Solution
```python
import math
def findLeft(A, x, l, r):
  if (l>r):
    return None

  mid = (l+r)//2
  if (A[mid] == x):
    if (mid == 0 or A[mid] != A[mid-1]):
      return mid
    else:
      return findLeft(A, x, l, mid)
  elif (x > A[mid]):
    return findLeft(A, x, mid+1, r)
  else:
    return findLeft(A, x, l, mid-1)

def findRight(A, x, s, l, r):
  if (l>r):
    return None

  mid = math.ceil((l+r)/2)
  if (A[mid] == x):
    if (mid == s-1 or A[mid] != A[mid+1]):
      return mid
    else:
      return findRight(A, x, s, mid, r)
  elif (x > A[mid]):
    return findRight(A, x, s, mid+1, r)
  else:
    return findRight(A, x, s, l, mid-1)


def findOccOf(L, x):
  s = len(L)
  if (s<1):
    return None
  
  start = findLeft(L, x, 0, s-1)
  end = findRight(L, x, s, 0, s-1)
  return (start, end)
A = [int(item) for item in input().split(" ")]
x = int(input())
timeout = 1.0 # Timeout in sec
```
# GRPA 2
<img width="650" src="https://user-images.githubusercontent.com/94922914/235132036-6da95957-8d8a-4f4b-903d-22186236202a.png"/>

## Solution
```python
def mergeAndCount(A,B):
  (m,n) = len(A), len(B)
  (C, i, j, k, count) = ([], 0, 0, 0, 0)
  while k< m+n:
    if i == m:
      C.append(B[j])
      (j,k) = (j+1, k+1)
    elif j == n:
      C.append(A[i])
      (i,k) = (i+1, k+1)
    elif A[i] < B[j]:
      C.append(A[i]) 
      (i,k) = (i+1, k+1)
    else:
      C.append(B[j])
      (j, k, count) = (j+1, k+1, count+(m-i))
  return (C,count)

def sortAndCount(A):
  n = len(A)
  if n <= 1:
    return(A,0)
  
  (L,countL) = sortAndCount(A[:n//2])
  (R,countR) = sortAndCount(A[n//2:])
  
  (B,countB) = mergeAndCount(L,R)
  return(B,countL+countR+countB)

def countIntersection(X1, X2):
  # Sort according to one points while keeping the matching of points in X1 to X2
  combined = [(X1[i], X2[i]) for i in range(0, len(X1))]
  combined.sort()
  X1, X2 = zip(*combined)

  # Now we just need to count the inversions in X2 for number of intersection points.
  return sortAndCount(X2)[1]
L1 = [int(i) for i in input().split(" ")]
L2 = [int(i) for i in input().split(" ")]
timeout = 2.0  # Timeout in sec
```
# GRPA 3
<img width="650" src="https://user-images.githubusercontent.com/94922914/235132218-ba589730-c8a3-43bc-b823-44ef4e9dd7f5.png"/>

## Solution
```python
import math

# Returns eucledian disatnce between points p and q
def distance(p, q):
  return math.sqrt(math.pow(p[0] - q[0],2) + math.pow(p[1] - q[1],2))

def minDistanceRec(Px, Py):
  s = len(Px)
  # Given number of points cannot be less than 2.
  # If only 2 or 3 points are left return the minimum distance accordingly.
  if (s == 2):
    return distance(Px[0],Px[1])
  elif (s == 3):
    return min(distance(Px[0],Px[1]), distance(Px[1],Px[2]), distance(Px[2],Px[0]))

  # For more than 3 points divide the poitns by point around median of x coordinates
  m = s//2
  Qx = Px[:m]
  Rx = Px[m:]
  xR = Rx[0][0]    # minimum x value in Rx
  
  # Construct Qy and Ry in O(n) rather from Py
  Qy=[]
  Ry=[]
  for p in Py:
    if(p[0] < xR):
      Qy.append(p)
    else:
      Ry.append(p)

  # Extract Sy using delta
  delta = min(minDistanceRec(Qx, Qy), minDistanceRec(Rx, Ry))
  Sy = []
  for p in Py:
    if abs(p[0]-xR) <= delta:
      Sy.append(p)
    
  #print(xR,delta,Sy)
  sizeS = len(Sy)
  if sizeS > 1:
      minS = distance(Sy[0], Sy[1])
      for i in range(1, sizeS-1):
          for j in range(i, min(i+15, sizeS)-1):
              minS = min(minS, distance(Sy[i], Sy[j+1]))
      return min(delta, minS)
  else:
      return delta

def minDistance(Points):
  Px = sorted(Points)
  Py = Points
  Py.sort(key=lambda x: x[-1])
  #print(Px,Py)
  return round(minDistanceRec(Px, Py), 2)

pts = eval(input())
timeout = 2.0  # Timeout in sec
```
# GRPA 4
<img width="650" src="https://user-images.githubusercontent.com/94922914/235132759-2566c928-cac9-4cd6-ac9f-3b246f8a999d.png"/>

## Solution
```python
def partitionPos(arr, pivot):
  arr[pivot], arr[0] = arr[0], arr[pivot]
  l = 1
  r = len(arr)-1
  while (l<r):
    while(arr[l] < arr[0]):
      l+=1
    while(arr[r]>=arr[0]):
      r-=1
    arr[l], arr[r] = arr[r], arr[l]

  return l-1

def MoM7(arr):
  if len(arr) <= 7:
    arr.sort()
    return(arr[len(arr)//2])

  # Construct list of block medians
  M = []

  for i in range(0, len(arr), 7):
    X = arr[i:i+7]
    X.sort()
    M.append(X[len(X)//2])

  return(MoM7(M))

def MoM7Pos(arr): 
  mom = MoM7(arr)
  return partitionPos(arr, arr.index(mom))
arr=[int(item) for item in input().split(" ")]
print(MoM7Pos(arr))
```
