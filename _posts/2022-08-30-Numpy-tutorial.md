# Numpy tutorial (keep updating...)

## 1. martix dot product

```python
import numpy as np


A = np.array([[1, 2, 3],[2, 3, 4]]).T
B = np.array([[1, 2, 3],[2, 3, 4]])

C = A@B
print(C)
D = np.dot(A,B)
print(D)
```

Results:

```bash
[[ 5  8 11]
 [ 8 13 18]
 [11 18 25]]
[[ 5  8 11]
 [ 8 13 18]
 [11 18 25]]
 ```

## 2. numpy.vstack() function

**numpy.vstack()** function is used to stack the sequence of input arrays vertically to make a single array.

**Syntax** : numpy.vstack(tup)

**Parameters** :
tup : [sequence of ndarrays] Tuple containing arrays to be stacked. The arrays must have the same shape along all but the first axis.

**Return** : [stacked ndarray] The stacked array of the input arrays.

**Example**:
code:

```python
import numpy as np

#input array
arr1 = np.array([[1, 2, 3], [-1, -2, -3]])
print("1st input array: \n", arr1)
arr2 = np.array([[4, 5, 6], [-4, -5, -6]])
print("2nd input array: \n", arr2)

# Stacking the two arrays vertically
arr3 = np.vstack((arr1, arr2))
print("output stacked array: \n", arr3)
```

output:

```bash
1st Input array : 
[[ 1  2  3]
 [-1 -2 -3]]
2nd Input array : 
[[ 4  5  6]
 [-4 -5 -6]]
Output stacked array :
[[ 1  2  3]
 [-1 -2 -3]
 [ 4  5  6]
 [-4 -5 -6]]
```
