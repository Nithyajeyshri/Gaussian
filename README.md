# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Input the number of equations and form the augmented matrix with coefficients and constants.

2. Apply forward elimination to convert the matrix into an upper triangular form by eliminating lower elements using row operations.

3. Perform back substitution starting from the last equation to find each variable sequentially.

4. Display the computed values of all unknowns as the final solution.

## Program:
```
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: NITHYA JEYSHRI S S
RegisterNumber: 212225040288
'''
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
    if a[i][i]==0.0:
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
    print('X%d = %0.2f'% (i,x[i]),end=' ')
```

## Output:
<img width="1431" height="847" alt="Screenshot 2026-05-20 083612" src="https://github.com/user-attachments/assets/28eeec62-d770-4fe4-8131-c6c377c27495" />
<img width="1419" height="802" alt="Screenshot 2026-05-20 083632" src="https://github.com/user-attachments/assets/23c9b965-ffb8-4e76-909c-8e7709408bd9" />
<img width="1425" height="325" alt="Screenshot 2026-05-20 083644" src="https://github.com/user-attachments/assets/0569e32f-f924-4aa8-b2b8-50902050643d" />


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

