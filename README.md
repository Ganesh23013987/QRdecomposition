# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

    ![eqn1](./ex4.jpg)

    ![eqn2](./ex6.jpg)

    ![eqn3](./ex3.jpg)

3.	Obtain the Q matrix   
    ![eqn4](./ex1.jpg)
4.	Construct the upper triangular matrix R
    ![eqn5](./ex2.jpg)

## program steps:
# Step 1: 
Import the numpy library with the alias np
# Step 2: 
Define a function called QR_Decomposition that takes a matrix A as input
# Step 3: 
Get the dimensions of the matrix A
# Step 4: 
Create empty matrices Q and U to store intermediate results
# Step 5: 
Initialize the first column of U and Q
# Step 6: 
Perform Gram-Schmidt process for the remaining columns
# Step 7: 
Initialize the R matrix
# Step 8: 
Populate the upper triangular part of R
# Step 9: 
Print the Q and R matrices
# Step 10: 
Take user input for the matrix A
# Step 11: 
Call the QR_Decomposition function with the input matrix A
# Step 12:
End program.

## Program:
### Gram-Schmidt Method
```
''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by:   Ganesh.D
RegisterNumber: 23013987
'''
import numpy as np
def QR_Decomposition(A):
    n , m = A.shape
    Q = np.empty((n,n))
    U = np.empty((n,n))
    U[:,0] = A[:,0]
    Q[:,0] = U[:,0]/np.linalg.norm(U[:,0])
    for i in range (1,n):
        U[:,i] = A[:,i]
        for j in range(i):
            U[:,i] -=(A[:,i] @ Q[:,j]) * Q[:,j]
        Q[:,i] = U[:,i]/np.linalg.norm(U[:,i])
    R = np.zeros((n,m))
    for i in range(n):
        for j in range(i,m):
            R[i,j] = A[:,j] @ Q[:,i]
    print(Q)
    print(R)
a = np.array(eval(input()))
QR_Decomposition(a)

```

## Output
![Alt text](<Algorithm for QR Decomposition.png>)
## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
Then, the program is successfully executed.