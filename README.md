# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Input n and n×(n+1) augmented matrix [A|b]
2. Forward elimination: zeros below diagonal
3. Back substitution: solve x[n-1] to x[0]
4. Output solutions x[0] to x[n-1]    

## Program:
```
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: G.Sushanth
RegisterNumber: 212225230088
'''
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"
n = int(input())

a = [[0 for i in range(n + 1)] for j in range(n)]

for i in range(n):
    for j in range(n + 1):
        a[i][j] = float(input())

for i in range(n):
    for j in range(i + 1, n):
        ratio = a[j][i] / a[i][i]
        for k in range(n + 1):
            a[j][k] = a[j][k] - ratio * a[i][k]

x = [0 for i in range(n)]

x[n - 1] = a[n - 1][n] / a[n - 1][n - 1]

for i in range(n - 2, -1, -1):
    x[i] = a[i][n]
    for j in range(i + 1, n):
        x[i] = x[i] - a[i][j] * x[j]
    x[i] = x[i] / a[i][i]

for i in range(n):
    print("X%d = %.2f" % (i, x[i]), end=" ")



```

## Output:
<img width="1077" height="462" alt="Screenshot 2026-05-28 180302" src="https://github.com/user-attachments/assets/880a086d-11e6-46b0-a316-4db2f930eab0" />


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

