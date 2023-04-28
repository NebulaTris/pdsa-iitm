# GRPA 1
<img src="https://user-images.githubusercontent.com/94922914/235100012-42864a30-a772-4c6a-a69c-e815f5b7d141.png" width="650"/>

## Solution
```python
#python
import string
def combinationSort(strList):
  # Create a dictionary with 26 keys from characters 'a' to 'z', each key has an empty list as value.
  groups = {k: [] for k in string.ascii_lowercase}

  # Using this dictionary to group strings with same initial character.  
  for i in range(len(strList)):
    char=strList[i][0]
    groups[char].append(strList[i])
  
  strList=[]
  # Recreate the list from all the strings in groups, iterating on groups from a to z.
  for char in groups.keys():
    for s in groups[char]:
      strList.append(s)
  
  L1 = strList.copy() # Saving intermediate result to return later.
  i = 1
  left = 0
  # As there can be no more than 100 strings with same initial character.
  # Using insertion sort within group.
  while i<len(strList):
    right = i
    while(right>left and strList[right][0] == strList[right-1][0] and int(strList[right-1][1:])<int(strList[right][1:])):
      strList[right], strList[right-1] = strList[right-1], strList[right]
      right -= 1
    i += 1
  
  return L1, strList
```
# GRPA 2
<img width="650" src="https://user-images.githubusercontent.com/94922914/235100272-538b21d0-7a57-4e47-b8c6-565e445354eb.png">

## Solution
```python
#python
def findLargest(L):
  left = 0
  s = len(L)
  right = s-1
  
  # If list has only one element, that is the max.
  if (s==1):
    return L[0]
    
  while (left<=right):
    mid=(left+right)//2
    
    # if mid is at last index, next element to compare will be at index 0
    if (mid == s-1):
      nextToMid = 0
    else:
      nextToMid = mid+1

    if (L[mid] > L[nextToMid]):
      return L[mid]
    elif (L[mid] < L[0]):
      # our element is in left of mid
      right = mid-1
    else:
      # our element is in right of mid
      left = mid+1
```
# GRPA 3
<img width="650" src="https://user-images.githubusercontent.com/94922914/235100457-924cd784-ee7c-442b-819f-09e8d0af089a.png"/>

## Solution
```python
#python
def mergeInPlace(A, B):
  m = len(A)
  n = len(B)
  if (m < 1 or n < 1):
    return 
  
  # Find the smaller list of A and B.
  for i in range(0, m):
    # A and B are already sorted. B[0] will always be least in B, 
    # as we will maintain its sortedness .
    if (A[i] > B[0]):
      A.swap(i, B, 0)
       
      # move `B[0]` to its correct position in B to maintain the sortedness of B
      j = 0
      while(j < n - 1 and B[j] > B[j + 1]):
        B.swap(j+1, B, j)        
        j += 1
```
