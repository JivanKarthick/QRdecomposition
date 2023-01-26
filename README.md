# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by
![1](https://user-images.githubusercontent.com/121165867/214806388-9282af23-a1e2-4389-b821-6bb9526c8add.png)

![2](https://user-images.githubusercontent.com/121165867/214806323-db3cd1e6-e245-4ba7-bc84-ed344a42f8eb.png)

![3](https://user-images.githubusercontent.com/121165867/214806429-907a8deb-7a72-4e75-b593-063ce7e3a016.png)


3.	Obtain the Q matrix   
    ![4](https://user-images.githubusercontent.com/121165867/214806481-3d76de83-c772-4eac-b7f9-9726491e5caf.png)

4.	Construct the upper triangular matrix R
    ![5](https://user-images.githubusercontent.com/121165867/214806530-9f00f8a6-fab3-45a4-b7a1-1ad6034c5cf2.png)




## Program:
### Gram-Schmidt Method
```python
Developed by:Jivan Karthec.B.S
RegisterNumber: 22004763

import numpy as np
arr =np.array(eval(input()))
n,m=arr.shape
u=np.empty((n,m))
e=np.empty((n,m))
u[:,0]=arr[:,0]
e[:,0]=u[:,0]/np.linalg.norm(u[:,0])
for i in range(1,n):
    u[:,i]=arr[:,i]
    for j in range(i):
        u[:,i]-=(arr[:,i]@e[:,j])*e[:,j]
        e[:,i]=u[:,i]/np.linalg.norm(u[:,i])
R=np.zeros((n,m))
for i in range(n):
    for j in range(i,m):
        R[i,j]=arr[:,j]@e[:,i]
print(e)
print(R)


```

## Output
![6](https://user-images.githubusercontent.com/121165867/214807177-c7bc0fba-1533-4419-bf21-6185899b57c7.png)


## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
