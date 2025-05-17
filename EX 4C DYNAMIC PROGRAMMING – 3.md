# EX 4C DYNAMIC PROGRAMMING – 3
## DATE: 05/04/2025
## AIM:
Given a sequence, find the length of the longest palindromic subsequence in it.





## Algorithm
1.Initialize a square table dp of size n x n.

2.Set diagonal elements of dp to 1.

3.Iterate through increasing substring lengths, filling dp[i][j] based on character comparison and adjacent dp values.

4.The top-right cell dp[0][n-1] holds the result. 

## Program:
```
/*
Program to implement to find the length of the longest palindromic subsequence in it

.
Developed by: LAVANYA S
Register Number: 212223230112
*/
seq=input()
n=len(seq)
str1=seq[::-1]
dp=[[-1]*(1001) for i in range(1001)]
def lps(s1,s2,n1,n2):
    if n1==0 or n2==0:
        return 0
    elif dp[n1][n2]!=-1:
        return dp[n1][n2]
    elif s1[n1-1]==s2[n2-1]:
        dp[n1][n2]=1+lps(s1,s2,n1-1,n2-1)
    else:
        dp[n1][n2]=max(lps(s1,s2,n1-1,n2),lps(s1,s2,n1,n2-1))
    return dp[n1][n2]
print("The length of the LPS is",lps(seq,str1,n,n))
```

## Output:
![image](https://github.com/user-attachments/assets/73cd3da7-aa14-4339-aa83-5a9bd56c2b65)



## Result:
Thus the program was executed successfully for finding the length of longest palindromic string.
