# GRPA 1
<img width="650" alt="Screenshot 2021-09-23 at 7 32 59 PM" src="https://user-images.githubusercontent.com/94922914/235103707-0fea38a5-1e92-4e99-a2e2-38e51f08704d.png">

## Solution
```python
# Helper function
from collections import deque
class myQueue:
  def __init__(self):
    self.Q = deque()
  
  def deQueue(self):
    return self.Q.popleft()

  def enQueue(self, x):
    return self.Q.append(x)

  def isEmpty(self):
    return False if self.Q else True

def findConnectionLevel(n, Gmat, Px, Py):
  q = myQueue() 
  visited = [False for i in range(n)]
  q.enQueue(Px)
  q.enQueue(-1) #using -1 in queue to distinguish between levels in BFS.
  visited[Px]=True
  level=1;

  while not q.isEmpty():
    v = q.deQueue()
    if (v == -1):
      level+=1
      if (not q.isEmpty()):
        q.enQueue(-1)
      continue
    for i in range(n):
      if(i==Py and Gmat[v][i] == 1):
        return level
      if(Gmat[v][i] and (not visited[i])):
        q.enQueue(i)
        visited[i]=True

  return 0
vertices = int(input())
Amat = []
for i in range(vertices):
  row = [int(item) for item in input().split(" ")]
  Amat.append(row)
personX = int(input())
personY = int(input())
print(findConnectionLevel(vertices, Amat, personX, personY))
```
# GRPA 2
<img width="650" alt="Screenshot 2021-09-23 at 7 33 34 PM" src="https://user-images.githubusercontent.com/94922914/235103845-40235405-e236-4693-96a0-91eab9d2a7ba.png">

## Solution
```python
from collections import deque
class myStack:
  def __init__(self):
    self.stack = deque()
  
  def pop(self):
    return self.stack.pop()
  
  def push(self, x):
    return self.stack.append(x)

  def isEmpty(self):
    return False if self.stack else True

# Run depth first search starting from vertex t and mark all nodes that are visited.
def runDFSForTankT(tanks, GList, t, visited):
  s = myStack()
  s.push(t)
  visited[t] = True

  while not s.isEmpty():
    i = s.pop()
    for p in GList[i]:
      if not visited[p]:
        s.push(p)
        visited[p] = True;

# Brute force approach is to do a DFS for all vertices and check if all other vertices can be reached.
# Time complexity for this approach will be O(n(n+m)). 
# Below function finds the master tank in O(n+m) time complexity. Here v is number of vertices and e is number of edges.
def findMasterTank(tanks, pipes):
  # Create an adjacency list for graph representing the system of pipes and tanks.
  GList = {}
  for i in tanks:
    GList[i]=[]
  for (i,j) in pipes:
    GList[i].append(j)

  # Mark every tank not visited.
  visited = {t:False for t in tanks}
  
  lastVisited = tanks[0] 
  # Traverse the tanks through depth first search method and keep track of last visited tank.
  for t in tanks:
    if not visited[t]:
      runDFSForTankT(tanks, GList, t, visited)
      lastVisited = t

  # Check if this last visited tank has paths to all other tanks in the system by doing another depth first search.
  visited = {t:False for t in tanks}
  runDFSForTankT(tanks, GList, lastVisited, visited)

  # Check visited to verify if all tanks are visited.
  for v in visited:
    if not visited[v]:
      return 0
  return lastVisited

  # Although we are calling DFS multiple times in a loop, the visited marking is common between all these calls. This ensures that we will traverse tanks only once, hence running the solution in linear time.

v = [item for item in input().split(" ")]
#Tanks(vertices) numbered from 1 to n in string format.
numberOfEdges = int(input())
e = []
for i in range(numberOfEdges):
  s = input().split(" ")
  e.append((s[0], s[1]))
print(findMasterTank(v, e))

```
# GRPA 3
<img width="650" alt="Screenshot 2021-09-23 at 7 33 58 PM" src="https://user-images.githubusercontent.com/94922914/235104146-9203f949-b32a-4d63-bb72-b31331c9ec0c.png">
<img width="650" alt="Screenshot 2021-09-23 at 7 34 25 PM" src="https://user-images.githubusercontent.com/94922914/235104243-b9f01011-d706-496d-99b3-92c4d07d0d81.png">

## Solution
```python
# A Queue class to keep track of the visited nodes
class Queue:
  def __init__(self):
    self.queue = []

  def addq(self, v):
    self.queue.append(v)

  def delq(self):
    v = None
    if not self.isempty():
      v = self.queue[0]
      self.queue = self.queue[1:]
      return v

  def isempty(self):
    return self.queue == []

  def __str__(self):
    return str(self.queue)
 
# Dictionary inversion for d which has list as values
def dInv(d): 
  d_ = {}
  if not isinstance(list(d.values())[0], list):
    for k, v in d.items():
      if v not in d_:
        d_[v] = []
      d_[v].append(k)
    return d_

  if isinstance(list(d.values())[0], list):
    for k, v in d.items():
      for v_ in v:
        if v_ not in d_:
          d_[v_] = []
        d_[v_].append(k)
    return d_

# Longest path function from the lecture
def longestpathlist(AList): 
  indegree, lpath = {}, {}
  for u in AList:
    indegree[u], lpath[u] = 0, 0
  for u in AList:
    for v in AList[u]:
      indegree[v] = indegree[v] + 1
  
  zerodegreeq = Queue()
  for u in AList:
    if indegree[u] == 0:
      zerodegreeq.addq(u)
  
  while not zerodegreeq.isempty():
    j = zerodegreeq.delq()
    indegree[j] = indegree[j] - 1
    for k in AList[j]:
      indegree[k] = indegree[k] - 1
      lpath[k] = max(lpath[k], lpath[j] + 1)
      if indegree[k] == 0:
        zerodegreeq.addq(k)
  return lpath
  
def longJourney(AList):
  lpath = longestpathlist(AList) # longest path (dict)
  IAList = dInv(AList) # inverse adjacency list to get the reverse graph
  Ilj = dInv(lpath) # longest path as key and list of cities as values

  maxVal = max(lpath.values()) # value of longest path in which the city ends in the longest path
  prev = Ilj[maxVal][0] # last city
  path = [prev] # appending the last city
  for i in range(maxVal, -1, -1): # going backwards from last city to the first city in terms of longest path
    for p in Ilj[i]: # for every city p has the longest path i
      if p in IAList[prev]: 
        path.append(p) # append to path if there is edge from p to prev in AList or edge from prev to p in IAList(reversed graph)
        prev = p
  return path[::-1] # reverse the path since it is computed from the last
```
