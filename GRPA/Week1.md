# GRPA 1
<img src="https://user-images.githubusercontent.com/94922914/235096760-c7681067-d68b-4f82-8303-9afa64ad7414.png" width="650"/>

## Solution
```python
def find_Min_Difference(L,P):
  L.sort()
  N = P
  M = len(L)
  min_diff = max(L) - min(L)
  for i in range(M-N+1):
    if L[i+N-1] - L[i] < min_diff:
      min_diff = L[i+N-1] - L[i]
  return min_diff
L=eval(input().strip())
P=int(input())
print(find_Min_Difference(L,P))
```
# GRPA 2
<img width="650" src="https://user-images.githubusercontent.com/94922914/235097289-c8a5d66a-614f-4a3f-8ae1-17852a49fe9a.png">

## Solution
```python
def prime(n):
  if n < 2:
    return False
  for i in range(2,n//2+1):
    if n%i==0:
      return False
  return True

def Goldbach(n):
  Res=[]
  for i in range((n//2)+1):
    if prime(i)==True:
      if prime(n-i)==True:
        Res.append((i,n-i))
  return(Res)
n=int(input())
print(sorted(Goldbach(n)))
```
# GRPA 3
<img width="650" alt="T3W1Q3" src="https://user-images.githubusercontent.com/94922914/235097599-be129a03-904e-4a3e-8e4d-33900f980d72.png">

## Solution
```python
def odd_one(L):
  P = {}
  for elem in L:
    if type(elem) not in P:
      P[type(elem)] = 0
    P[type(elem)] += 1
  for key, value in P.items():
    if value == 1:
      return key.__name__
print(odd_one(eval(input().strip())))
```
