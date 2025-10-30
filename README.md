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
def gram_schmidt(A):
    A=np.array(A,dtype=float)
    m,n=A.shape
    Q=np.zeros((m,n))
    R=np.zeros((n,n))

    for j in range(n):
        v=A[:,j]
        for i in range(j):
            R[i,j]=np.dot(Q[:,i],A[:,j])
            v=v-R[i,j]*Q[:,i]
        R[j,j]=np.linalg.norm(v)
        Q[:,j]=v/R[j,j]
   return Q,R

A=[[1,1,0],
   [1,0,1],
   [0,1,1]]

Q,R=gram_schmidt(A)

print("The Q Matrix is")
print(Q)
print("\nThe R Matrix is")
print(R)
```

## Output
```
<img width="462" height="216" alt="Screenshot 2025-10-30 at 10 47 54 AM" src="https://github.com/user-attachments/assets/1afa10f9-6955-4ced-9dd1-6d64085215f9" />

```

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
