# EX 3A Knight Tour & Count Path
## DATE: 07/03/25
## AIM:
To write a python program to find minimum steps to reach to specific cell in minimum moves by knight

## Algorithm
1. Start BFS from the knight's position.  
2. Explore all 8 moves of a knight from the current cell.  
3. Mark visited cells to avoid revisits.  
4. Stop when target is reached — return steps taken.  
5. Print the minimum number of steps.
6. 
## Program:
```
/*
Program to implement to find minimum steps to reach to specific cell in minimum moves by knight.
Developed by: SANTHIYA R
Register Number: 212223230192
*/
```
```
class cell:
     
    def __init__(self, x = 0, y = 0, dist = 0):
        self.x = x
        self.y = y
        self.dist = dist

def isInside(x, y, N):
    if (x >= 1 and x <= N and
        y >= 1 and y <= N):
        return True
    return False
def minStepToReachTarget(knightpos,targetpos, N):
    dx = [2, 2, -2, -2, 1, 1, -1, -1]
    dy = [1, -1, 1, -1, 2, -2, 2, -2]
    
    visited = [[False for _ in range(N + 1)] for _ in range(N + 1)]
    queue = []
    
    queue.append(cell(knightpos[0], knightpos[1], 0))
    visited[knightpos[0]][knightpos[1]] = True
    
    while queue:
        current = queue.pop(0)
        
        if current.x == targetpos[0] and current.y == targetpos[1]:
            return current.dist
        
        for i in range(8):
            x = current.x + dx[i]
            y = current.y + dy[i]
            
            if isInside(x, y, N) and not visited[x][y]:
                queue.append(cell(x, y, current.dist + 1))
                visited[x][y] = True

N = 30
knightpos = [1, 1]
targetpos = [30, 30]
print(minStepToReachTarget(knightpos,targetpos, N))
```
## Output:

![image](https://github.com/user-attachments/assets/cdb654d0-9b89-4c19-ae7c-11debde7aa08)


## Result:
The program executed successfully, and the minimum number of steps for the knight to reach the target was calculated.
