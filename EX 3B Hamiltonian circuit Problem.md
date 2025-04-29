# EX 3B Hamiltonian Circuit Problem
## DATE: 07/03/25
## AIM:
To write a python program to check whether Hamiltonian path exits in the given graph.

## Algorithm

1. Use DP with bitmasking to track visited nodes in all possible paths.  
2. Start with each node as the beginning of the path.  
3. For each subset of nodes, try extending the path to an unvisited neighbor.  
4. Update DP if a valid transition exists.  
5. Check if any path covers all nodes — return `"YES"` if found, else `"NO"`.

## Program:
```
/*
Program to implement to check whether Hamiltonian path exits in the given graph.
Developed by: 
Register Number:  
*/
```
```
def Hamiltonian_path(adj, N):
    dp=[[False for _ in range(1<<N)] for _ in range(N)]
    for i in range(N):
        dp[i][1<<i]=True
    for i in range(1<<N):
        for j in range(N):
            if (i & (1<<j)) and any((i & (1<<k)) and adj[k][j] and j!=k and dp[k][i^(1<<j)] for k in range(N)):
                dp[j][i]=True
    return any(dp[i][(1<<N)-1] for i in range(N))
adj = [ [ 0, 1, 1, 1, 0 ] ,
        [ 1, 0, 1, 0, 1 ],
        [ 1, 1, 0, 1, 1 ],
        [ 1, 0, 1, 0, 0 ] ]
 
N = len(adj)
 
if (Hamiltonian_path(adj, N)):
    print("YES")
else:
    print("NO")

```

## Output:

![image](https://github.com/user-attachments/assets/e4f01e5e-02b2-43eb-84a4-5591f1fca875)


## Result:
The Hamiltonian path program executed successfully, and it determined whether a Hamiltonian path exists in the given graph.
