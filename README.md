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



## Program:
### Gram-Schmidt Method
```
''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by: LAVANYA S
RegisterNumber: 212223230112
'''
import numpy as np
def QR_Decomposition(A):
    n,m=A.shape
    Q=np.empty((n,m))
    R=np.zeros((n,m))
    U=np.empty((n,m))
    #print(n,m)
    U[:,0]=A[:,0]
    Q[:,0]=U[:,0]/np.linalg.norm(U[:,0])
    for i in range(1,n):
        U[:,i]=A[:,i]
        for j in range(n):
            U[:,i]-=(A[:,i]@Q[:,j])*Q[:,j]
        Q[:,i]= U[:,i]/np.linalg.norm(U[:,i])
    for i in range(n):
        for j in range(i,n):
            R[i,j]=A[:,j]@Q[:,i]
    print(Q)
    print(R)
a = np.array(eval(input()))
QR_Decomposition(a)

```

## Output

![alt text](image-1.png)

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.