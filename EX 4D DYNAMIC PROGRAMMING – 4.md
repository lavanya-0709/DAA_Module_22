# EX 4D DYNAMIC PROGRAMMING – 4
## DATE: 08/04/2025
## AIM:
To find the minimum number of operations to convert str1 to str2 using Naive recursive method.





## Algorithm
1.Base Cases: If either string is empty, the cost is the length of the other.

2.Last Chars Match: If the last characters are the same, no operation needed; recurse on prefixes.

3.Last Chars Differ: Consider insert, delete, substitute (cost 1 each), and take the minimum of the recursive calls on the resulting substrings.

4.Return Minimum: The final result is the minimum number of operations found through the recursive calls.
   

## Program:
```
/*
Program to implement to find the minimum number of operations to convert str1 to str2 using Naive recursive method

.
Developed by: LAVANYA S
Register Number: 212223230112
*/
def LD(s, t):
    #########  Add your code here ###########
    if s=="":
        return len(t)
    if t=="":
        return len(s)
    if s[-1]==t[-1]:
        cost=0
    else:
        cost=1
    res=min([LD(s,t[:-1])+1,LD(s[:-1],t)+1,LD(s[:-1],t[:-1])+cost])
    return res
    
str1=input()
str2=input()
print('Edit Distance',LD(str1,str2))


```

## Output:
![image](https://github.com/user-attachments/assets/ed05e15b-2a94-491e-8641-cd102aa0cf84)



## Result:
Thus the program was executed successfully for finding edit distance between two strings.
