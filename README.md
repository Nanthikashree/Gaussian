# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Read the order of the matrix and input the augmented matrix [A∣B]. Initialize the solution vector X
2. Perform forward elimination to convert the matrix into an upper triangular matrix and check for division by zero.
3. Apply back substitution starting from the last equation to compute the values of unknowns.
4. Display the values of all unknown variables in the solution vector.

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: Nanthikashree T
RegisterNumber: 212225040274
*/
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][j]==0.0:
        sys.exit('Divide by zero detected!')
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
    print("X%d = %0.2f "%(i,x[i]),end="")
```

## Output:
<img width="1072" height="873" alt="image" src="https://github.com/user-attachments/assets/ad2a7ff0-f11c-45ef-ab1a-5767017d7595" />



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

