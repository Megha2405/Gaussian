# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm

```
step 1: Import the numpy module to use the built-in functions for calculation.

Step 2: Get input from the user for number of rows and add it by 1 for number of columns.

Step 3: Using np.zeros() set the matrix as null matrix.

Step 4: Using nested for loop get input from the user for each element in the matrix.

Step 5: Using nested for loop find the ratio and perform the elementary row operations and find the final matrix.

Step 6: Use back substitution method to find the value of the variables and print it.
```


## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by:Megha S 
RegisterNumber:24900135
*/



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

    x[n-1]=matrix[n-1][n]/matrix[n-1][n-1]
    for i in range(n-2,-1,-1):
        x[i]=matrix[i][n]
        for j in range(i+1,n):
            x[i]=x[i]-matrix[i][j]*x[j]
        x[i]=x[i]/matrix[i][i]
    for i in range(n):
       print("X%d = %0.2f"%(i,x[i]),end=" ")

```





## Output:
![output](<Screenshot 2024-11-17 145905.png>)



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

