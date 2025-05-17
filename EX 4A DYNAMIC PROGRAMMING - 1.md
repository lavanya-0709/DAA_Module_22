# EX 4A DYNAMIC PROGRAMMING - 1
## DATE: 29/03/2025
## AIM:
To find longest common subsequence using Dynamic Programming.



## Algorithm
1. Initialize a 2D DP table dp[m+1][n+1] with zeros.

2. Loop through strings X and Y, comparing characters.

3. If characters match, set dp[i][j] = dp[i-1][j-1] + 1.

4. If not, set dp[i][j] = max(dp[i-1][j], dp[i][j-1]).

5. Return dp[m][n] as the length of the LCS (optionally reconstruct sequence). 

## Program:
```
/*
Program to implement the longest common subsequence using Dynamic Programming

.
Developed by: LAVANYA S
Register Number: 212223230112
*/
def lcs(a,b):
    c=[[-1]*(len(b)+1)for _ in range(len(a)+1)]
    for i in range(len(a)+1):
        c[i][len(b)]=0
    for i in range(len(b)+1):
        c[len(a)][i]=0
    for i in range(len(a)-1,-1,-1):
        for j in range(len(b)-1,-1,-1):
            if a[i]==b[j]:
                c[i][j]=1+c[i+1][j+1]
            else:
                c[i][j]=max(c[i+1][j],c[i][j+1])
    return c
def printing(a,b,c):
    i=j=0
    while not (i==len(a) or j==len(b)):
        if a[i]==b[j]:
            print(a[i],end='')
            i+=1
            j+=1
        elif(c[i][j+1]>c[i+1][j]):
            j+=1
        else:
            i+=1

a=input()
b=input()
ans=lcs(a,b)
printing(a,b,ans)
```

## Output:

![image](https://github.com/user-attachments/assets/cc01919f-b3e9-43e6-afa1-67a6b6e8d400)


## Result:
Thus the program was executed successfully for computing the length of longest common subsequence.
