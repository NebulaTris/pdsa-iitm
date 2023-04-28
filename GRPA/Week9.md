# GRPA 1
<img width="650" src="https://user-images.githubusercontent.com/94922914/235133010-c9dffaf4-e884-44fa-922f-7f6ae646efbd.png"/>

## Solution
```python
memo = {}
def constructWord(word, wordList):
    if word == '':
        return [[]]
    if word in memo.keys():
        return memo[word]
    totalwordlist = []
    for subword in wordList:
        if subword == word[:len(subword)]:
            subwordList = constructWord(word[len(subword):], wordList)
            totalwordlist.extend([[subword] + lst for lst in subwordList])
    memo[word] = totalwordlist
    return totalwordlist
```
# GRPA 2
<img width="650" src="https://user-images.githubusercontent.com/94922914/235133148-ba8a2260-d1d1-4f03-9154-ce0f6646cfa5.png"/>

## Solution
```python
def MaxCoinPath(M,x1,y1,x2,y2):
    MCP=[]
    # Create matrix same size of M and initialized with 0
    for i in range(len(M)):
        L = []
        for j in range(len(M[0])):
            L.append(0)
        MCP.append(L)
    # Initialize x1 row and y1 coloumn    
    MCP[x1][y1] = M[x1][y1]
    for i in range(y1+1,len(M[0])):
        MCP[x1][i]= MCP[x1][i-1] + M[x1][i]
    for i in range(x1+1,len(M)):
        MCP[i][y1]= MCP[i-1][y1] + M[i][y1]
	# calculate value for each cell
    for i in range(x1+1,len(M)):
        for j in range(y1+1,len(M[0])):
            MCP[i][j] = max(MCP[i-1][j],MCP[i][j-1]) + M[i][j]
    # return max coin value at x2,y2
    return MCP[x2][y2]
M = eval(input())
(x1,y1)=eval(input())
(x2,y2) = eval(input())
print(MaxCoinPath(M,x1,y1,x2,y2))
```
# GRPA 3
<img width="650" src="https://user-images.githubusercontent.com/94922914/235133365-1c8dcc72-c588-4647-92b7-02d635103ef6.png"/>

## Solution
```python
def LDS(L):
    n = len(L)
    LDSCount = [1]*n # LDS with respect to the index
    prev = [None]*n # previous value with respect to the index
    for i in range(n):
        preMax = L[0]
        for j in range(i):
            if L[j] > L[i] and LDSCount[j] > preMax:
                preMax, prev[i] = LDSCount[j], j
        LDSCount[i] = 1 + preMax # updating LDSCount
    mx = max(LDSCount) # count of LDS
    mxi = LDSCount.index(mx) # index of LDS

    # backtracking to get the sequence
    seq = []
    while mxi != None:
        seq.append(L[mxi])
        mxi = prev[mxi]
    return seq[::-1]
```
