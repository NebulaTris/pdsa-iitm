# GRPA 1
<img src="https://user-images.githubusercontent.com/94922914/235104820-55dd535f-7e5b-4598-89b7-8833b4daa453.png" width="650"/>

## Solution
```python
def kruskal(WList):
    (edges,component,TE)=([],{},[])
    for u in WList.keys():
        edges.extend([(d,u,v) for (v,d) in WList[u]])
        component[u] = u
    edges.sort()
    for (d,u,v) in edges:
        if component[u] != component[v]:
            TE.append((u,v))
            c = component[u]
        for w in WList.keys():
            if component[w] == c:
                component[w] = component[v]
    return(TE)

def FiberLink(distance_map):
    R = kruskal(distance_map)
    S = 0
    for e in R:
        for ed in distance_map[e[0]]:
            if ed[0]==e[1]:
                S += ed[1]
    return S
size = int(input())
edges = eval(input())
WL = {}
for i in range(size):
    WL[i] = []
for ed in edges:
    WL[ed[0]].append((ed[1],ed[2]))
    WL[ed[1]].append((ed[0],ed[2]))
print(FiberLink(WL))
```
# GRPA 2
<img width="650" src="https://user-images.githubusercontent.com/94922914/235104940-91db4f47-359c-499d-9274-d571bfcb7d47.png"/>

## Solution
```python
def dijkstra(WList,s):
    infinity = 1 + len(WList.keys())*max([d for u in WList.keys()for (v,d) in WList[u]])
    (visited,distance,prev) = ({},{},{})
    for v in WList.keys():
        (visited[v],distance[v],prev[v]) = (False,infinity,None)       
    distance[s] = 0    
    for u in WList.keys():
        nextd = min([distance[v] for v in WList.keys() if not visited[v]])
        nextvlist = [v for v in WList.keys() if (not visited[v]) and distance[v] == nextd]
        if nextvlist == []:
            break
        nextv = min(nextvlist)        
        visited[nextv] = True        
        for (v,d) in WList[nextv]:
            if not visited[v]:
                if distance[v] > distance[nextv]+d:
                    distance[v] = distance[nextv]+d
                    prev[v] = nextv    
    return(distance,prev)


def min_cost_walk(WList,S, D, V):
    distance1,path1 = dijkstra(WList, S)
    distance2,path2 = dijkstra(WList, V)
    tot_dist = distance1[V] + distance2[D]
    Route_S_V = []
    Route_V_D = []
	# shortest route for S to V
    if distance1[V] != 0:
        dest = V
        while dest != S:
            Route_S_V = [dest] + Route_S_V
            for i,j in path1.items():
                if dest == i:
                    dest = j
                    break
        Route_S_V = [dest] + Route_S_V
  	# shortest route for V to D
    if distance2[D] != 0:
        dest = D
        while dest != V:
            Route_V_D = [dest] + Route_V_D
            for i,j in path2.items():
                if dest == i:
                    dest = j
                    break
        Route_V_D = [dest] + Route_V_D
    Route_S_D = Route_S_V[:-1]+ Route_V_D
    return (tot_dist,Route_S_D)
size = int(input())
edges = eval(input())
S= int(input())
D=int(input())
V=int(input())
WL = {}
for i in range(size):
    WL[i] = []
for ed in edges: #for create list for undirected graph
    WL[ed[0]].append((ed[1],ed[2]))
    WL[ed[1]].append((ed[0],ed[2]))
print(min_cost_walk(WL,S, D, V))
```
# GRPA 3
<img width="650" src="https://user-images.githubusercontent.com/94922914/235105267-c9c856c0-70e3-4c95-9cdb-2ce1f8ad3db0.png">

## Solution
```python
def IsNegativeWeightCyclePresent(WList):
    s = 0
    infinity = 1 + len(WList.keys())*max([d for u in WList.keys() for (v,d) in WList[u]])
    distance = {}
    for v in WList.keys():
        distance[v] = infinity        
    distance[s] = 0 
    for i in WList.keys():
        for u in WList.keys():
            for (v,d) in WList[u]:
                distance[v] = min(distance[v], distance[u] + d)

    for u in WList.keys():
        for (v,d) in WList[u]:
            if (distance[u] + d < distance[v]):
                return True
    return False
size = int(input())
edges = eval(input())
WL = {}
for i in range(size):
    WL[i] = []
for ed in edges:
    WL[ed[0]].append((ed[1],ed[2]))
    
print(IsNegativeWeightCyclePresent(WL))
```
