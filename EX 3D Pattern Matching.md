# EX 3D Pattern Matching
## DATE:11/03/25
## AIM:
To write a python program to implement pattern matching on the given string using Brute Force algorithm.

## Algorithm

1. Loop through `s1` from index `0` to `len(s1) - len(s2)`.  
2. For each position, compare characters of `s1` and `s2`.  
3. If all characters match, return the starting index.  
4. If no match is found after all positions, return `-1`.

## Program:
```
/*
Program to implement the Pattern Matching.
Developed by: SANTHIYA R
Register Number: 212223230192
*/
```
```
def BF(s1,s2):
    len_s1=len(s1)
    len_s2=len(s2)
    for i in range(len_s1-len_s2+1):
        j=0
        while j<len_s2 and s1[i+j]==s2[j]:
            j+=1
        if j==len_s2:
            return i
    return -1
if __name__ == "__main__":
    a1=input() 
    a2=input() 
    b=BF(a1,a2)
    print(b)
```

## Output:

![image](https://github.com/user-attachments/assets/5033c27e-5e64-4b47-8e4b-83def9a01e52)


## Result:
The brute force substring search program executed successfully and returned the starting index of the match or 0 if no match was found.
