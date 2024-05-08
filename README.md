# Gaussian Elimination
## Date:
## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Initialize a square matrix matrix of size n x (n+1) with zeros.
2. Iterate through each row and column to populate the matrix with user input values.
3. Perform Gaussian elimination
4. Perform back substitution
5. Print the solution vector x. 

## Program:
```
Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: RAMYA R
RegisterNumber: 212223230169
import numpy as np
n=int(input())
matrix=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        matrix[i][j]=int(input())
for i in range(n):
    for j in range(i+1,n):
        ratio=matrix[j][i]/matrix[i][i]
        for k in range(n+1):
            matrix[j][k]=matrix[j][k]-ratio*matrix[i][k]
#Back substitution
x[n-1]=matrix[n-1][n]/matrix[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=matrix[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-matrix[i][j]*x[j]
    x[i]=x[i]/matrix[i][i]
for i in range(n):
    print("X%d = %0.2f" %(i,x[i]),end=" ")
```

## Output:
![alt text](<Screenshot 2024-03-20 090630.png>)
![alt text](<Screenshot 2024-03-20 090638.png>)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

