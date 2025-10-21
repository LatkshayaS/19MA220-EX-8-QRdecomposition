# EX-8- Algorithm for QR Decomposition
## AIM:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## EQUIPMENT'S REQUIRED:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## ALGORITHM:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

    ![eqn1](./ex4.jpg)

    ![eqn2](./ex6.jpg)

    ![eqn3](./ex3.jpg)

3.	Obtain the Q matrix   
    ![eqn4](./ex1.jpg)
4.	Construct the upper triangular matrix R
    ![eqn5](./ex2.jpg)



## PROGRAM:
### Gram-Schmidt Method
``` 
Program to QR decomposition using the Gram-Schmidt method
Developed by: Latkshaya S
RegisterNumber: 25009540
'''
import numpy as np
#Write your code
def g(a):
    
    
    a=np.array( a,dtype=float )
    m,n = a.shape
    q=np.zeros((m,n))
    r=np.zeros((n,n))
    for j in range(n):
       v=a[:,j]
       for i in range (j):
           r[i,j] = np.dot(q[:,i],a[:,j])
           v = v-r[i,j]*q[:,i]
       r[j,j] = np.linalg.norm(v)
       q[:,j] = v/r[j,j]
    return q,r
a=np.array(eval(input()))
q,r=g(a)
print("The Q Matrix is\n",q)
print("The R Matrix is\n",r)







```

## OUTPUT:
```
![EX8.png]()
```

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
