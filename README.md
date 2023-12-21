# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1.import numpy and sys to use the built-in functions for calculation. 
2.Get the size of the matrix (order) fromthe user and initialize an empty matrix and vector
3.Use for loop to get elements of the matrix and vectorfrom the user. 
4.Using another for loop to take each element in the matrix and solve in row echloen form.
5.Perform back substitutions and print the values with two decimal places. 
6.End the Program.

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by:Nithish DM 
RegisterNumber:212223230144
*/
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: Nithish DM
RegisterNumber: 23009598
'''
import sys
import numpy as np
n=int(input())
matrix=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        matrix[i][j]=int(input())
for i in range(n):
    if matrix[i][j]==0.0:
        sys.exit("Divide by zero error")
    for j in range(i+1,n):
        ratio=matrix[j][i]/matrix[i][i]
        for k in range(n+1):
            matrix[j][k]=matrix[j][k]-ratio*matrix[i][k]
x[n-1]=matrix[n-1][n]/matrix[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=matrix[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-matrix[i][j]*x[j]
    x[i]=x[i]/matrix[i][i]
for i in range(n):
    print("X%d = %0.2f"%(i,x[i]),end=' ')
```

## Output:
![ge](https://github.com/Mrnithishx/Gaussian/assets/148201573/4ddd5018-e091-48e9-a314-6334d4e890ed)



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

