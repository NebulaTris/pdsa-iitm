# GRPA 1
<img width="650" src="https://user-images.githubusercontent.com/94922914/235133655-56894598-1d37-4d24-ac12-e00a42c59d35.png"/>

## Solution
```python
def findContinuousRepetitions(t, p):
  last = {} # Preprocess
  m = len(p)
  for i in range(m):
    last[p[i]] = i
  poslist, i, count, maxR = [], 0, 0, 0 # Loop
  
  while i <= (len(t)-m):
    matched,j = True,len(p)-1
    poslist.append(i)
    while j > 0 and matched:
      if t[i+j] != p[j]:
        matched = False
        count = 0
      j = j - 1
    if matched:
      count += 1
      if (count > maxR): maxR = count 
      i = i + m
    else:
      j = j + 1
      if t[i+j] in last.keys():
        i = i + max(j-last[t[i+j]],1)
      else:
        i = i + j + 1
  return maxR
t = input()
p = input()
print(findContinuousRepetitions(t, p))
```
# GRPA 2
<img width="650" src="https://user-images.githubusercontent.com/94922914/235133757-6b1ed619-e988-498b-83c7-587b67b07a09.png"/>

## Solution
```python
def FindPattern(T,P):
    last = {} # Preprocess
    for i in range(len(P)):
        if P[i] != '$':
            last[P[i]] = i
    poslist=[]
    i = 0 # Loop
    while i <= (len(T)-len(P)):
        matched,j = True,len(P)-1
        while j >= 0 and matched:
            if P[j] != '$':
                if T[i+j] != P[j]:
                    matched = False
            j = j - 1            
        if matched:
            poslist.append((i,T[i:i+len(P)]))
            i = i + 1
        else:
            j = j + 1
            if T[i+j] in last.keys():
                i = i + max(j-last[T[i+j]],1)
            else:
                i = i + 1
    return(poslist)
T = input()
P = input()
print(FindPattern(T,P))
```
# GRPA 3
<img width="650" src="https://user-images.githubusercontent.com/94922914/235133869-7f2e166c-b844-4988-a2cb-37c8dcd9bcc4.png"/>

## Solution
```python
def kmp_fail(p):
# Initialize
    m = len(p)
    fail = [0 for i in range(m)]
# Update
    j,k = 1,0
    while j < m:
        if p[j] == p[k]: #k+1 chars match
            fail[j] = k+1
            j,k = j+1,k+1
        elif k > 0: #find shorter prefix
            k = fail[k-1]
        else: #no match found at j
            j = j+1
    return(fail[-1])

def MakePalindrome(s):
    if len(s)==0:
        return s
    m = kmp_fail(s + '#' + s[::-1])
    if m == len(s):
        return None        
    else:
        return s[m:][::-1]
s = input()
print(MakePalindrome(s))
```
