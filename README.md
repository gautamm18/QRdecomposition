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
<img width="1036" height="141" alt="image" src="https://github.com/user-attachments/assets/e0687a6b-c2d1-4237-9546-12a2e414bb53" />

### Gram-Schmidt Method
import numpy as np
import matplotlib.pyplot as plt

def gram_schmidt(vectors):
    Q = []
    for v in vectors:
        for q in Q:
            v -= np.dot(q, v) * q
        Q.append(v / np.linalg.norm(v))
    return np.array(Q)

# Sample 2D vectors
v1 = np.array([2, 1])
v2 = np.array([1, 2])

# Apply Gram-Schmidt
Q = gram_schmidt([v1, v2])

# Plot original and orthogonalized vectors
plt.figure()
origin = np.zeros(2)

plt.quiver(*origin, *v1, color='r', scale=5, label='v1')
plt.quiver(*origin, *v2, color='b', scale=5, label='v2')
plt.quiver(*origin, *Q[0], color='g', scale=5, label='q1 (orthogonal)')
plt.quiver(*origin, *Q[1], color='orange', scale=5, label='q2 (orthogonal)')

plt.axis('equal')
plt.legend()
plt.title('Gram-Schmidt Orthogonalization Visualization (2D)')
plt.show()





```







```

## Output
```
<img width="1040" height="217" alt="image" src="https://github.com/user-attachments/assets/b6b6572a-3d80-4931-a416-e137f218e6a4" />

```

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
