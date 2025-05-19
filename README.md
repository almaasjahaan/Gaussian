# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Import numpy and sys, and create the augmented matrix using np.zeros() and
input() for user data.
2. Use np.linalg.LU() (or similar built-in LU decomposition) to decompose the
augmented matrix into P, L, and U.
3. Solve for the solution vector using back substitution with built-in np.linalg.solve() or
equivalent.
4. Print the solution vector using formatted output with print() and the end the

## Program:
```
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: M ALMAAS JAHAAN
RegisterNumber: 212224230016
'''
import numpy as np
n=int(input())
matrix=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        matrix[i][j]=int(input())
for i in range(n):
        if matrix[i][i]==0:
            matrix[i][i]=1e-10
        for j in range(i+1,n):
            ratio=matrix[j][i]/matrix[i][i]
            for k in range(n+1):
                matrix[j][k]-=ratio*matrix[i][k]
x[n-1]=matrix[n-1][n]/matrix[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=matrix[i][n]
    for j in range(i+1,n):
        x[i]-=matrix[i][j]*x[j]
    x[i]=x[i]/matrix[i][i]
for i in range(n):
    print("X%d = %.2f"%(i,x[i]),end=" ")
```

## Output:
![gaussian elimination]()
![image](https://github.com/user-attachments/assets/6c6f0ac6-12c9-43dd-b4e6-05072ce844d6)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

