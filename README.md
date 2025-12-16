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
import numpy as np
def QR_Decomposition(A):
    # Write your code 
    A=A.astype(float)
    m,n=A.shape
    Q=np.zeros((m,n))
    R=np.zeros((n,n))
    for i in range(n):
        u=A[:,i]
        for j in range(i):
            R[j,i]= np.dot(Q[:,j],A[:,i])
            u=u-R[j,i]*Q[:,j]
        R[i,i]= np.linalg.norm(u)
        Q[:,i]= u/R[i,i]
    print("The Q Matrix is")
    print(f" {Q}")
    print("The R Matrix is")
    print(f" {R}")
a = np.array(eval(input()))
QR_Decomposition(a)






```

## Output
```
<img width="1366" height="768" alt="Screenshot 2025-12-16 201841" src="https://github.com/user-attachments/assets/9271726b-fac0-43a2-b33d-2bf635bd9216" />

```

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
