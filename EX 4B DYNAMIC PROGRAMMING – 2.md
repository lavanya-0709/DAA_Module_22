# EX 4B DYNAMIC PROGRAMMING – 2
## DATE: 01/04/2025
## AIM:
To find the longest string (or strings) that is a substring (or are substrings) of two strings..



## Algorithm
1.Compare characters of both strings.

2.Build a table tracking matching substring lengths.

3.Find the maximum length in the table.

4.Extract the substring(s) corresponding to the maximum length. 

## Program:
```
/*
Program to implement the longest common substring problem

.
Developed by: LAVANYA S
Register Number: 212223230112
*/
def longest(a,b):
    ma=0
    end=len(a)
    c=[[0]*(len(b)+1)for _ in range(len(a)+1)]
    for i in range(1,len(a)+1):
        for j in range(1,len(b)+1):
            if a[i-1]==b[j-1]:
                c[i][j]=1+c[i-1][j-1]
                if c[i][j]>ma:
                    ma=c[i][j]
                    end=i
    return a[end-ma:end]

a=input()
b=input()
print("The longest common substring is",longest(a,b))
```

## Output:
![image](https://github.com/user-attachments/assets/7fdebc0d-1ec6-4458-9209-6928f6a5057b)



## Result:
Thus the program was executed successfully for finding the longest common substring .
