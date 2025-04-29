# EX 3C Sudoku Solver
## DATE: 11/03/25
## AIM:
To write a python program to find the solution of sudoku puzzle using Backtracking.


## Algorithm

1. Traverse the board to find the first empty cell (value `0`).  
2. Try placing numbers `1` to `9`** in that cell.  
3. Check safety the number must not repeat in the row, column, or 3×3 subgrid.  
4. If safe, place the number and recursively solve the rest of the board.  
5. Backtrack by resetting the cell if the move leads to no solution.  
6. Print board when all cells are filled correctly.

## Program:
```
/*
Program to implement to to find the solution of sudoku puzzle using Backtracking.
Developed by: SANTHIYA R
Register Number: 212223230192
*/
```
```
board = [
    [0, 0, 0, 8, 0, 0, 4, 0, 3],
    [2, 0, 0, 0, 0, 4, 8, 9, 0],
    [0, 9, 0, 0, 0, 0, 0, 0, 2],
    [0, 0, 0, 0, 2, 9, 0, 1, 0],
    [0, 0, 0, 0, 0, 0, 0, 0, 0],
    [0, 7, 0, 6, 5, 0, 0, 0, 0],
    [9, 0, 0, 0, 0, 0, 0, 8, 0],
    [0, 6, 2, 7, 0, 0, 0, 0, 1],
    [4, 0, 3, 0, 0, 6, 0, 0, 0]
]

def printBoard(board):
    for i in range(0, 9):
        for j in range(0, 9):
            print(board[i][j], end=" ")
        print()

def isPossible(board, row, col, val):
    for j in range(0, 9):
        if board[row][j] == val:
            return False

    for i in range(0, 9):
        if board[i][col] == val:
            return False

    startRow = (row // 3) * 3
    startCol = (col // 3) * 3
    for i in range(0, 3):
        for j in range(0, 3):
            if board[startRow+i][startCol+j] == val:
                return False
    return True

def solve():
    for row in range(9):
        for col in range(9):
            if board[row][col] == 0:
                for val in range(1, 10):
                    if isPossible(board, row, col, val):
                        board[row][col] = val
                        solve()
                        board[row][col] = 0
                return
    printBoard(board)
solve()

```

## Output:

![image](https://github.com/user-attachments/assets/88304812-b784-431e-915f-bb2e103a3baf)


## Result:
The Sudoku solver program executed successfully and found the solution for the given puzzle.
